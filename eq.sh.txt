#!/bin/sh

mkdir -p ~/.config/pipewire/pipewire.conf.d
cp /usr/share/pipewire/filter-chain/sink-eq6.conf ~/.config/pipewire/pipewire.conf.d/sink-eq6.conf
sed -i.bak  '23 s/control = { "Freq" = 100.0 "Q" = 1.0 "Gain" = 0.0 }/control = { "Freq" = 200.0 "Q" = 0.6 "Gain" = 10.5 }/' ~/.config/pipewire/pipewire.conf.d/sink-eq6.conf
sed -i '41 s/control = { "Freq" = 5000.0 "Q" = 1.0 "Gain" = 0.0 }/control = { "Freq" = 14000.0 "Q" = 0.6 "Gain" = 8.0 }/' ~/.config/pipewire/pipewire.conf.d/sink-eq6.conf
sed -i '47 s/control = { "Freq" = 5000.0 "Q" = 1.0 "Gain" = 0.0 }/control = { "Freq" = 0 "Q" = 1.0 "Gain" = 5.0 }/' ~/.config/pipewire/pipewire.conf.d/sink-eq6.conf

echo "reboot steamOS!"
