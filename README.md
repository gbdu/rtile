Ruby script for manual tiling and window placement.

fork of rtile 

![Demo](http://i.imgur.com/4VgLJBn.gif)


```
<?xml version="1.0" encoding="UTF-8"?>
<?xml version="1.0" encoding="UTF-8"?>
<settings>
	<gaps top="34" bottom="5" left="22" right="22" windows_x="10" windows_y="5"/>
	<columns max_size_main="2" max_size="4" max_count="2"/>

	<!--<workspace id="<id>" median="0.5" reverse_x="true|false" reverse_y="true|false"/>-->

	<workspace id="0" median="0.50"/>
	<workspace id="1" median="0.50"/>
	<workspace id="2"/>
	<workspace id="3" median="0.6"/>
	<workspace id="4" reverse_x="true" median="0.4"/>

	<window class="mpv" floating="true"/>
	<window class="steam" floating="true"/>
	<window class="firefox" priority="high"/>
	<window class="geany" priority="high" fake_windows="2"/>
	<window class="nemo" fake_windows="3"/>
	<window class="transmission-gtk" priority="low" fake_windows="3"/>
	<window class="terminator" priority="low" fake_windows="3"/>



	<column_config id="1" windows="1" column_sizes="1"/>
	<column_config id="1" windows="2" column_sizes="1, 1"/>
	<column_config id="1" windows="3" column_sizes="1, 2"/>
	<column_config id="1" windows="4" column_sizes="1, 3"/>
	<column_config id="1" windows="5" column_sizes="1, 4"/>
	<column_config id="1" windows="6" column_sizes="1, 2, 3"/>
	<column_config id="1" windows="7" column_sizes="1, 2, 4"/>
	<column_config id="1" windows="8" column_sizes="1, 3, 3"/>
	<column_config id="1" windows="9" column_sizes="1, 4, 4"/>
	<column_config id="1" windows="10" column_sizes="1, 4, 4, 1"/>
	<column_config id="1" windows="11" column_sizes="1, 4, 4, 2"/>

	<column_config id="2" windows="1" column_sizes="1"/>
	<column_config id="2" windows="2" column_sizes="1, 1"/>
	<column_config id="2" windows="3" column_sizes="2, 1"/>
	<column_config id="2" windows="4" column_sizes="2, 2"/>
	<column_config id="2" windows="5" column_sizes="2, 3"/>
	<column_config id="2" windows="6" column_sizes="2, 3"/>
	<column_config id="2" windows="7" column_sizes="1, 6"/>

	<column_config id="3" windows="1" column_sizes="1"/>
	<column_config id="3" windows="2" column_sizes="1, 1"/>
	<column_config id="3" windows="3" column_sizes="1, 1, 1"/>
	<column_config id="3" windows="4" column_sizes="1, 1, 2"/>
	<column_config id="3" windows="5" column_sizes="1, 2, 2"/>
	<column_config id="3" windows="6" column_sizes="2, 2, 2"/>
	<column_config id="3" windows="7" column_sizes="1, 3, 3"/>
	<column_config id="3" windows="8" column_sizes="1, 3, 3"/>
	<column_config id="3" windows="9" column_sizes="3, 3, 3"/>

	<column_config id="4" windows="1" column_sizes="1"/>
	<column_config id="4" windows="2" column_sizes="1, 1"/>
	<column_config id="4" windows="3" column_sizes="1, 1, 1"/>
	<column_config id="4" windows="4" column_sizes="1, 1, 2"/>
	<column_config id="4" windows="5" column_sizes="1, 2, 2"/>
	<column_config id="4" windows="6" column_sizes="2, 2, 2"/>
	<column_config id="4" windows="7" column_sizes="2, 3, 2"/>
	<column_config id="4" windows="8" column_sizes="2, 4, 2"/>
	<column_config id="4" windows="9" column_sizes="4, 1, 4"/>


</settings>

```


#Example mouse and keybindings for Openbox using the keypad

```

	<!-- rtile.rb section -->

			<mousebind action="Press" button="W-Left">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --swap</command>
				</action>
			</mousebind>

			<mousebind action="Press" button="W-Right">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --binary</command>
				</action>
			</mousebind>

			<mousebind action="Click" button="W-Down">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --grow-down</command>
				</action>
			</mousebind>

			<mousebind action="Click" button="W-Up">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --grow-up</command>
				</action>
			</mousebind>

			<mousebind action="Click" button="W-S-Up">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --grow-right</command>
				</action>
			</mousebind>

			<mousebind action="Click" button="W-S-Down">
				<action name="Focus"/>
				<action name="Raise"/>
				<action name="Execute">
					<command>/home/garg/scripts/rtile.rb --grow-left</command>
				</action>
			</mousebind>

	<keyboard>
		<chainQuitKey>C-g</chainQuitKey>
		<!-- Keybindings for desktop switching -->

		<keybind key="W-A">
			<action name="Execute">
				<command>~/scripts/rtile.rb --all</command>
			</action>
		</keybind>

		<keybind key="C-W-KP_8">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --split-up</command>
			</action>
		</keybind>

		<keybind key="C-W-KP_2">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --split-down</command>
			</action>
		</keybind>
		<keybind key="C-W-KP_4">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --split-left</command>
			</action>
		</keybind>
		<keybind key="C-W-KP_6">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --split-right</command>
			</action>
		</keybind>

		<keybind key="W-1">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --all --id=1</command>
			</action>
		</keybind>

		
		<keybind key="W-2">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --all --id=2</command>
			</action>
		</keybind>

		
		<keybind key="W-3">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --all --id=3</command>
			</action>
		</keybind>

		
		<keybind key="W-4">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --all --id=4</command>
			</action>
		</keybind>

		
		<keybind key="C-W-KP_5">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --next-monitor</command>
			</action>
		</keybind>

		<keybind key="S-W-KP_8">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --grow-up</command>
			</action>
		</keybind>
		<keybind key="S-W-KP_2">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --grow-down</command>
			</action>
		</keybind>
		<keybind key="S-W-KP_4">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --grow-left</command>
			</action>
		</keybind>
		<keybind key="S-W-KP_6">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --grow-right</command>
			</action>
		</keybind>
		<keybind key="S-W-KP_0">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --cycle</command>
			</action>
		</keybind>
		<keybind key="S-W-KP_5">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --cycle-monitors</command>
			</action>
		</keybind>

		<keybind key="W-KP_8">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb t</command>
			</action>
		</keybind>
		<keybind key="W-KP_5">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb</command>
			</action>
		</keybind>
		<keybind key="W-KP_2">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb b</command>
			</action>
		</keybind>
		<keybind key="W-KP_7">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb tl</command>
			</action>
		</keybind>
		<keybind key="W-KP_4">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb l</command>
			</action>
		</keybind>
		<keybind key="W-KP_1">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb bl</command>
			</action>
		</keybind>
		<keybind key="W-KP_9">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb tr</command>
			</action>
		</keybind>
		<keybind key="W-KP_6">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb r</command>
			</action>
		</keybind>
		<keybind key="W-KP_3">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb br</command>
			</action>
		</keybind>
		<keybind key="W-KP_0">
			<action name="Execute">
				<command>/home/garg/scripts/rtile.rb --binary</command>
			</action>
		</keybind>

```
