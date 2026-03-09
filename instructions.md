LEKTION 1 - Intro / Setup
(billeder+cheat-sheet under '1 - intro')

	1	Installering af GoDot 4.3 (Download fra GoDot Hjemmeside)
	2	Introduktion til GoDot Engine (bÃ¸rn lukker computere!);
	3	SÃ¦t dit fÃ¸rste spil op; sÃ¥dan opretter du et nyt spil.
	4	GÃ¥ til 2D mode og snak om viewport (i.e. rendering surface) + koordinatsystem.
	5	Uddeling af 'Assets' folder samt flytte den ind i projektet.
	6	Hvad er Nodes?
	7	Hvad er en Scene?
	8	Uddel Cheat-sheets (de fÃ¥r dem kun 1 gang.... sÃ¥ det er eget tab hvis de mister dem!)
	9	Lav Game-scene :D
	10	KÃ¸r "spillet".

Detaljeret Forklaring
	1	Download og unzip
	1	HjÃ¦lp bÃ¸rnene med at komme ind pÃ¥ hjemmesiden; hjÃ¦lp dem med at udpakke / unzip et sted hvor det giver mening (i 'dokumenter' eller pÃ¥ 'skrivebordet'). Lav en NY FOLDER, hvor du lÃ¦gger .exe filerne hen (brug ogsÃ¥ denne til spillene!)
	2	Vis fÃ¦rdig version (2025 spring)
	1	Vis bÃ¸rnene rundt i programmet; Demo fÃ¸rste spil vi skal lave (fÃ¦rdig version); 
	1	[2D view] vs [Script view] (tscn vs gd)
	2	Hvad er 
	1	Scene
	1	Noder i trÃ¦struktur
	2	Enhed som kan genbruges 
	3	Kan vÃ¦re
	•	Karakter
	•	Bane
	•	menu screen
	•	Projektil
	•	UI element
	2	Scene struktur (trÃ¦) (rod’en og bÃ¸rn)

	1	Roden (Paddle)
	1	Engenskab for hele scene 
	2	The top-level node is the root node and controls the entire scene. Child nodes inherit properties from their parents.

	3	FileSystem (res:// godot stifinder/mapper)
	4	Inspector
	3	Setup projekt
	1	Vi starter med at Ã¥bne GoDot Engine (uden 'console'); 'create' -> Navn 'Gem Catcher' -> Browse for folder -> sÃ¸rg for at 'create folder' er tjekket af (skal vÃ¦re en tom folder) -> VÃ¦lg 'Mobile' mode. ('Compatibility' mode hvis bÃ¸rnene har problemer med grafik kort/fÃ¥r advarsler).

	4	Spil box
	1	Snak om den lilla boks der definerer hvad vi kan se nÃ¥r vi starter spillet (alt uden for boksen vil ikke vÃ¦re pÃ¥ skÃ¦rmen!). Snak om x- og y-aksen (og specifikt at y-aksen vokser nedad og x-aksen vokser mod hÃ¸jre), hvor er (0,0)?
	5	Del assets
	1	Del assets ud og bed dem om at flytte en kopi af hele mappen ind i deres spil-mappe :)
	6	Noder
	1	(1) Noder er de mest essentielle byggesten i GoDot Engine; En Node er 1 enhed. En node indeholder 2 ting; 
	1	funktioner som GÃ˜R noget og 
	2	attributter som ER noget. (2) 
	2	Udviklerne hos GoDot har vÃ¦ret sÃ¥ sÃ¸de at lave en masse Noder som kan en masse af de ting vi har brug for, sÃ¥ vi behÃ¸ver ikke sidde og lave det hele fra bunden, men kan bygge videre ved hjÃ¦lp af deres byggesten. (EVT LEGO REFERENCE - I stedet for at bruge en masse smÃ¥ ensformige brikker, sÃ¥ kan vi bruge trekanter, stÃ¸rre klodser og andre former, som er lavet for os i forvejen.)
	7	Scener
	1	Scener er lavet af en rÃ¦kke noder i en trÃ¦struktur. Der er prÃ¦cis 1 'root'-node, og derefter er der bÃ¸rn og bÃ¸rnebÃ¸rn osv. som hver bliver brugt til forskellige ting. 
	2	Vi kan ogsÃ¥ bruge scener inden i andre scener, ligesom vi bruger Noder.
	8	Cheat-sheets - vises

	9	tilfÃ¸j 'Node2D' som root og kald den 'Game' 
	1	gem i res://scenes/ 
	2	TilfÃ¸j en 'Sprite2D' Node til at vise baggrunden som BARN til 'Game'.
	3	Ã…bn 'assets' folderen i FileSystem og hiv 'GameBg.png' ind i 'Texture' attributten.
	4	SÃ¦t 'scale' til 0.7 
	5	flyt Sprite2D sÃ¥ den dÃ¦kker viewport (under 'Transform'). -> Ctrl+S
	6	
	7	Alt er object (ikke primitive typer: int, float, boolean, string
	8	Alt er noder (ikke resourser: billeder, musik) noder findes i den virkelig verden mens resourcer kan indgÃ¥ i en node
	9	Hvilken class skal man vÃ¦lge? Den class som matcher formÃ¥let bedst.
	10	

	10	KÃ¸r spillet 
	1	"Run Project" -> i pop-up vÃ¦lg "select current" som 'main scene' (i.e. det her er scenen som altid starter nÃ¥r vi kÃ¸rer spillet som helhed) 
	2	man kan Ã¦ndre denne indstilling (Project -> Project Settings -> Application -> Run -> Main Scene)

LEKTION 2 - Paddle & Gem
(billeder & Kode under '2 - paddle & gem')

	1	TilfÃ¸j Paddle (Adrea2d)
	1	Lav en ny scene med en 'Area2D' Node som root, sÃ¦t navnet til 'Paddle' og gem.
	2	TilfÃ¸j Sprite2D' 
	1	som barn til Paddle, og sÃ¦t de relevante atributter.
	3	TilfÃ¸j 'CollisionShape2D' 
	1	Inspektor - > Shape (download)
	2	Capsule
	3	Rotate 90
	4	TrÃ¦k sÃ¥ collisionShape dÃ¦kker sprite2D
	5	Tal om: Hvorfor bruge collisionshape?
	1	Billedet er firkantet (klik pÃ¥ Sprite2D for at se kassen)
	2	Forskudt collisionShape2D gÃ¸r spillet mere spilbart
	6	Tal om: Hvad betyder rÃ¦kkefÃ¸lgen af noder

	4	TilfÃ¸j Paddle til Game scenen.
	5	'Gem' scene 
	1	BÃ¸rnene gÃ¸r det selv (ligesom med Paddle)
	1	Rod: Area2D (omdÃ¸b til “Gem”)
	2	Sprite2D (FÃ¸rste node)
	1	Texture: element_red_diamond.png
	3	CollisionShape2D:
	1	Shape: Rectangle
	2	Rotation 45

	6	Introducer GD-Script
	1	tilfÃ¸j script pÃ¥ Gem -> nÃ¦vn "Inherits", "Template" & "Path"). Snak om 
	1	Inheritance
	1	forÃ¦ldre       Area2d
	2	beste forÃ¦ldre Node2D
	3	OldeforÃ¦ldre   CanvasItem
	2	classes 
	1	DÃ¸ber Barnet af Area2D til Gem (class_name Gem)
	2	Hvis dit script ikke har et navn (er dÃ¸bt) kan resten af spillet ikke kalde det.
	3	Instances
	1	Classen findes kun som ide/koncept men er ikke i spillet.
	2	en instance af Gem-classen er Ã©n Gem som er en del af spillet. Ligesom ideen om en ko er classen er koen pÃ¥ market en instances af koen.
	7	Gem falder. 
	1	(2) Forklar 
	1	_ready()
	2	_process(delta) 
	1	kaldes automatisk af Godot hvert frame (60 gange per sekund ved standard settings)
	2	delta er vigtig â€“ det er tiden (i sekunder) siden sidste frame blev kÃ¸rt. Typisk omkring 0.016 sekunder ved 60 FPS.
	3	Hvorfor det betyder noget:
	•	Computere har varierende frame rates
	•	Du skal bruge delta til at gÃ¸re bevÃ¦gelse frame-rate uafhÃ¦ngig
	•	Uden delta: dÃ¥rlig ydeevne pÃ¥ langsommere computere
	3	Vector2
	2	Syntax
	1	indentation
	2	Store og smÃ¥ bogstaver
	3	export variable.
	8	Gem fjernes.
	9	Paddle bevÃ¦ger sig: 
	1	Naviger til 
	1	Project 
	2	Project Settings
	3	Input Map
	4	tilfÃ¸j 'action' left og right 
	5	brug Input singleton class i koden til at bevÃ¦ge
	10	Test at det virker :D Udlever cheat-sheet
Detaljeret Forklaring
	1	Lav en ny scene og vÃ¦lg 'Other Node' i menuen til venstre -> sÃ¸g efter Area2D og vÃ¦lg denne som root i scenen. Vi vil gerne bruge en Area2D fordi den kan registrere kollisioner med andre ting - det fÃ¥r vi brug for nÃ¥r vi skal fange diamanterne, hvordan skulle vi ellers finde ud af at vi rÃ¸rer en diamant? Ã†ndr navnet til 'Paddle' og gem scenen med Ctrl+S.
	2	Marker Paddle og tilfÃ¸j 'CollisionShape2D'-> I 'Inspector' vinduet til venstre kan du nu tilfÃ¸je en 'Shape' hvor vi i dette spil ville skulle bruge en 'Capsule'. Marker Paddle igen og tilfÃ¸j en 'Sprite2D' sÃ¥ vi kan vise et stykke grafik -> Hiv 'PaddleBlu.png' over i 'Texture' attributten. Under 'CollisionShape2D', roter den med 90 grader (under 'Transform') og sÃ¦t den sÃ¥ den passer med grafikken.
	3	Naviger til 'Game' scenen og marker root Noden -> vÃ¦lg 'instantiate a child scene' ved siden af plusset -> vÃ¦lg '.../paddle.tscn' -> Flyt den ned i bunden af scenen.
	4	FÃ¸lg step 1 & 2, men brug 'element_red_diamond.png' som Texture og en relevant CollisionShape2D (f.eks. 'Rectangle' drejet 45 grader)
	5	Introducer GD-Script -> nÃ¥r vi gerne vil have nogle funktionaliteter som ikke allerede bare eksisterer, her UDVIDER vi funktioner og attributter pÃ¥ vores scener :D Snak om Inheritance, classes og instances -> Hvis vi tÃ¦nker tilbage pÃ¥ sidste gang hvor vi snakkede om Noder, som hver har attributter og metoder, sÃ¥ kan vi ogsÃ¥ tÃ¦nke pÃ¥ dem som det vi kalder for klasser. Klasser er en mÃ¥de at indkaplse noget funktionalitet som kan genbruges i mange forskellige, og kan ses som et "blueprint" eller en "skabelon" for hvordan en specifik type ting skal fungere. NÃ¥r vi har en instans af noget, sÃ¥ har vi et instantieret objekt som fÃ¸lger den skabelon. F.eks. som vi har Person som klasse og Mie som instans. Inheritance er derudover noget som vi kan bruge til at arve koden fra en anden klasse i en ny klasse vi laver. F.eks. hvis vi har klassen for en person, sÃ¥ kan vi lave forskellige klasser som arver funktionerne og attributterne fra personen men ogsÃ¥ kan noget andet! (Vis ogsÃ¥ evt. i Inspector i GoDot, hvordan tingene er delt ind under forskellige overskrifter)
	6	Nu skal vi til at skrive lidt kode :D Du tilfÃ¸jer et script til en Node ved at markere den og trykke pÃ¥ den lille scroll med et grÃ¸nt +. Til at starte med tilfÃ¸jer vi et script til 'Gem' noden og lader den starte med Default script for Node2D. dette gÃ¸r at vi har en _process() som kÃ¸res hvert frame og en _ready() som kÃ¸res Ã©n gang som det fÃ¸rste, inden den ellers gÃ¥r i gang med at kÃ¸re videre. Mange af de ting vi arbejder med i vores spil kommer til at bruge Vector2, som er en Vector der indeholder 2 tal (what?), da vi jo netop arbejder i 2 dimensioner (x- og y-retning) er det super handy at have 2 tal af gangen. Vores position tilgÃ¥s med variabel navn 'position' og har 2 attributter (det er OGSÃ… en klasse :D), sÃ¥ for at opdatere vores position pÃ¥ y-aksen skal vi tilgÃ¥ og Ã¦ndre 'position.y'.
	7	For at kode hvornÃ¥r gem fjernes skal vi fÃ¸rst finde ud af hvornÃ¥r den har forladt skÃ¦rmen. (spÃ¸rg evt. her bÃ¸rnene om de har en idÃ© til hvordan) -> Vi kan hente stÃ¸rrelsen pÃ¥ viewport (altsÃ¥ stÃ¸rrelsen pÃ¥ spil-vinduet der er synligt hos spilleren) ved hjÃ¦lp af 'get_viewport_rect().size.y'. Funktionen returnere altsÃ¥ en Rect, hvoraf vi specifikt er interesseret i y-koordinatet pÃ¥ stÃ¸rrelsen af vinduet (da origin som udgangspunkt er i (0,0)). Hvis gem's y er stÃ¸rre end viewport y kan vi stoppe processen og fjerne gem (se kode) - mind her bÃ¸rnene om det faktum at y bliver stÃ¸rre nÃ¥r man bevÃ¦ger sig nedad.
	8	TilfÃ¸j venstre og hÃ¸jre instruktioner i Input map, og skriv herefter kode som vurdere om der er givet input ved hjÃ¦lp af 'Input.is_action_pressed("left")' som giver en bool (true / false) til at opdatere 'position.x
	9	Test at det virker & udlever cheat-sheet.

paddle.gd
extends Area2D

@export var speed : float = 200.0

func _process(delta: float) -> void:
    # MOVE PADDLE USING INPUT MAP (8)
    if Input.is_action_pressed("left"):
        position.x -= speed * delta
    if Input.is_action_pressed("right"):
        position.x += speed * delta

gem.gd
extends Area2D # INHERITANCE

class_name Gem

signal gem_off_screen

@export var speed : float = 100.0

func _process(delta: float) -> void:
    # FÃ… GEM TIL AT FALDE (6)
    position.y += speed * delta
    
    # FJERNE GEM I BUNDEN AF SKÃ†RMEN (7)
    if position.y > get_viewport_rect().size.y:
        gem_off_screen.emit()
        set_process(false)
        queue_free()




 
LEKTION 3 - Signaler & Gameplay
(kode under '3 - Signaler & Gameplay')

	1	Vi vil gerne vide nÃ¥r en gem rammer vores paddle -> hvad er signaler?
	2	TilfÃ¸j signal-hÃ¥ndtering 'area_entered(...)' pÃ¥ Paddle
	3	TilfÃ¸j custom signal 'gem_off_screen' pÃ¥ Gem
	4	TilfÃ¸j script game.gd til Game scene -> connect alle gems (minimum 2) til samme funktion
	5	Disconnect og slet alle gems og signal funktionen :O
	6	TilfÃ¸j en Timer til Game scenen med Autoplay og 2 sek timeout.
	7	Connect Timer timeout til game.gd og spawn en ny gem ved hvert timeout. (i.e. importer gem scene, skirv hjÃ¦lpe-funktion spawn_gem() og kald funktionen) -> test at gems spawner og falder :D
	8	TilfÃ¸j game_over() og connect gem_off_screen signalet
	9	TilfÃ¸j Class_name til Gem for at have bedre error-handling og development assistance.
Detaljeret Forklaring
	1	Vi vil gerne vide nÃ¥r en gem rammer vores paddle -> signaler er det vi bruger til at sende en besked om at der er sket noget; signaler informerer om specifikke typer af events og giver os mulighed for at Ã¦ndre pÃ¥ hvordan vores objekter opfÃ¸rer sig under specifikke forhold, som f.eks. en kollision. Signaler bliver sendt direkte til de objekter (altsÃ¥ instanser) som har subscribed til det specifikke signal, og objekterne har lokalt en funktion der bliver kÃ¸rt nÃ¥r signalet modtages.
	2	I hÃ¸jre side vÃ¦lg "Node" fanen frem for "Inspector" fanen, og sÃ¸rg for at vÃ¦re pÃ¥ 'Signals'. Dobbelt-klik pÃ¥ 'area_entered(...)' signalet - pop-up vinduet vil automatisk foreslÃ¥ connection til Area2D selv med metode-navnet '_on_area_entered' og den vil automatisk sÃ¦tte den nye funktion op.
	3	I toppen af gem.gd script defineres signal ved at skrive "signal gem_off_screen". derefter kan signalet sendes ud samme sted som vi stopper process ved at kÃ¸re koden "gem_off_screen.emit()"
	4	Opret nyt script i Game scene pÃ¥ root ved navn game.gd -> VÃ¦lg den ene gem og connect signalet vi har lavet i step 3 til en ny funktion -> vÃ¦lg herefter en anden gem og connect den til SAMME funktion som den fÃ¸rste gem (brug 'pick' til at vÃ¦lge den eksisterende funktion).
	5	Vi gÃ¸r klar til at auto-generere gems ved at slette de kopier vi havde liggende i game-scenen sÃ¥ vi kan arbejde pÃ¥ auto-generation, inklusiv signaler og signal funktion.
	6	TilfÃ¸j en Timer til Game scenen. Timeren er ligesom en ringeklokke; efter et givent stykke tid ringer den med et signal og siger "hov, sÃ¥ er tiden gÃ¥et!". Vi kan fÃ¥ den til automatisk at starte (Autoplay) og vÃ¦lge om den kun skal kÃ¸re Ã©n gang (One-shot). SlÃ¥ AUtoplay til og sÃ¦t timeren pÃ¥ 2 sekunder.
	7	TilfÃ¸j en export variable i game.gd af typen 'PackedScene' (.tscn fil) til gem_scene, og tilfÃ¸j herefter gem.tscn i 'Inspector' vinduet. En 'PackedScene' er en klasse, og som vi snakkede om i Lektion 2 kan vi lave en instans af en klasse / PackedScene! Vi laver en ny funktion spawn_gem() som laver en ny lokal variabel som er en 'gem_scene.instantiate()' (en instans af en gem scene) -> tilfÃ¸j instansen som barn til Game ved hjÃ¦lp af 'add_child(...)' -> generer en random x-position mellem 70 og 1050 (passer til default vinduet) ved hjÃ¦lp af 'randf_range(start, end)' og ryk gem til den x-position og en y-position pÃ¥ -50. InvokÃ©r funktionen on timer timeout OG i _ready funktionen :D
	8	Lav en tom game_over() funktion og kÃ¸r den nÃ¥r gems ryger ud fra skÃ¦rmen med noget a la 'new_gem.gem_off_screen.connect(game_over)'
	9	TilfÃ¸j Class_name til Gem for at have bedre error-handling og development assistance. Det gÃ¸r vores kode meget nemmere at arbejde med fordi vi kan bruge auto-completes til at undgÃ¥ en lang rÃ¦kke tastefejl o.lign.
LEKTION 4 - Point & Afslutning
(kode under '4 - Point & Afslutning')

	1	TilfÃ¸j "Label" til Game scenen med tekst '00000', stÃ¸rrelse 48 og en farve du godt kan lide.
	2	Fjern on_area_entered fra paddle, og tilfÃ¸j den i game i stedet - lad funktionen opdatere en lokal variabel '_score'.
	3	TilgÃ¥ Label i game.gd og opdater nÃ¥r scoren opdateres.
	4	Fjern Gem efter kollision.
	5	Skriv en funktion som stopper alt (timer, loop over 'children') og fÃ¥ game_over til at kalde denne.
	6	SlÃ¥ loop til for mp3 filen. TilfÃ¸j den herefter som baggrundsmusik i en 'AudioStreamPlayer' Node.
	7	TilfÃ¸j 'AudioStreamPlayer2D' med lydeffekten 'spell1_0.wav'. I game.gd, afspil lyden nÃ¥r der gives point i Game scenen.
	8	Preload 'explode.wav' i toppen af scriptet & i en nye funktion 'play_explosion() -> void' kÃ¸r explode lydfilen pÃ¥ 'AudioStreamPlayer2D'.
Detaljeret Forklaring
	1	GÃ¥ ind i Game scenen, marker root og tryk pÃ¥ plusset. SÃ¸g en "Label" node frem; dette er ikke en Node2D men derimod en Control node. Skriv teksten "00000" i tekst-feltet i inspectoren og observer i 2D-view at teksten dukker op pÃ¥ din skÃ¦rm. Under Control -> Theme Overrides, vÃ¦lg 'Font Sizes' 48 og 'Colors' til noget du syntes er pÃ¦nt (brug gerne alle 3). Du kan evt. brug sampling og vÃ¦lge en farve der er i spilvinduet. Flyt gerne label lidt ind sÃ¥ den ikke er direkte i 0,0 :)
	2	GÃ¥ til paddle scenen og disconnect signalet for area entered, samt slet funktionen i koden. Naviger herefter til Game scenen og connect paddle area entered signalet direkte til game.gd. Lav en int variabel i toppen som starter med at vÃ¦re 0 og opdater denne med 1 hver gang signalet modtages.
	3	Vi kan tilgÃ¥ bÃ¸rn af noden direkte i vores script ved hjÃ¦lp af $Label, men dett kan give ret mange problemer hvis vi skal tilgÃ¥ den samme node mange steder og vi lige pludselig omdÃ¸ber noden. Derfor laver vi en variabel med @onready annotation som henter label ind, og sÃ¦tter dennes tekst til "%05d" % _score -> tag et tal (d) og front-pad med 0 til 5 digits, formateret med _score som tallet.
	4	I samme funktion, tilfÃ¸j at den 'area' der kollideres med fÃ¥r kaldt queue_free()
	5	Lav en ny function 'stop_all() -> void' som stopper timeren (hent denne ind som en variabel ligesom det blev gjort med label) og definÃ©r derefter et for-loop over listen 'get_children()' hvor du fÃ¥r hvert barn i listen kalder '.set_process(false)'. Slet print-statement i game_over funktionen, og erstat med at kalde denne funktion.
	6	For 'bgm_action_5.mp3': NÃ¥r mp3-filen markeres og man i stedet for scene vÃ¦lger import i det venstre vindue, sÃ¥ vil der vÃ¦re en rÃ¦kke settings alt efter filtypen. SlÃ¥ her 'Loop' til for mp3-filen og klik reimport. TilfÃ¸j nu en 'AudioStreamPlayer' til Game scenen og slÃ¥ 'Autoplay' til samt sÃ¦t volumen lidt ned. TilfÃ¸j mp3-filen i stream feltet.
	7	TilfÃ¸j en 'AudioStreamPlayer2D' - det der gÃ¸r denne anderledes er at den spiller lyden fra en specifik lokation, hvilket giver en bedre oplevelse for folk med surround sound / hÃ¸retelefoner. Brug lydeffekten 'spell1_0.wav' som stream og importer noden Ã¸verst i game.gd ligesom vi gjorde med 'label'. I funktionen hvor vi opdaterer scoren og fjerner gem, opdater positionen pÃ¥ lyd-afspilleren til gem positionen og afspil derefter lyden.
	8	Preload 'explode.wav' i toppen af game.gd script; dette kan gÃ¸res med drag-ctrl-drop. Lav en ny funktion 'play_explosion()' som gÃ¸r (1) stopper AudioStreamPlayer2D, (2) sÃ¦tter AudioStreamPlayer2D.stream til den preloadede scene og (3) starter AudioStreamPlayer2D. Kald denne nye funktion i game_over.
LEKTION 5 - FRI LEG
Her kan bÃ¸rnene frit vÃ¦lge en retning at arbejde videre og forbedre spillet. De kan blandt andet overveje fÃ¸lgende idÃ©er eller kÃ¸re med deres egne:

	•	(Begynder) Gems falder langsomt til at starte med men falder hurtigere over tid eller efter x antal point.
	•	(Medium) TilfÃ¸j en anden farve gem som giver flere point. Overvej om denne skal vÃ¦re en seperat scene og generering eller om du tilfÃ¦ldigt skifter mellem de 2 typer.
	•	(Medium) Lav en start-knap -> (Avanceret) herefter kÃ¸r tilbage til skÃ¦rm med start-knap pÃ¥ game-over -> (Avanceret) kan du vise en highscore pÃ¥ start-skÃ¦rmen?

