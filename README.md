# Multiplexer-and-Demultiplexer-Design
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

-- 2:1 Multiplexer Entity
entity MUX_2to1 is
    Port ( I0 : in  STD_LOGIC;
           I1 : in  STD_LOGIC;
           S  : in  STD_LOGIC;
           Y  : out STD_LOGIC);
end MUX_2to1;

architecture Behavioral of MUX_2to1 is
begin
    process(I0, I1, S)
    begin
        if (S = '0') then
            Y <= I0;
        else
            Y <= I1;
        end if;
    end process;
end Behavioral;

library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

-- 1:2 Demultiplexer Entity
entity DEMUX_1to2 is
    Port ( I  : in  STD_LOGIC;
           S  : in  STD_LOGIC;
           Y0 : out STD_LOGIC;
           Y1 : out STD_LOGIC);
end DEMUX_1to2;

architecture Behavioral of DEMUX_1to2 is
begin
    process(I, S)
    begin
        -- Default assignment to prevent latches
        Y0 <= '0';
        Y1 <= '0';
        if (S = '0') then
            Y0 <= I;
        else
            Y1 <= I;
        end if;
    end process;
end Behavioral;

