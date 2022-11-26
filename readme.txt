DayZ Chernarus NukeTown For Console and PC xml json Mod Instructions & Terms Of Use

Spawns a Call of Duty Inspired POI at 2060.38, 14883.43 which is North East of Tisy Military Base on Chernarus.

Limited Testing on PC Chernarus Local Server DAYZ Version 1.15 Dec 2021.

Created by @scalespeeder. Please report bugs & errors to scalespeeder@gmail.com with screenshots.

If you'd like to edit my NukeTown, simply load "nuketown[project.dze" into DayZ Editor.

Many Thanks To Inclement Dab for his amazing DayZ Editor that makes this all possible: https://steamcommunity.com/sharedfiles/filedetails/?id=2250764298

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml / json files and instructions could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

I always recomend you validate your files at: https://www.xmlvalidation.com/ and https://jsonformatter.curiousconcept.com/

Instructions:

Click the "Code" button and "Download Zip" on the Github Repository and extract the files on your local PC for access.

Ensure your DayZ Server has activated the cfggameplay.json. For console users on Nitrado Servers, go to "General Settings" on your server and tick "Enable cfggameplay.json".

On PC Servers add the following line to your serverDZ.cfg:

enableCfgGameplayFile = 1;

(On some PC servers, including Nitrado, the serverDZ.cfg is "hidden", so you need to enable "expert mode" in settings,
then go to "expert settings", which is the serverDZ.cfg. Stop the server before making changes this way.)

Upload "nuketownstructures.json" & "nukeweapons.json" from the extracted files to inside the "custom" folder of the mission directory on your server. This file places the structures on your map.
(If you haven't got a "custom" folder, create one.)

Open the cfggameplay.json file in the correct mission file for your server and look for the "objectSpawnersArr" line.

This file tells your server to access your custom file.

Edit it to look like this: 

	"objectSpawnersArr": ["custom/nuketownstructures.json"],
	
THIS WILL SPAWN IN THE NUKETOWN BUILDINGS, BUT NOT THE WEAPONS WHEN YOU RESTART THE SERVER.

If you want the weapons too, edit it to look like this:

	"objectSpawnersArr": ["custom/nuketownstructures.json","custom/nukeweapons.json"],
	
WARNING: THIS IS NOT THE IDEAL WAY TO SPAWN WEAPONS, AND WILL CAUSE DUPLICATION ISSUES. WHEN YOUR NUKETOWN EVENT IS
OVER, REMOVE "custom/nukeweapons.json" FROM THE "objectSpawnersArr" LINE, AND THE WEAPONS WILL START TO DESPAWN.
	
If you already are calling custom jsons to spawn items, seperate the files like this:

	"objectSpawnersArr": ["custom/nuketownstructures.json","custom/nukeweapons.json","custom/differentfile.json"],
	
Save your changes & upload if you need to.

If you want to have all players spawn back at the NukeTown area when they die, upload the cfgplayerspawnpoints.xml file to the root directory of
your mission file, over the top of the original one. (Make a back-up of the original so you can revert after your Nuketown event is over.)
	
Next we add loot to the structures by adding the following code snippet to the top of your mapgrouppos.xml file, after <map> 

	<!--Nuke Town Loot-->
	<group name="Land_Wreck_Ikarus" pos="2073.479980 438.139008 14895.500000" rpy="0.000000 0.000000 127.111961" a="-37.112"/>
	<group name="Land_wreck_truck01_aban2_green" pos="2076.899902 436.359009 14886.299805" rpy="-7.899989 0.100000 -45.559391" a="135.559"/>
	<group name="Land_Wreck_hb02_aban1_red" pos="2083.370117 436.993988 14884.700195" rpy="0.000000 0.000000 121.605995" a="-31.606"/>
	<group name="Land_Wreck_Lada_Green" pos="2064.760010 437.618988 14899.400391" rpy="0.000000 0.000000 -78.404480" a="168.404"/>
	<group name="Land_Village_Pub" pos="2088.889893 441.725006 14901.599609" rpy="0.000000 0.000000 38.257492" a="51.7425"/>
	<group name="Land_Misc_Greenhouse" pos="2092.156006 441.254120 14924.875000" rpy="-0.000000 -0.000000 -45.939770" a="135.94"/>
	<group name="Land_Misc_Well_Pump_Blue" pos="2085.312988 437.395935 14893.489258" rpy="0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Shed_M3" pos="2105.148682 440.948395 14914.761719" rpy="-0.000000 -0.000000 133.686813" a="-43.6868"/>
	<group name="Land_Lunapark_Carousel_Small" pos="2095.291992 441.331635 14914.528320" rpy="0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Village_Pub" pos="2061.669922 439.760010 14883.299805" rpy="0.000000 0.000000 -139.897995" a="-130.102"/>
	<group name="Land_Shed_W6" pos="2076.267578 439.101624 14909.779297" rpy="-0.000000 -0.000000 41.424141" a="48.5759"/>
	<group name="Land_Shed_W5" pos="2073.379883 437.281006 14879.700195" rpy="3.600000 0.000000 129.475998" a="-39.476"/>
	<group name="Land_Misc_Polytunnel" pos="2060.030029 435.654999 14861.299805" rpy="0.000000 0.000000 129.999985" a="-40"/>
	<group name="Land_misc_chickenCoop" pos="2050.169678 435.656372 14866.641602" rpy="0.000000 0.000000 -136.439804" a="-133.56"/>
	<group name="Land_Shed_M1" pos="2043.606323 436.062866 14874.397461" rpy="-0.000000 -0.000000 -50.977531" a="140.978"/>
	<group name="Land_Farm_WaterTower_Small" pos="2093.070068 441.553986 14890.799805" rpy="0.000000 -0.100000 39.999996" a="50"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2049.209961 435.334015 14845.700195" rpy="-3.345260 2.212079 -65.241203" a="155.241"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2038.880005 435.950989 14853.099609" rpy="-1.500000 1.000000 -47.993992" a="137.994"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2031.079956 436.487000 14861.400391" rpy="-1.999999 0.000000 -37.946983" a="127.947"/>
	<group name="Land_misc_chickenCoop" pos="2052.434570 435.408783 14864.539063" rpy="0.000000 0.000000 -136.439804" a="-133.56"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2100.723877 443.760071 14941.313477" rpy="5.140065 0.700029 112.156815" a="-22.1568"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2108.030518 443.578125 14935.016602" rpy="5.203377 -0.623407 129.403793" a="-39.4038"/>
	<group name="Land_Mil_Tent_Big2_1" pos="2115.263184 443.401947 14928.173828" rpy="5.285093 -1.482205 139.450699" a="-49.4507"/>
	<group name="Land_Shed_W1" pos="2057.917236 438.033722 14891.347656" rpy="-0.000000 -0.000000 133.112381" a="-43.1124"/>
	<group name="Land_Misc_Toilet_Dry" pos="2047.979980 436.743011 14879.599609" rpy="0.000000 0.000000 -51.266201" a="141.266"/>
	<group name="Land_Misc_Toilet_Dry" pos="2049.419922 436.876007 14881.299805" rpy="0.000000 0.000000 -50.672298" a="140.672"/>
	<group name="Land_Misc_Toilet_Dry" pos="2104.157715 440.615051 14908.872070" rpy="-0.000000 -0.000000 129.057693" a="-39.0577"/>
	<group name="Land_Misc_Toilet_Dry" pos="2102.712891 440.724945 14907.242188" rpy="-0.000000 -0.000000 129.651566" a="-39.6516"/>
	<group name="Land_Mil_Tent_Big3" pos="2113.030029 437.997009 14874.900391" rpy="-4.999997 0.000000 -52.911594" a="142.912"/>
	<group name="Land_Mil_Tent_Big1_1" pos="2095.610107 435.282990 14861.099609" rpy="0.000000 -7.099997 -141.423996" a="-128.576"/>
	<group name="Land_Mil_Tent_Big1_1" pos="2106.030029 435.437988 14856.200195" rpy="0.000000 -7.500000 -153.712982" a="-116.287"/>
	<group name="Land_wreck_truck01_aban1_orange" pos="2117.692871 436.374359 14858.280273" rpy="-0.000000 -0.000000 0.000000" a="90"/>
	<group name="Land_wreck_truck01_aban2_orange" pos="2122.800049 436.444000 14855.799805" rpy="0.000000 2.499999 0.000000" a="90"/>
	<group name="Land_Misc_DeerStand1" pos="2053.742920 440.336975 14902.798828" rpy="-0.000000 -0.000000 -59.687580" a="149.688"/>
	<group name="Land_Misc_DeerStand1" pos="2096.563721 439.172821 14879.736328" rpy="-0.000000 -0.000000 130.313980" a="-40.314"/>
	<group name="Land_Wreck_Volha_Police" pos="2102.670898 447.273224 15001.833984" rpy="-2.137850 0.762746 0.000000" a="90"/>
	<group name="Land_Wreck_Volha_Police" pos="2106.089600 447.214752 14999.498047" rpy="-0.000000 -0.000000 -97.455978" a="-172.544"/>
	<group name="Land_BusStop_Village2" pos="2065.469971 438.184998 14905.599609" rpy="0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_BusStop_City" pos="2080.111084 436.951904 14878.173828" rpy="0.000000 0.000000 -173.770157" a="-96.2298"/>
	
Save your changes & upload if you need to.

Restart your server and the new structures will appear immediatly, and then they will slowly stock with loot.

Thanks, Rob.
