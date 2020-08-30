# Conky

Conky é um monitor de sistema de desktop, é altamente personalizável.

## Instalação

1. `dnf -y install conky hddtemp curl lm_sensors`
2. `chmod u+s /usr/sbin/hddtemp`
3. Digite no terminal: `sensors-detect` e use as configurações padrão para as respostas
4. Encontre o nome da sua interface de rede com `ip addr`
5. Criar arquivo de configuração `touch ~/.conkyrc`
6. Ative a auto inicialização no Gnome Config (Ajustes)
7. Obtenha ajuda [aqui](http://www.ifxgroup.net/conky.htm)

## Personalização

Altere no arquivo de configuração `gedit /etc/conky/conky.conf`, ou altere este arquivo configuração `gedit /home/seu)usuario/.conkyrc`.

Após a versão 1.x o aquivo de personalização aceita apenas a linguagem LUA. Portanto, copie e cole o seguinte código substituindo o original no arquivo acima.

Em `conky.text = [[` descomente as opções para monitorar a placa da NVidia, para descomentar, retire os `--` e espaço das linhas antes do sinal de `$`.

```lua
-- Conky settings
conky.config = {
  gap_x = 5,
	gap_y = 30,
	alignment = 'top_right',
	background = false,
	border_width = 0.5,
	font = 'Segoe UI:size = 9',
	stippled_borders = 0,
	update_interval = 0.001,
	uppercase = false,
	total_run_times = 0,
	format_human_readable = true,
	extra_newline = true,
	nvidia_display = true,
	nvidia = true,

	cpu_avg_samples = 8,
	diskio_avg_samples = 2,
	net_avg_samples = 2,

	text_buffer_size = 256,
	imlib_cache_size = 32768,
	imlib_cache_flush_interval = 300,
	no_buffers = true,
	short_units = true,
	if_up_strictness = 'address',
  
	default_color = 'lightgray',
	default_outline_color = 'white',
	default_shade_color = 'black',
  
	draw_borders = false,
	draw_graph_borders = false,
	draw_outline = false,
	draw_shades = false,
  
	extra_newline = false,
	minimum_height = 5,
	minimum_width = 200,
	maximum_width = 200,
  
	out_to_console = false,
	out_to_ncurses = false,
	out_to_stderr = false,
	out_to_x = true,
  
	override_utf8_locale = true,
  
  own_window = true,
  -- own_window_type = 'override',
	own_window_colour = 000000,
	own_window_class = Conky,
	own_window_argb_visual = true,
	own_window_argb_count = 0,
	own_window_argb_value = 128,
	own_window_type = desktop,
	own_window_transparent = true,
  own_window_hints = 'undecorated,below,sticky,skip_taskbar,skip_pager',
  own_window_argb_visual = true, own_window_argb_value = 192,
  
  double_buffer = true,

	show_graph_range = false,
	show_graph_scale = false,

	temperature_unit = 'celsius',

	use_spacer = 'none',
	use_xft = true,
	xftalpha = 0.5,
	xftfont = 'Segoe UI:size=10',
}

conky.text = [[

  ${color 294172}${font ConkyColorsLogos:size=10}f${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color 294172}SYSTEM ${hr 2}$color${font}
  ${font ConkyColorsLogos:size=10}l${font}
  ${offset +15}${voffset -30}${font Segoe UI:size=9}Kernel${alignr}${kernel}

  ${color 127CC1}${font ConkyColors:size=10}l${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color dodgerblue3}PERFORMANCE ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9} System Uptime ${alignr}${color}${uptime_short}
  ${font ConkyColors:size=10}d${font}
  ${offset +15}${voffset -30}${font Segoe UI:size=9}Package ${cpu}% ${alignr}Freq: ${freq_g} GHz
  ${cpugraph 0 10,200 009afa ff0000 -t -l}

  ${color 127CC1}${font ConkyColorsLogos:size=10}i${font}
  ${offset +15}${voffset -30}${color 127CC1}${font Segoe UI:bold:size=9}PROCESSORS ${hr 2}$color${font}
  ${font Segoe UI:size=9}Core1 ${cpu cpu1}% ${voffset 1}${alignr}${cpubar cpu1 7,140}
  Freq: ${freq_g 1}GHz 
  Core2 ${cpu cpu2}% ${voffset 1}${alignr}${cpubar cpu2 7,140}
  Freq: ${freq_g 2}GHz 
  Core3 ${cpu cpu3}% ${voffset 1}${alignr}${cpubar cpu3 7,140}
  Freq: ${freq_g 3}GHz 
  Core4 ${cpu cpu4}% ${voffset 1}${alignr}${cpubar cpu4 7,140}
  Freq: ${freq_g 4}GHz
  Core5 ${cpu cpu5}% ${voffset 1}${alignr}${cpubar cpu5 7,140}
  Freq: ${freq_g 5}GHz 
  Core6 ${cpu cpu6}% ${voffset 1}${alignr}${cpubar cpu6 7,140}
  Freq: ${freq_g 6}GHz
  Core7 ${cpu cpu7}% ${voffset 1}${alignr}${cpubar cpu7 7,140}
  Freq: ${freq_g 7}GHz 
  Core8 ${cpu cpu8}% ${voffset 1}${alignr}${cpubar cpu8 7,140}
  Freq: ${freq_g 8}GHz

  ${color 127CC1}${font Font Awesome:size=10}
  ${color 127CC1}${offset +15}${voffset -16}${font Segoe UI:Bold:size=9}CPU TEMPERATURES ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}Package: ${hwmon 1 temp 1}°C
  Core1: ${hwmon 1 temp 2}°C${alignr}Core2: ${hwmon 1 temp 3}°C
  Core3: ${hwmon 1 temp 4}°C${alignr}Core4: ${hwmon 1 temp 5}°C
  ${font Segoe UI:size=9}CPU Fan: ${hwmon 2 fan 2} RPM

  ${color black}${font ConkyColors:size=10}g${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color black}MEMORY ${hr 2}$color${font}
  ${font Segoe UI:size=9}Use: ${mem}/${memmax}${alignr}Free: ${memeasyfree}
  ${memperc}%${memgraph 10,180 lightgray black -t -l}

  ${color dodgerblue3}${font Font Awesome:size=10}
  ${color dodgerblue3}${offset +18}${voffset -16}${font Segoe UI:Bold:size=9}NETWORK ${hr 2}$color${font}
  ${font Segoe UI:size=9}External IP ${color red}${alignr}${exec curl ipinfo.io/ip}
  ${color}IPv4  ${color red}${alignr}${addr enp4s0}${color}
  ${font Font Awesome:style=Duotone:size=10} ${font Segoe UI:size=9}${color}${downspeedf enp4s0}Kbps${alignr}${downspeedgraph enp4s0 10,120 00fa1d 00fa1d -t -l}
  ${font Font Awesome:style=Duotone:size=10} ${font Segoe UI:size=9}$color${upspeedf enp4s0}Kbps${alignr}${upspeedgraph enp4s0 10,120 fab700 fab700 -t -l}
  
  ${color 12279e}${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:Bold:size=9}${color 12279e}STORAGE ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}${exec hddtemp /dev/sda | cut -c11-29}
  ${fs_used}b/${fs_size}b${alignr}${exec hddtemp -n --unit=C /dev/sda}°C
  Read ${diskio_read /dev/sda2}${alignr}${diskiograph_read /dev/sda2 10,120 ffffff ff0000 -t -l}
  Write ${diskio_write /dev/sda2}${alignr}${diskiograph_write /dev/sda2 10,120 ffffff ff0000 -t -l}
  ${fs_used_perc}% ${voffset 1}${fs_bar 7}
  ${voffset -5}${hr 0}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}${exec hddtemp /dev/sdb1 | cut -c12-22}
  ${fs_used /mnt/Compartilhado}b/${fs_size /mnt/Compartilhado}b${alignr}${exec hddtemp -n --unit=[C] /dev/sdb}°C | ${exec hddtemp -n --unit=[C] /dev/sdc}°C
  Read ${diskio_read /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1}${alignr}${diskiograph_read /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1 10,120 ffffff ff0000 -t -l}
  Write ${diskio_write /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1}${alignr}${diskiograph_write /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1 10,120 ffffff ff0000 -t -l}
  ${fs_used_perc /mnt/Compartilhado}% ${voffset 1}${fs_bar 7 /mnt/Compartilhado}
  ${voffset -5}${hr 0}
  SWAP ${voffset 1}${swapbar 7}
  ${swap}/${swapmax} ${alignr} ${swapperc}%
]]
```

O Arquivo de personalização sem GPU:

```lua
-- Conky settings
conky.config = {
  gap_x = 5,
	gap_y = 30,
	alignment = 'top_right',
	background = false,
	border_width = 0.5,
	font = 'Segoe UI:size = 9',
	stippled_borders = 0,
	update_interval = 0.001,
	uppercase = false,
	total_run_times = 0,
	format_human_readable = true,
	extra_newline = true,
	nvidia_display = true,
	nvidia = true,

	cpu_avg_samples = 8,
	diskio_avg_samples = 2,
	net_avg_samples = 2,

	text_buffer_size = 256,
	imlib_cache_size = 32768,
	imlib_cache_flush_interval = 300,
	no_buffers = true,
	short_units = true,
	if_up_strictness = 'address',
  
	default_color = 'lightgray',
	default_outline_color = 'white',
	default_shade_color = 'black',
  
	draw_borders = false,
	draw_graph_borders = false,
	draw_outline = false,
	draw_shades = false,
  
	extra_newline = false,
	minimum_height = 5,
	minimum_width = 200,
	maximum_width = 200,
  
	out_to_console = false,
	out_to_ncurses = false,
	out_to_stderr = false,
	out_to_x = true,
  
	override_utf8_locale = true,
  
  own_window = true,
  -- own_window_type = 'override',
	own_window_colour = 000000,
	own_window_class = Conky,
	own_window_argb_visual = true,
	own_window_argb_count = 0,
	own_window_argb_value = 128,
	own_window_type = desktop,
	own_window_transparent = true,
  own_window_hints = 'undecorated,below,sticky,skip_taskbar,skip_pager',
  own_window_argb_visual = true, own_window_argb_value = 192,
  
  double_buffer = true,

	show_graph_range = false,
	show_graph_scale = false,

	temperature_unit = 'celsius',

	use_spacer = 'none',
	use_xft = true,
	xftalpha = 0.5,
	xftfont = 'Segoe UI:size=10',
}

conky.text = [[

  ${color 294172}${font ConkyColorsLogos:size=10}f${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color 294172}SYSTEM ${hr 2}$color${font}
  ${font ConkyColorsLogos:size=10}l${font}
  ${offset +15}${voffset -30}${font Segoe UI:size=9}Kernel${alignr}${kernel}

  ${color 127CC1}${font ConkyColors:size=10}l${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color dodgerblue3}PERFORMANCE ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9} System Uptime ${alignr}${color}${uptime_short}
  ${font ConkyColors:size=10}d${font}
  ${offset +15}${voffset -30}${font Segoe UI:size=9}Package ${cpu}% ${alignr}Freq: ${freq_g} GHz
  ${cpugraph 0 10,200 009afa ff0000 -t -l}

  ${color 127CC1}${font ConkyColorsLogos:size=10}i${font}
  ${offset +15}${voffset -30}${color 127CC1}${font Segoe UI:bold:size=9}PROCESSORS ${hr 2}$color${font}
  ${font Segoe UI:size=9}Core1 ${cpu cpu1}% ${voffset 1}${alignr}${cpubar cpu1 7,140}
  Freq: ${freq_g 1}GHz 
  Core2 ${cpu cpu2}% ${voffset 1}${alignr}${cpubar cpu2 7,140}
  Freq: ${freq_g 2}GHz 
  Core3 ${cpu cpu3}% ${voffset 1}${alignr}${cpubar cpu3 7,140}
  Freq: ${freq_g 3}GHz 
  Core4 ${cpu cpu4}% ${voffset 1}${alignr}${cpubar cpu4 7,140}
  Freq: ${freq_g 4}GHz
  Core5 ${cpu cpu5}% ${voffset 1}${alignr}${cpubar cpu5 7,140}
  Freq: ${freq_g 5}GHz 
  Core6 ${cpu cpu6}% ${voffset 1}${alignr}${cpubar cpu6 7,140}
  Freq: ${freq_g 6}GHz
  Core7 ${cpu cpu7}% ${voffset 1}${alignr}${cpubar cpu7 7,140}
  Freq: ${freq_g 7}GHz 
  Core8 ${cpu cpu8}% ${voffset 1}${alignr}${cpubar cpu8 7,140}
  Freq: ${freq_g 8}GHz

  ${color 127CC1}${font Font Awesome:size=10}
  ${color 127CC1}${offset +15}${voffset -16}${font Segoe UI:Bold:size=9}CPU TEMPERATURES ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}Package: ${hwmon 1 temp 1}°C
  Core1: ${hwmon 1 temp 2}°C${alignr}Core2: ${hwmon 1 temp 3}°C
  Core3: ${hwmon 1 temp 4}°C${alignr}Core4: ${hwmon 1 temp 5}°C
  ${font Segoe UI:size=9}CPU Fan: ${hwmon 2 fan 2} RPM

  ${color black}${font ConkyColors:size=10}g${font}
  ${offset +15}${voffset -30}${font Segoe UI:Bold:size=9}${color black}MEMORY ${hr 2}$color${font}
  ${font Segoe UI:size=9}Use: ${mem}/${memmax}${alignr}Free: ${memeasyfree}
  ${memperc}%${memgraph 10,180 lightgray black -t -l}

  ${color dodgerblue3}${font Font Awesome:size=10}
  ${color dodgerblue3}${offset +18}${voffset -16}${font Segoe UI:Bold:size=9}NETWORK ${hr 2}$color${font}
  ${font Segoe UI:size=9}External IP ${color red}${alignr}${exec curl ipinfo.io/ip}
  ${color}IPv4  ${color red}${alignr}${addr enp4s0}${color}
  ${font Font Awesome:style=Duotone:size=10} ${font Segoe UI:size=9}${color}${downspeedf enp4s0}Kbps${alignr}${downspeedgraph enp4s0 10,120 00fa1d 00fa1d -t -l}
  ${font Font Awesome:style=Duotone:size=10} ${font Segoe UI:size=9}$color${upspeedf enp4s0}Kbps${alignr}${upspeedgraph enp4s0 10,120 fab700 fab700 -t -l}
  
  ${color 12279e}${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:Bold:size=9}${color 12279e}STORAGE ${hr 2}$color${font}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}${exec hddtemp /dev/sda | cut -c11-29}
  ${fs_used}b/${fs_size}b${alignr}${exec hddtemp -n --unit=C /dev/sda}°C
  Read ${diskio_read /dev/sda2}${alignr}${diskiograph_read /dev/sda2 10,120 ffffff ff0000 -t -l}
  Write ${diskio_write /dev/sda2}${alignr}${diskiograph_write /dev/sda2 10,120 ffffff ff0000 -t -l}
  ${fs_used_perc}% ${voffset 1}${fs_bar 7}
  ${voffset -5}${hr 0}
  ${font Font Awesome:size=10}
  ${offset +15}${voffset -16}${font Segoe UI:size=9}${exec hddtemp /dev/sdb1 | cut -c12-22}
  ${fs_used /mnt/Compartilhado}b/${fs_size /mnt/Compartilhado}b${alignr}${exec hddtemp -n --unit=[C] /dev/sdb}°C | ${exec hddtemp -n --unit=[C] /dev/sdc}°C
  Read ${diskio_read /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1}${alignr}${diskiograph_read /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1 10,120 ffffff ff0000 -t -l}
  Write ${diskio_write /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1}${alignr}${diskiograph_write /dev/mapper/ldm_vol_DESKTOP-3M6NSMK-Dg0_Volume1 10,120 ffffff ff0000 -t -l}
  ${fs_used_perc /mnt/Compartilhado}% ${voffset 1}${fs_bar 7 /mnt/Compartilhado}
  ${voffset -5}${hr 0}
  SWAP ${voffset 1}${swapbar 7}
  ${swap}/${swapmax} ${alignr} ${swapperc}%
]]
```
