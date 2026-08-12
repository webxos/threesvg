<svg viewBox="0 0 1920 1080" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" style="background-color: #000000; width: 100%; height: 100%; display: block; margin: auto;">
    <defs>
        <!-- 1-Bit Dithering & Threshold Filters -->
        <filter id="ditherBackground" x="0" y="0" width="100%" height="100%">
            <feTurbulence type="fractalNoise" baseFrequency="0.015" numOctaves="3" result="noise" seed="1">
                <animate attributeName="baseFrequency" values="0.015; 0.025; 0.015" dur="20s" repeatCount="indefinite"/>
            </feTurbulence>
            <feColorMatrix type="matrix" values="0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  20 0 0 0 -8">
                <animate attributeName="values" values="0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  20 0 0 0 -3; 0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  20 0 0 0 -12; 0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  20 0 0 0 -3" dur="15s" repeatCount="indefinite"/>
            </feColorMatrix>
        </filter>

        <!-- 1-bit Point Cloud Generator (Cubist Texture & Grime) -->
        <filter id="cubistTexture" x="-10%" y="-10%" width="120%" height="120%">
            <feTurbulence type="fractalNoise" baseFrequency="0.2" numOctaves="2" result="noise" seed="3"/>
            <feColorMatrix in="noise" type="matrix" values="0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  4 0 0 0 -1.6" result="threshold"/>
            <feComposite in="SourceGraphic" in2="threshold" operator="in"/>
        </filter>

        <filter id="crispText">
            <feComponentTransfer>
                <feFuncR type="discrete" tableValues="0 1"/>
                <feFuncG type="discrete" tableValues="0 1"/>
                <feFuncB type="discrete" tableValues="0 1"/>
            </feComponentTransfer>
        </filter>

        <!-- Ink-Bleed Transition Filter -->
        <filter id="inkBleedFilter">
            <feTurbulence type="fractalNoise" baseFrequency="0.015" numOctaves="3" result="noise" seed="2"/>
            <feDisplacementMap in="SourceGraphic" in2="noise" scale="80" xChannelSelector="R" yChannelSelector="G"/>
        </filter>

        <!-- Picasso-Style Cubist Patterns -->
        <pattern id="cubistHatch" width="12" height="12" patternUnits="userSpaceOnUse">
            <rect width="12" height="12" fill="#000000"/>
            <line x1="0" y1="12" x2="12" y2="0" stroke="#FFFFFF" stroke-width="2"/>
            <line x1="0" y1="6" x2="6" y2="12" stroke="#FFFFFF" stroke-width="2"/>
        </pattern>
        <pattern id="cubistWeave" width="10" height="10" patternUnits="userSpaceOnUse">
            <rect width="10" height="10" fill="#000000"/>
            <line x1="0" y1="0" x2="10" y2="0" stroke="#FFFFFF" stroke-width="2"/>
            <line x1="0" y1="5" x2="10" y2="5" stroke="#FFFFFF" stroke-width="2"/>
        </pattern>
        <pattern id="labyrinth" width="80" height="80" patternUnits="userSpaceOnUse">
            <rect width="80" height="80" fill="#000000"/>
            <path d="M10,10 L70,10 L70,70 L40,70 L40,30 L10,30 Z" fill="none" stroke="#FFFFFF" stroke-width="4"/>
            <path d="M10,50 L20,50 L20,60 L10,60" fill="none" stroke="#FFFFFF" stroke-width="4"/>
        </pattern>

        <!-- Storybook Page Transition Masks -->
        <mask id="inkBleed1">
            <rect width="100%" height="100%" fill="black"/>
            <circle cx="960" cy="540" r="0" fill="white" filter="url(#inkBleedFilter)">
                <animate attributeName="r" values="0; 1600; 1600; 0; 0" keyTimes="0; 0.05; 0.30; 0.33; 1" dur="45s" repeatCount="indefinite"/>
            </circle>
        </mask>
        
        <mask id="inkBleed2">
            <rect width="100%" height="100%" fill="black"/>
            <circle cx="960" cy="540" r="0" fill="white" filter="url(#inkBleedFilter)">
                <animate attributeName="r" values="0; 0; 1600; 1600; 0; 0" keyTimes="0; 0.33; 0.38; 0.63; 0.66; 1" dur="45s" repeatCount="indefinite"/>
            </circle>
        </mask>

        <mask id="inkBleed3">
            <rect width="100%" height="100%" fill="black"/>
            <circle cx="960" cy="540" r="0" fill="white" filter="url(#inkBleedFilter)">
                <animate attributeName="r" values="0; 0; 1600; 1600; 0" keyTimes="0; 0.66; 0.71; 0.96; 1" dur="45s" repeatCount="indefinite"/>
            </circle>
        </mask>
    </defs>

    <!-- Base Black Void -->
    <rect width="1920" height="1080" fill="#000000"/>

    <!-- ========================================== -->
    <!-- SCENE 1: The Fragmented Muse (0s - 15s)    -->
    <!-- ========================================== -->
    <g id="scene1" mask="url(#inkBleed1)">
        <!-- Shifting Abstract Background -->
        <rect x="0" y="0" width="1920" height="1080" fill="#FFFFFF" filter="url(#ditherBackground)"/>

        <!-- Cubist Architectural Planes -->
        <polygon points="0,1080 0,400 600,800 800,1080" fill="#000000"/>
        <polygon points="1920,1080 1920,300 1400,700 1200,1080" fill="url(#cubistHatch)"/>
        <polygon points="0,0 0,400 500,200 800,0" fill="url(#cubistWeave)"/>

        <!-- The Cubist Face (Frontal & Profile merged) -->
        <g transform="translate(960, 500)">
            <!-- Left Half (Frontal) -->
            <path d="M0,-200 L150,-100 L200,150 L50,300 L0,150 Z" fill="#FFFFFF" stroke="#000000" stroke-width="8"/>
            <!-- Right Half (Profile) -->
            <path d="M0,-200 L-100,-150 L-250,0 L-200,200 L0,150 Z" fill="#000000" stroke="#FFFFFF" stroke-width="8"/>
            
            <!-- Disjointed Facial Features -->
            <!-- Left Eye (Geometric) -->
            <polygon points="50,0 100,-20 120,40 70,60" fill="#000000"/>
            <polygon points="60,10 90,0 100,30 70,50" fill="#FFFFFF"/>
            <!-- Right Eye (Fragmented) -->
            <circle cx="-120" cy="-20" r="30" fill="#FFFFFF"/>
            <circle cx="-115" cy="-15" r="10" fill="#000000"/>
            
            <!-- Nose (Sharp Angle) -->
            <polygon points="0,0 -50,150 20,100" fill="#FFFFFF" stroke="#000000" stroke-width="6"/>
            
            <!-- Mouth (Intersecting Shapes) -->
            <path d="M-20,220 L80,200 L40,280 Z" fill="#FFFFFF"/>
            <path d="M-20,220 L-80,180 L-40,280 Z" fill="#000000"/>

            <!-- Subtle evolution: sliding the profile slightly -->
            <animateTransform attributeName="transform" type="translate" values="960, 500; 980, 480; 960, 500" dur="12s" repeatCount="indefinite"/>
        </g>

        <!-- Interlocking Guitar Elements -->
        <circle cx="960" cy="900" r="180" fill="none" stroke="#000000" stroke-width="12"/>
        <circle cx="960" cy="900" r="120" fill="#000000"/>
        <rect x="940" y="600" width="40" height="250" fill="#000000"/>
        <polygon points="900,600 1020,600 960,500" fill="url(#cubistHatch)"/>

        <!-- Camera Pan -->
        <animateTransform attributeName="transform" type="translate" values="-50, 0; 50, 0; -50, 0" keyTimes="0; 0.5; 0" dur="45s" repeatCount="indefinite"/>
    </g>

    <!-- ========================================== -->
    <!-- SCENE 2: The Shattered Still Life (15s - 30s) -->
    <!-- ========================================== -->
    <g id="scene2" mask="url(#inkBleed2)">
        <!-- Background -->
        <rect x="0" y="0" width="1920" height="1080" fill="#000000"/>
        
        <!-- Cubist Table & Background Planes -->
        <polygon points="0,1080 1920,1080 1920,600 0,800" fill="#FFFFFF"/>
        <polygon points="0,800 800,400 1200,600 1920,500 1920,800" fill="url(#cubistWeave)"/>
        <polygon points="0,0 1920,0 1920,500 0,800" fill="#000000" filter="url(#cubistTexture)"/>

        <!-- Shattered Guitar Fragments floating in space -->
        <g>
            <!-- Body Fragment 1 -->
            <path d="M600,500 L800,450 L850,650 L650,700 Z" fill="#FFFFFF" stroke="#000000" stroke-width="8">
                <animateTransform attributeName="transform" type="rotate" values="0 725 575; 15 725 575; 0 725 575" dur="10s" repeatCount="indefinite"/>
            </path>
            <!-- Body Fragment 2 -->
            <path d="M850,650 L1050,600 L1100,800 L900,850 Z" fill="url(#cubistHatch)" stroke="#FFFFFF" stroke-width="8">
                <animateTransform attributeName="transform" type="rotate" values="0 975 725; -10 975 725; 0 975 725" dur="12s" repeatCount="indefinite"/>
            </path>
            <!-- Neck Fragment -->
            <rect x="1100" y="300" width="60" height="300" fill="#000000" stroke="#FFFFFF" stroke-width="6" transform="rotate(25 1130 450)"/>
            <!-- Soundhole (Relocated) -->
            <circle cx="1300" cy="700" r="80" fill="#FFFFFF"/>
            <circle cx="1300" cy="700" r="40" fill="#000000"/>

            <!-- Strings (Tension lines) -->
            <line x1="600" y1="500" x2="1300" y2="700" stroke="#FFFFFF" stroke-width="3"/>
            <line x1="800" y1="450" x2="1100" y2="300" stroke="#FFFFFF" stroke-width="3"/>
            <line x1="1100" y1="300" x2="1300" y2="700" stroke="#000000" stroke-width="3"/>
        </g>

        <!-- Point Cloud Dust / Texture -->
        <g fill="#FFFFFF" filter="url(#cubistTexture)">
            <rect x="0" y="0" width="1920" height="1080" opacity="0.2"/>
        </g>

        <!-- Camera Pan -->
        <animateTransform attributeName="transform" type="translate" values="50, -50; -50, 50; 50, -50" keyTimes="0; 0.5; 0" dur="45s" repeatCount="indefinite"/>
    </g>

    <!-- ========================================== -->
    <!-- SCENE 3: The Watcher's Minotaur (30s - 45s) -->
    <!-- ========================================== -->
    <g id="scene3" mask="url(#inkBleed3)">
        <!-- Background -->
        <rect x="0" y="0" width="1920" height="1080" fill="#000000"/>
        
        <!-- Labyrinth Background Pattern -->
        <rect x="0" y="0" width="1920" height="1080" fill="url(#labyrinth)" opacity="0.3"/>
        <rect x="0" y="0" width="1920" height="1080" fill="#000000" filter="url(#ditherBackground)" opacity="0.8"/>

        <!-- The Minotaur (Heavy, Blocky, Imposing) -->
        <g transform="translate(960, 540)">
            <!-- Massive Shoulders/Body -->
            <polygon points="-400,400 -300,0 -100,-100 100,-100 300,0 400,400" fill="#FFFFFF" stroke="#000000" stroke-width="12"/>
            <polygon points="-400,400 -300,0 -100,-100 100,-100 300,0 400,400" fill="url(#cubistHatch)" opacity="0.5"/>
            
            <!-- Neck -->
            <polygon points="-100,-100 100,-100 50,-250 -50,-250" fill="#000000"/>

            <!-- Head (Half Bull, Half Human Structure) -->
            <path d="M-200,-250 L200,-250 L250,-450 L100,-550 L-100,-550 L-250,-450 Z" fill="#000000" stroke="#FFFFFF" stroke-width="12"/>
            
            <!-- Left Horn -->
            <polygon points="-200,-450 -350,-600 -150,-500" fill="#FFFFFF"/>
            <!-- Right Horn -->
            <polygon points="200,-450 350,-600 150,-500" fill="#FFFFFF"/>

            <!-- Left Eye (Piercing Human) -->
            <polygon points="-150,-400 -50,-400 -100,-350" fill="#FFFFFF"/>
            <circle cx="-100" cy="-375" r="10" fill="#000000"/>
            
            <!-- Right Eye (Bull) -->
            <polygon points="50,-400 150,-400 100,-350" fill="url(#cubistWeave)"/>
            
            <!-- Snout / Nose -->
            <polygon points="-100,-350 100,-350 50,-200 -50,-200" fill="#FFFFFF" stroke="#000000" stroke-width="8"/>
            <rect x="-30" y="-300" width="60" height="20" fill="#000000"/>

            <!-- Nostril Flare Animation -->
            <animateTransform attributeName="transform" type="scale" values="1; 1.05; 1" dur="4s" repeatCount="indefinite" additive="sum"/>
            <animateTransform attributeName="transform" type="translate" values="960, 540" additive="sum"/>
        </g>

        <!-- Foreground Architectural Blocks -->
        <polygon points="0,1080 300,800 400,1080" fill="#000000" stroke="#FFFFFF" stroke-width="4"/>
        <polygon points="1920,1080 1620,800 1520,1080" fill="url(#cubistHatch)"/>

        <!-- Camera Zoom -->
        <animateTransform attributeName="transform" type="scale" values="1; 1.1; 1" keyTimes="0; 0.5; 0" dur="45s" repeatCount="indefinite"/>
    </g>

    <!-- ========================================== -->
    <!-- CAPTIONS / STORYBOOK TEXT                  -->
    <!-- ========================================== -->
    <g font-family="Georgia, serif" text-anchor="middle" filter="url(#crispText)" font-weight="bold" font-style="italic">
        <!-- Scene 1 Caption -->
        <text x="960" y="1000" font-size="38" fill="#FFFFFF" letter-spacing="4">
            I. THE FRAGMENTED MUSE
            &lt;animate attributeName="opacity" values="0; 1; 1; 0; 0" keyTimes="0; 0.05; 0.3; 0.33; 1" dur="45s" repeatCount="indefinite"/&gt;
        </text>

        <!-- Scene 2 Caption -->
        <text x="960" y="1000" font-size="38" fill="#FFFFFF" letter-spacing="4">
            II. THE SHATTERED STILL LIFE
            &lt;animate attributeName="opacity" values="0; 0; 1; 1; 0; 0" keyTimes="0; 0.33; 0.38; 0.63; 0.66; 1" dur="45s" repeatCount="indefinite"/&gt;
        </text>

        <!-- Scene 3 Caption -->
        <text x="960" y="1000" font-size="38" fill="#FFFFFF" letter-spacing="4">
            III. THE MINOTAUR'S GAZE
            &lt;animate attributeName="opacity" values="0; 0; 1; 1; 0" keyTimes="0; 0.66; 0.71; 0.96; 1" dur="45s" repeatCount="indefinite"/&gt;
        </text>
    </g>
</svg>
