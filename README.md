# battery
just code for information about battery and information in linux

# Code 

#!/bin/bash
# Battery profile: 50–60%
# Author: Aniket
# Usage: sudo battery-50-60
# sudo nano /usr/local/bin/battery

# power device
echo "upower -i /org/freedesktop/UPower/devices/battery_BAT1"
upower -i /org/freedesktop/UPower/devices/battery_BAT1


# battery full information 
echo "battery information - grep . /sys/class/power_supply/BAT1/* 2>/dev/null"
grep . /sys/class/power_supply/BAT1/* 2>/dev/null

#acpi infromation 
echo "acpi battery information - acpi -V"
acpi -V



# # Previous barrty limit
# # Display battery status

# echo "Previous Start: $(cat /sys/class/power_supply/BAT1/charge_control_start_threshold)%  End: $(cat /sys/class/power_supply/BAT1/charge_control_end_threshold)%"


# Now Apply charge limits
# sudo sh -c 'echo 40 > /sys/class/power_supply/BAT1/charge_control_start_threshold'
# sudo sh -c 'echo 50 > /sys/class/power_supply/BAT1/charge_control_end_threshold'

# echo "Now Battery charge limits set to 40–50%"
# echo "------------------------------------"

# Display battery status

# echo "Start: $(cat /sys/class/power_supply/BAT1/charge_control_start_threshold)%  End: $(cat /sys/class/power_supply/BAT1/charge_control_end_threshold)%"


# Display system 
echo "System Info: inxi -F"
inxi -F

#Fastfetch
echo "fastfetch"
fastfetch

#boot time
echo "Boot Time"
systemd-analyze

#boot time for chain
echo "Boot time chain time- systemd-analyze critical-chain "
systemd-analyze critical-chain




