<!DOCTYPE html>
<html>
<head>
    <title>VOTV Map of All Things</title>
    <style>
        body {
            background-color: #6B8944;
            overflow: hidden;
        }

        #map {
            width: 100vw;
            height: calc(100vh - 40px); /* Adjust to accommodate the coordinates display */
            overflow: hidden;
            position: relative;
        }

            #map img {
                width: 4000px;
                height: 4000px;
                position: absolute;
                top: 0;
                left: 0;
                cursor: move;
            }

        .marker {
            position: absolute;
            width: 45px;
            height: 32px;
            background-image: url('https://drive.google.com/uc?export=view&id=1IBHWXLUKjZz5McbNyX85CBb-UUSL7DCr');
            background-size: cover;
            cursor: pointer;
            pointer-events: auto;
            transform: translate(-50%, -50%);
            transition: transform 0.2s ease-in-out;
        }

            .marker:hover {
                transform: scale(1.2) translate(-50%, -50%);
            }

            .marker span {
                position: absolute;
                top: -50px; /* Adjust the distance between the marker and the title */
                left: 50%;
                transform: translateX(-50%);
                background-color: rgba(0, 0, 0, 0.8);
                color: #fff;
                padding: 4px 8px;
                border-radius: 4px;
                white-space: nowrap;
                font-size: 12px;
                font-weight: bold;
                visibility: hidden;
                opacity: 0;
                transition: visibility 0s, opacity 0.2s ease-in-out;
            }

            .marker.clicked span {
                visibility: visible;
                opacity: 1;
            }

            .marker:before {
                content: "";
                position: absolute;
                bottom: -10px; /* Adjust the position of the arrow */
                left: 50%;
                transform: translateX(-50%);
                border-left: 9px solid transparent;
                border-right: 9px solid transparent;
                border-top: 9px solid rgb(255, 0, 0);
            }

        #coordinates {
            position: fixed;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.8);
            color: #fff;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 14px;
            font-weight: bold;
        }
        #tabContainer {
            position: fixed;
            top: 0;
            right: 0;
            width: 60px;
            height: 100vh;
            background-color: rgba(0, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 999;
        }
        .markerIcon {
            width: 50px;
            height: 50px;
            background-image: url('https://drive.google.com/uc?export=view&id=1IBHWXLUKjZz5McbNyX85CBb-UUSL7DCr');
            background-size: cover;
            border-radius: 50%;
            margin-bottom: 10px;
            cursor: pointer;
            transition: background-color 0.2s ease-in-out;
        }

            .markerIcon:hover {
                background-color: #8AB06B;
            }
        .marker.hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div id="map">
        <img src="https://drive.google.com/uc?export=view&id=1imqBLXGJDMIsnODQhEzGORkaN-Eln-T-" alt="Interactive Map">
        <div class="marker" id="Bmarker" style="top: 1975px; left: 2009px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -14, Y:-10)<br>Located next to base.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2020px; left: 1915px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -63, Y: 12)<br>Located under bridge.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2053px; left: 2065px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 11, Y: 29)<br>Located in between rocks.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 1983px; left: 2016px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -10, Y: -3)<br>Located behind supply box.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2011px; left: 2012px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -14, Y: 6)<br>Located under pipes.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2032px; left: 2012px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -14, Y: 19)<br>Located behind bed.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2032px; left: 2023px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -6, Y: 19)<br>Located on toilet.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2025px; left: 2019px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -7, Y: 13)<br>Located under supply boxes.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 1985px; left: 2020px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -9, Y: -3)<br>Located next to server.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2008px; left: 2025px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -8, Y: 3)<br>Located behind desk.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2016px; left: 2025px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -9, Y: 9)<br>Located behind desk.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2023px; left: 2029px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -4, Y: 16)<br>Located behind wooden palletes.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2031px; left: 2052px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 6, Y: 19)<br>Located behind wooden palletes.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2017px; left: 2048px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 5, Y: 10)<br>Located behind supply boxes.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 823px; left: 2325px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 157, Y: -584)<br>(Requires: Shovel, Metal Detector) Dig in that specific spot.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 852px; left: 722px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -651, Y: -587)<br>Located in the AB Cave entrance.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 1960px; left: 745px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -621, Y: -28)<br>Located behind a desk in The Hole.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2055px; left: 3349px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 639, Y: 44)<br>Next to the Ship Engine.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2412px; left: 1847px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: -100, Y: 203)<br>Located on the side of Juliett Satellite Dish's first level.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 1970px; left: 2119px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 43, Y: -12)<br>Located next to tree.</span>
        </div>
        <div class="marker" id="Bmarker" style="top: 2030px; left: 2047px; " onclick="showInfo('Burger', 'Coordinates', this)">
            <span>Burger:<br>(X: 3, Y: 18)<br>Located on the roof.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 1978px; left: 2038px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: 0, Y: -9)<br>Located on the roof of main base.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 2029px; left: 1900px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: -68, Y: 16)<br>Located on the left side of a bridge near main base.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 1963px; left: 745px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: -620, Y: -28)<br>Located behind desk in The Hole.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 1919px; left: 937px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: -525, Y: -49)<br>Next to a tree base.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 2361px; left: 1131px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: -464, Y: 173)<br>Located in the middle of a field.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 1959px; left: 3051px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: 500, Y: -2)<br>Located behind the top level of the Uniform Satellite Dish.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 3288px; left: 3372px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: 615, Y: 620)<br>Located next to Green Box.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 3369px; left: 1332px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: -372, Y: 702)<br>Located behind desk in Guard Post.</span>
        </div>
        <div class="marker" id="Tmarker" style="top: 137px; left: 3760px; background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk'); width: 60px; height: 60px; " onclick="showInfo('Tile', 'Coordinates', this)">
            <span>Tile:<br>(X: 874, Y: -874)<br>Located on the very corner of the of the playable map, two rivers corner.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 3130px; left: 2515px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: 213, Y: 549)<br>Located offset of the center of the Stonehenge behind one layer of grass.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 2625px; left: 914px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: -569, Y: 302)<br>Located near a skeleton of bones and a radioactive capsule. In the Darkened Bone Pit.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 2089px; left: 1352px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: -343, Y: 38)<br>Located near the Light Pit, it will be found outside the vicinity of the Light Bone Pit behind a couple bushes.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 830px; left: 718px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: -655, Y: -600)<br>Located deep inside the AB Cave towards the cave barrier and on your left.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 2020px; left: 2021px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: -7, Y: 12)<br>Located behind one of the boxes in the Bedroom.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 2056px; left: 3344px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: 637, Y: 44)<br>(Requires: Shovel, Metal Detector) Located underneath the Ship Engine,<br> on the left side of the object you will need to point your shovel into the middle hole and as far center as you can reach.</span>
        </div>
        <div class="marker" id="Smarker" style="top: 1970px; left: 2557px; background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF'); width: 60px; height: 60px; " onclick="showInfo('Skull', 'Coordinates', this)">
            <span>Skull:<br>(X: 261, Y: -6)<br>(Requires: Shovel, Metal Detector) Located near a large boulder you will need to dig around it in order to access a box that has a skull in it.</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1010px; left: 1005px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Romeo<br>(X: -500, Y: -500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1401px; left: 1429px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>November<br>(X: -300, Y: -300)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 994px; left: 2019px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Sierra<br>(X: 0, Y: -500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1001px; left: 2991px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Tango<br>(X: 500, Y: -500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2020px; left: 1009px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Yankee<br>(X: -500, Y: 0)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 3000px; left: 2053px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Whiskey<br>(X: 0, Y: 500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2600px; left: 2673px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Papa<br>(X: 300, Y: 300)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1391px; left: 2613px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Oscar<br>(X: 300, Y: -300)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1970px; left: 3052px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Uniform<br>(X: 500, Y: 0)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 3014px; left: 3106px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Victor<br>(X: 500, Y: 500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2995px; left: 1087px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Xray<br>(X: -500, Y: 500)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2599px; left: 1465px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Quebec<br>(X: -300, Y: 300)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1977px; left: 2425px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Foxtrot<br>(X: 200, Y: 0)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2386px; left: 1849px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Juliett<br>(X: -100, Y: 200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2375px; left: 2037px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>India<br>(X: 0, Y: 200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2386px; left: 2240px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Hotel<br>(X: 100, Y: 200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1593px; left: 1825px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Bravo<br>(X: -100, Y: -200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1593px; left: 2029px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Charlie<br>(X: 0, Y: -200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2183px; left: 2441px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Golf<br>(X: 200, Y: 100)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2010px; left: 1651px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Lima<br>(X: -200, Y: 0)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1800px; left: 1630px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Mike<br>(X: -200, Y: -100)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 2193px; left: 1659px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Kilo<br>(X: -200, Y: 100)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1596px; left: 2226px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Delta<br>(X: 100, Y: -200)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="SDmarker" style="top: 1789px; left: 2430px; background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa'); width: 60px; height: 60px; " onclick="showInfo('SatelliteDish', 'Coordinates', this)">
            <span>Echo<br>(X: 200, Y: -100)<br>Satellite Dish</span>
        </div>
        <div class="marker" id="Amarker" style="top: 1713px; left: 3275px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Red Argemia:<br>(X: 626, Y: -128)<br>Located in the Deep Pit next to Uniform Satellite Dish, near the fence.</span>
        </div>
        <div class="marker" id="Amarker" style="top: 2782px; left: 1458px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Blue Argemia:<br>(X: -315, Y: 398)<br>Located right next to Quebec Satellite Dish, in a river with bumpy beaches.</span>
        </div>
        <div class="marker" id="Amarker" style="top: 3824px; left: 2714px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Green Argemia:<br>(X: 239, Y: 828)<br>Located on the highest point of the map, outside the fence, near Victor Satellite Dish.</span>
        </div>
        <div class="marker" id="Amarker" style="top: 2404px; left: 744px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Cyan Argemia:<br>(X: -630, Y: 190)<br>(Requires: Shovel, Metal Detector) Located on top of a high hill between Quebec and X-ray Satellite Dishes.</span>
        </div>
        <div class="marker" id="Amarker" style="top: 410px; left: 3785px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Purple Argemia:<br>(X: 872, Y: -793)<br>Located above the border corner tile key, on top of a floating white cube that is high up.<br> The only way to access this prop is flying a drone and pushing it off or flying a platform of balloons and grabbing it that way.</span>
        </div>
        <div class="marker" id="Amarker" style="top: 1928px; left: 2114px; background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG'); width: 60px; height: 60px; " onclick="showInfo('Argemia', 'Coordinates', this)">
            <span>Pink Argemia:<br>(X: 34.8, Y: -36.8)<br>Located in a hovering state, it is invisible (until it is touched by a any object or item in the game),<br> to access you need to put a drone at that very exact location and fly straight up and you should be able to hit it. From there it will fall off its hovering state and onto the ground below.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 1959px; left: 753px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: -622, Y: -31)<br>EMF Reader.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 1919px; left: 1800px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: -118, Y: -41)<br>Free Box of LVL 3 Drives.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 1968px; left: 2556px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: 261, Y: -6)<br>Box of Bones.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 1968px; left: 2328px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: 149, Y: -10)<br>Cactis Pet.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 1789px; left: 2973px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: 465, Y: -85)<br>Infinite Growing Basalt Pillars.</span>
        </div>
        <div class="marker" id="DPTmarker" style="top: 2625px; left: 913px; background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL'); width: 60px; height: 130px; " onclick="showInfo('DiggableSpot', 'Coordinates', this)">
            <span>Diggable Spot:<br>(X: -569, Y: 303)<br>Radioative Capsule.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 2056px; left: 3344px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Object', 'Coordinates', this)">
            <span>Ship Engine<br>(X: 637, Y: 44)<br>Object</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 3297px; left: 3373px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Object', 'Coordinates', this)">
            <span>SCP-432<br>(X: 613, Y: 623)<br>Object</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1060px; left: 2872px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Object', 'Coordinates', this)">
            <span>Invisible Boulder<br>(X: 437, Y: -467)<br>Object</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 306px; left: 329px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Erie and Argemia Statues<br>(X: -801, Y: -814)<br>Outside the fence.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 3366px; left: 1341px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Guard Post<br>(X: -373, Y: 703)<br>Outside the fence.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1996px; left: 2045px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Main Base<br>(X: 0, Y: 0)<br>Located in the middle of the entire world.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 2078px; left: 2044px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Bunker<br>(X: 20, Y: 25)<br>Located right beside the Main Base.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1939px; left: 2100px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Lighttower<br>(X: 19, Y: -31)<br>Located right beside the Main Base.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 3118px; left: 2509px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Stonehenge<br>(X: 213, Y: 541)<br>Throw and jump into ATV over the fence to access.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 2104px; left: 1340px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Light Bone Pit<br>(X: -352, Y: 47)<br>Located between the Kilo and Lima Satellite Dishes, simply walk in between them and up.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 2626px; left: 914px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Darkened Bone Pit<br>(X: -569, Y: 303)<br>Near X-ray.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1712px; left: 3274px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Deep Pit<br>(X: 626, Y: -128)<br>Near Uniform Satellite Dish and near the fence.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 841px; left: 720px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>AB Cave (Antibreather Cave)<br>(X: -651, Y: -585)<br>Near Romeo Satellite Dish, on the side of a giant cliff.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 809px; left: 1969px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Ariral Picnic<br>(X: -192, Y: -500)<br>Near Sierra Satellite Dish in a valley. (Event specific).</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 2788px; left: 2834px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Ariral Treehouse<br>(X: 366, Y: 388)<br>Near the Stonehenge Landmark (Event specific).</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1966px; left: 749px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>The Hole<br>(X: -618, Y: -27)<br>Near Yankee Satellite Dish.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1858px; left: 587px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Fence Opening<br>(X: -697, Y: -80)<br>Near The Hole.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 1688px; left: 250px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Secret Staircase<br>(X: 1293, Y: -223)<br>Inaccessible in Storymode,<br> location is outside the barrier.</span>
        </div>
        <div class="marker" id="Lmarker" style="top: 3956px; left: 1562px; background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e'); width: 60px; height: 60px; " onclick="showInfo('Landmark', 'Coordinates', this)">
            <span>Large Bone Pit<br>(X: -265, Y: 1005)<br>Inaccessible in Storymode, location is outside the barrier, near Guard Post.</span>
        </div>
    </div>
    <div id="tabContainer">
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1IBHWXLUKjZz5McbNyX85CBb-UUSL7DCr'); " onclick="toggleMarkerVisibility('Bmarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1WB21bD2Lw0CyFeHQfNlFUrHlLka9HNqk');" onclick="toggleMarkerVisibility('Tmarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1-DmPhZrMvFm1J80a1IgVA4mlGk55hPbF');" onclick="toggleMarkerVisibility('Smarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=15Ltb9bGn6ylg2lWBaZBjmLxIEPXdFCWa');" onclick="toggleMarkerVisibility('SDmarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1C503xOBxqrGzEy7IyrwWFWOfdRYg_8gG');" onclick="toggleMarkerVisibility('Amarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1ym0ry3QxeZQ2tMJpWWEaT-xWTyxWIcZL');" onclick="toggleMarkerVisibility('DPTmarker')"></div>
        <div class="markerIcon" style="background-image: url('https://drive.google.com/uc?export=view&id=1wfnY8kOZsH91EjE5fXUzPUBZR8wf4N6e');" onclick="toggleMarkerVisibility('Lmarker')"></div>
    </div>
    <div id="coordinates">Coordinates:<span id="mouseCoordinates">0, 0</span></div>

    <script>
        function showInfo(title, coordinates, marker) {
            marker.classList.toggle('clicked');
            // Additional code to handle the displayed information if needed
        }
        function toggleMarkerVisibility(markerId) {
            var markers = document.querySelectorAll('.marker[id="' + markerId + '"]');
            markers.forEach(function (marker) {
                marker.classList.toggle('hidden');
            });
        }
        window.addEventListener('DOMContentLoaded', function () {
            var map = document.getElementById('map');
            var image = map.querySelector('img');
            var markers = map.querySelectorAll('.marker');
            var coordinatesElement = document.getElementById('coordinates');

            var isDragging = false;
            var startCoords = { x: 0, y: 0 };
            var startScrollLeft = 0;
            var startScrollTop = 0;
            var minZoomLevel = 0.5; // Minimum zoom level constraint

            map.addEventListener('mousedown', function (e) {
                isDragging = true;
                startCoords.x = e.clientX;
                startCoords.y = e.clientY;
                startScrollLeft = map.scrollLeft;
                startScrollTop = map.scrollTop;
                e.preventDefault();
            });

            map.addEventListener('mouseup', function () {
                isDragging = false;
            });

            map.addEventListener('mousemove', function (e) {
                if (!isDragging) return;
                var dx = e.clientX - startCoords.x;
                var dy = e.clientY - startCoords.y;
                map.scrollLeft = startScrollLeft - dx;
                map.scrollTop = startScrollTop - dy;

                updateCoordinates(e.clientX, e.clientY);
            });
            map.addEventListener('mousemove', function (e) {
                var rect = map.getBoundingClientRect();
                var offsetX = e.clientX - rect.left;
                var offsetY = e.clientY - rect.top;

                var mapWidth = image.clientWidth;
                var mapHeight = image.clientHeight;

                var zoom = mapWidth / image.naturalWidth;

                var mapOffsetX = mapWidth / 2 - map.scrollLeft;
                var mapOffsetY = mapHeight / 2 - map.scrollTop;

                var relativeX = (offsetX - mapOffsetX) / zoom;
                var relativeY = (offsetY - mapOffsetY) / zoom;

                var offsetXCorrection = 37; // Adjust the X offset correction based on your specific map
                var offsetYCorrection = -5; // Adjust the Y offset correction based on your specific map

                var mapX = Math.round(relativeX) - offsetXCorrection;
                var mapY = Math.round(relativeY) - offsetYCorrection;

                coordinatesElement.textContent = '‎‎ ‎ ‎ ‎ ' + 'X: ' + (mapX * 0.437) + ', ' + 'Y: ' + (mapY * 0.437);
            });

            map.addEventListener('mousemove', function (e) {
                updateCoordinates(e.clientX, e.clientY);
            });

            map.addEventListener('wheel', function (e) {
                e.preventDefault();
                var zoom = 2;
                var zoomDelta = -e.deltaY * zoom; // Invert the delta value with a negative sign
                var newWidth = image.clientWidth + zoomDelta;
                var newHeight = image.clientHeight + zoomDelta;
                var offsetX = e.offsetX;
                var offsetY = e.offsetY;

                // Apply the minimum zoom level constraint
                if (newWidth >= map.clientWidth * minZoomLevel && newHeight >= map.clientHeight * minZoomLevel) {
                    var scale = newWidth / image.clientWidth;
                    image.style.width = newWidth + 'px';
                    image.style.height = newHeight + 'px';

                    map.scrollLeft += offsetX * zoomDelta / image.clientWidth;
                    map.scrollTop += offsetY * zoomDelta / image.clientHeight;

                    // Update marker positions
                    markers.forEach(function (marker) {
                        var markerTop = parseFloat(marker.style.top);
                        var markerLeft = parseFloat(marker.style.left);
                        var newMarkerTop = (markerTop * scale) + 'px';
                        var newMarkerLeft = (markerLeft * scale) + 'px';
                        marker.style.top = newMarkerTop;
                        marker.style.left = newMarkerLeft;
                    });
                }
            });
        });
    </script>
</body>
</html>
