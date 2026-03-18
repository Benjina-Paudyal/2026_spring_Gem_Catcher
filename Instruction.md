##                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               LEKTION 1 \- Intro / Setup

(billeder+cheat-sheet under '1 \- intro')

1. Installering af GoDot 4.3 (Download fra [GoDot Hjemmeside](https://godotengine.org/))  
2. Introduktion til GoDot Engine (børn lukker computere\!);  
3. Sæt dit første spil op; sådan opretter du et nyt spil.  
4. Gå til 2D mode og snak om viewport (i.e. rendering surface) \+ koordinatsystem.  
5. Uddeling af 'Assets' folder samt flytte den ind i projektet.  
6. Hvad er Nodes?  
7. Hvad er en Scene?  
8. Uddel Cheat-sheets (de får dem kun 1 gang.... så det er eget tab hvis de mister dem\!)  
9. Lav Game-scene :D  
10. Kør "spillet".

### 

### Detaljeret Forklaring

1. **Download og unzip**  
   1. Hjælp børnene med at komme ind på hjemmesiden; hjælp dem med at udpakke / unzip et sted hvor det giver mening (i 'dokumenter' eller på 'skrivebordet'). Lav en NY FOLDER, hvor du lægger .exe filerne hen (brug også denne til spillene\!)  
2. **Vis færdig version (2025 spring)**  
   1. Vis børnene rundt i programmet; Demo første spil vi skal lave (færdig version);   
      1. \[2D view\] vs \[Script view\] (tscn vs gd)  
      2. Hvad er   
         1. Scene  
            1. Noder i træstruktur  
            2. Enhed som kan genbruges   
            3. Kan være  
* Karakter  
* Bane  
* menu screen  
* Projektil  
* UI element  
  2. Scene struktur (træ) (rod’en og børn)

     ![][image1]

     1. Roden (Paddle)  
        1. Engenskab for hele scene   
           2. The top-level node is the **root node** and controls the entire scene. Child nodes inherit properties from their parents.

        3. FileSystem (res:// godot stifinder/mapper)  
        4. Inspector  
3. **Setup projekt**  
   1. Vi starter med at åbne GoDot Engine (uden 'console'); 'create' \-\> Navn 'Gem Catcher' \-\> Browse for folder \-\> sørg for at 'create folder' er tjekket af (skal være en tom folder) \-\> Vælg 'Mobile' mode. ('Compatibility' mode hvis børnene har problemer med grafik kort/får advarsler).

4. **Spil box**  
   1. Snak om den lilla boks der definerer hvad vi kan se når vi starter spillet (alt uden for boksen vil ikke være på skærmen\!). Snak om x- og y-aksen (og specifikt at y-aksen vokser nedad og x-aksen vokser mod højre), hvor er (0,0)?  
5. **Del assets**  
   1. Del assets ud og bed dem om at flytte en kopi af hele mappen ind i deres spil-mappe :)  
6. **Noder**  
   1. (1) Noder er de mest essentielle byggesten i GoDot Engine; En Node er **1 enhed**. En node indeholder 2 ting;   
      1. ***funktioner** som GØR* noget og   
      2. ***attributter** som ER* noget. (2)   
   2. Udviklerne hos GoDot har været så søde at lave en masse Noder som kan en masse af de ting vi har brug for, så vi behøver ikke sidde og lave det hele fra bunden, men kan bygge videre ved hjælp af deres byggesten. (**EVT LEGO REFERENCE** \- I stedet for at bruge en masse små ensformige brikker, så kan vi bruge trekanter, større klodser og andre former, som er lavet for os i forvejen.)  
7. **Scener**  
   1. Scener er lavet af en række noder i en træstruktur. Der er præcis 1 'root'-node, og derefter er der børn og børnebørn osv. som hver bliver brugt til forskellige ting.   
   2. Vi kan også bruge scener inden i andre scener, ligesom vi bruger Noder.  
8. **Cheat-sheets \- vises**  
     
9. **tilføj 'Node2D' som root og kald den 'Game'**   
   1. gem i res://scenes/   
   2. Tilføj en 'Sprite2D' Node til at vise baggrunden som BARN til 'Game'.  
   3. Åbn 'assets' folderen i FileSystem og hiv 'GameBg.png' ind i 'Texture' attributten.  
   4. Sæt 'scale' til 0.7   
   5. flyt Sprite2D så den dækker viewport (under 'Transform'). \-\> Ctrl+S  
   6. ![][image2]  
   7. Alt er object (ikke primitive typer: int, float, boolean, string  
   8. Alt er noder (ikke resourser: billeder, musik) noder findes i den virkelig verden mens resourcer kan indgå i en node  
   9. Hvilken class skal man vælge? Den class som matcher formålet bedst.  
   10. ![][image3]

10. **Kør spillet**   
    1. "Run Project" \-\> i pop-up vælg "select current" som 'main scene' (i.e. det her er scenen som altid starter når vi kører spillet som helhed)   
    2. man kan ændre denne indstilling (Project \-\> Project Settings \-\> Application \-\> Run \-\> Main Scene)

## 

## LEKTION 2 \- Paddle & Gem

(billeder & Kode under '2 \- paddle & gem')

1. Tilføj Paddle (Adrea2d)  
   1. Lav en ny scene med en 'Area2D' Node som root, sæt navnet til 'Paddle' og gem.  
2. Tilføj Sprite2D'   
   1. som barn til Paddle, og sæt de relevante atributter.  
3. Tilføj 'CollisionShape2D'   
   1. Inspektor \- \> Shape (download)  
   2. Capsule  
   3. Rotate 90  
   4. Træk så collisionShape dækker sprite2D  
   5. Tal om: Hvorfor bruge collisionshape?  
      1. Billedet er firkantet (klik på Sprite2D for at se kassen)  
      2. Forskudt collisionShape2D gør spillet mere spilbart  
   6. Tal om: Hvad betyder rækkefølgen af noder  
      ![][image4]  
4. Tilføj Paddle til Game scenen.  
5. 'Gem' scene   
   1. Børnene gør det selv (ligesom med Paddle)  
      1. Rod: Area2D (omdøb til “Gem”)  
      2. Sprite2D (Første node)  
         1. Texture: element\_red\_diamond.png  
      3. CollisionShape2D:  
         1. Shape: Rectangle  
         2. Rotation 45

6. Introducer GD-Script  
   1. tilføj script på Gem \-\> nævn "Inherits", "Template" & "Path"). Snak om   
      1. **Inheritance**  
         1. forældre 	  Area2d  
         2. beste forældre Node2D  
         3. Oldeforældre   CanvasItem  
      2. **classes**   
         1. Døber Barnet af Area2D til Gem (class\_name Gem)  
         2. Hvis dit script ikke har et navn (er døbt) kan resten af spillet ikke kalde det.  
      3. **Instances**  
         1. Classen findes kun som ide/koncept men er ikke i spillet.  
         2. en instance af Gem-classen er én Gem som er en del af spillet. Ligesom ideen om en ko er classen er koen på market en instances af koen.  
7. Gem *falder*.   
   1. (2) Forklar   
      1. \_ready()  
      2. \_process(delta)   
         1. kaldes automatisk af Godot **hvert frame** (60 gange per sekund ved standard settings)  
         2. **`delta`** er vigtig – det er tiden (i sekunder) siden sidste frame blev kørt. Typisk omkring 0.016 sekunder ved 60 FPS.  
         3. **Hvorfor det betyder noget:**  
* Computere har varierende frame rates  
* Du skal bruge `delta` til at gøre bevægelse frame-rate uafhængig  
* Uden `delta`: dårlig ydeevne på langsommere computere  
  3. Vector2  
  2. Syntax  
     1. indentation  
     2. Store og små bogstaver  
  3. export variable.  
8. Gem *fjernes*.  
9. Paddle bevæger sig:   
   1. Naviger til   
      1. Project   
      2. Project Settings  
      3. Input Map  
      4. tilføj 'action' *left* og *right*   
      5. brug Input singleton class i koden til at bevæge  
10. Test at det virker :D Udlever cheat-sheet

### Detaljeret Forklaring

1. Lav en ny scene og vælg 'Other Node' i menuen til venstre \-\> søg efter Area2D og vælg denne som root i scenen. Vi vil gerne bruge en Area2D fordi den kan registrere **kollisioner** med andre ting \- det får vi brug for når vi skal fange diamanterne, hvordan skulle vi ellers finde ud af at vi rører en diamant? Ændr navnet til 'Paddle' og gem scenen med Ctrl+S.  
2. Marker Paddle og tilføj 'CollisionShape2D'-\> I 'Inspector' vinduet til venstre kan du nu tilføje en 'Shape' hvor vi i dette spil ville skulle bruge en 'Capsule'. Marker Paddle igen og tilføj en 'Sprite2D' så vi kan vise et stykke grafik \-\> Hiv 'PaddleBlu.png' over i 'Texture' attributten. Under 'CollisionShape2D', roter den med 90 grader (under 'Transform') og sæt den så den passer med grafikken.  
3. Naviger til 'Game' scenen og marker root Noden \-\> vælg 'instantiate a child scene' ved siden af plusset \-\> vælg '.../paddle.tscn' \-\> Flyt den ned i bunden af scenen.  
4. Følg step 1 & 2, men brug 'element\_red\_diamond.png' som Texture og en relevant CollisionShape2D (f.eks. 'Rectangle' drejet 45 grader)  
5. Introducer GD-Script \-\> når vi gerne vil have nogle funktionaliteter som ikke allerede bare eksisterer, her UDVIDER vi funktioner og attributter på vores scener :D Snak om **Inheritance**, **classes** og **instances** \-\> Hvis vi tænker tilbage på sidste gang hvor vi snakkede om Noder, som hver har attributter og metoder, så kan vi også tænke på dem som det vi kalder for klasser. Klasser er en måde at *indkaplse noget funktionalitet* som kan genbruges i mange forskellige, og kan ses som et "blueprint" eller en "**skabelon**" for hvordan en specifik type ting skal fungere. Når vi har en **instans** af noget, så har vi et *instantieret* objekt som følger den skabelon. F.eks. som vi har *Person* som klasse og *Mie* som instans. Inheritance er derudover noget som vi kan bruge til at **arve** koden fra en anden klasse i en ny klasse vi laver. F.eks. hvis vi har klassen for en person, så kan vi lave forskellige klasser som arver funktionerne og attributterne fra personen men også kan noget andet\! (Vis også evt. i *Inspector* i GoDot, hvordan tingene er delt ind under forskellige overskrifter)  
6. Nu skal vi til at skrive lidt kode :D Du tilføjer et script til en Node ved at markere den og trykke på den lille scroll med et grønt \+. Til at starte med tilføjer vi et script til 'Gem' noden og lader den starte med Default script for Node2D. dette gør at vi har en \_process() som køres hvert frame og en \_ready() som køres én gang som det første, inden den ellers går i gang med at køre videre. Mange af de ting vi arbejder med i vores spil kommer til at bruge Vector2, som er en Vector der indeholder 2 tal (what?), da vi jo netop arbejder i 2 dimensioner (x- og y-retning) er det super handy at have 2 tal af gangen. Vores position tilgås med variabel navn 'position' og har 2 attributter (det er OGSÅ en klasse :D), så for at opdatere vores position på y-aksen skal vi tilgå og ændre **'position.y'**.  
7. For at kode hvornår gem fjernes skal vi først finde ud af hvornår den har forladt skærmen. (spørg evt. her børnene om de har en idé til hvordan) \-\> Vi kan hente størrelsen på viewport (altså størrelsen på spil-vinduet der er synligt hos spilleren) ved hjælp af *'get\_viewport\_rect().size.y'*. Funktionen returnere altså en Rect, hvoraf vi specifikt er interesseret i y-koordinatet på størrelsen af vinduet (da origin som udgangspunkt er i (0,0)). Hvis gem's y er større end viewport y kan vi stoppe processen og fjerne gem (se kode) \- mind her børnene om det faktum at y bliver større når man bevæger sig nedad.  
8. Tilføj venstre og højre instruktioner i Input map, og skriv herefter kode som vurdere om der er givet input ved hjælp af *'Input.is\_action\_pressed("left")'* som giver en bool (true / false) til at opdatere *'position.x*  
9. Test at det virker & udlever cheat-sheet.

[paddle.gd](http://paddle.gd)  
extends Area2D

@export var speed : float \= 200.0

func \_process(delta: float) \-\> void:  
	\# MOVE PADDLE USING INPUT MAP (8)  
	if Input.is\_action\_pressed("left"):  
		position.x \-= speed \* delta  
	if Input.is\_action\_pressed("right"):  
		position.x \+= speed \* delta

[gem.gd](http://gem.gd)  
extends Area2D \# INHERITANCE

class\_name Gem

signal gem\_off\_screen

@export var speed : float \= 100.0

func \_process(delta: float) \-\> void:  
	\# FÅ GEM TIL AT FALDE (6)  
	position.y \+= speed \* delta  
	  
	\# FJERNE GEM I BUNDEN AF SKÆRMEN (7)  
	if position.y \> get\_viewport\_rect().size.y:  
		gem\_off\_screen.emit()  
		set\_process(false)  
		queue\_free()

 

## LEKTION 3 \- Signaler & Gameplay

(kode under '3 \- Signaler & Gameplay')

      0\. Opsummerer fra sidste gang og hvad vi skal lave i dag.

1. Vi vil gerne vide når en gem rammer vores paddle \-\> hvad er signaler?  
2. Tilføj **signal-håndtering** *'area\_entered(...)'* på Paddle  
3. Tilføj custom **signal** *'gem\_off\_screen'* på Gem  
4. Tilføj script game.gd til Game scene \-\> connect alle gems (minimum 2\) til samme funktion  
5. Disconnect og slet alle gems og signal funktionen :O  
6. Tilføj en **Timer** til Game scenen med Autoplay og 2 sek timeout.  
7. Connect Timer timeout til game.gd og spawn en ny gem ved hvert timeout. (i.e. importer gem scene, skirv hjælpe-funktion **spawn\_gem()** og kald funktionen) \-\> test at gems spawner og falder :D  
8. Tilføj **game\_over()** og connect gem\_off\_screen signalet  
9. Tilføj Class\_name til Gem for at have bedre error-handling og development assistance.

### 

### Detaljeret Forklaring

1. Signaler:   
   1. Vi vil gerne vide når en gem rammer vores paddle \-\> signaler er det vi bruger til at sende en besked om at der er sket noget; signaler informerer om specifikke typer af events og giver os mulighed for at ændre på hvordan vores objekter opfører sig under specifikke forhold, som f.eks. en kollision. Signaler bliver sendt direkte til de objekter (altså instanser) som har *subscribed*(lyter) til det specifikke signal, og objekterne har lokalt en funktion der bliver kørt når signalet modtages.  
   2. Vælg **Game** (Sceen) \-\> vælg **paddle** (Noden) \-\> Vælge **Signals**. ![][image5]  
   3. Dobbelt-klik på **area\_entered(...)** signalet \- pop-up vinduet vil automatisk foreslå connection til Area2D   
      1. Skift metode navnet til \-\> **\_on\_paddle\_area\_entered**  
   4. tilføj *print(“nu\!”)* til metoden for at teste at det virker.  
2. I toppen af gem.gd script defineres signal ved at skrive "signal gem\_off\_screen". Derefter kan signalet sendes ud samme sted som vi stopper process ved at køre koden "gem\_off\_screen.emit()"  
3. Opret nyt script i Game scene på root ved navn game.gd   
   1. Vælg den ene gem og connect signalet vi har lavet i step 3 til en ny funktion \-\>   
      1. *for c in self.get\_children():*  
      2.       *c.set\_process(false)*  
   2. Gentag for de andre(anden) gem  
   3. Tal om hvordan man godt kan bygge spillet på denne måde og hvorfor det er en dårlig ide. Flyt den éne gem over view-port og vis spillet.   
4. Vi gør klar til at auto-generere gems   
   1. slette de kopier vi havde liggende i game-scenen   
   2. I stedet bruger via: **auto-generation**, **signaler** og **signal funktion**.  
5. Tilføj en ***Timer*** til Game scenen.   
   1. Timeren er ligesom en ringeklokke; efter et givent stykke tid ringer den med et signal og siger "hov, så er tiden gået\!". Vi kan få den automatisk til at starte (**Autoplay**) og vælge om den kun skal køre én gang (**One-shot**). Slå Autoplay til og sæt timeren på 2 sekunder.

6. Tilføj en export variable   
   1. Navn: gem\_scene  
   2. Type:  PackedScene \-\> Det er navnet på en sceen (.tscn fil)   
   3. tilføj herefter i 'Inspector' vinduet. En 'PackedScene' er en klasse, og som vi snakkede om i Lektion 2 kan vi lave en **instans** af en klasse / PackedScene\!   
   4. Vi laver en ny funktion **spawn\_gem()**   
      1. Laver en ny lokal variabel   
         1. *'gem\_scene.instantiate()'* (en instans af en gem scene)   
      2. tilføj instansen som barn til Game ved hjælp af *'add\_child(...)'*   
      3. generer en random x-position mellem 70 og 1050 (passer til default vinduet) ved hjælp af *'randf\_range(start, end)'* og ryk gem til den x-position og en y-position på \-50. Invokér funktionen *on timer timeout* OG i *\_ready* funktionen :D  
   5. func spawn\_gem() \-\> void:  
   6. 	\# INSTANTIATE GEM  
   7. 	var new\_gem: Gem \= gem\_scene.instantiate()  
   8. 	var xpos: float \= randf\_range(70.0, 1050.0)  
   9. 	new\_gem.position \= Vector2(xpos, \-50)  
   10. 	add\_child(new\_gem)  
7. Lav en tom **game\_over()**   
   1. Hvad er **keywords** (or **reserved words**)  
   2. funktion og kør den når gems ryger ud fra skærmen med noget a la *'new\_gem.gem\_off\_screen.connect(game\_over)'*  
   3. *func stop\_all() \-\> void:*  
   4. 	*timer.stop()*  
   5. 	*for c in get\_children():*  
   6. 		*c.set\_process(false)*  
   7.   
   8. *func game\_over() \-\> void:*  
   9. 	*stop\_all()*  
   10. *Tilføj **timer** (træk med Ctrl nede)*  
   11. *Tilføj til func\_spawn\_gem()*  
       ***new\_gem.gem\_off\_screen.connect(game\_over)***  
8. Tilføj Class\_name til Gem for at have bedre error-handling og development assistance. Det gør vores kode meget nemmere at arbejde med fordi vi kan bruge auto-completes til at undgå en lang række tastefejl o.lign.

## 

## LEKTION 4 \- Point & Afslutning

(kode under '4 \- Point & Afslutning')

1. Tilføj "Label" til Game scenen med tekst '00000', størrelse 48 og en farve du godt kan lide.  
2. Fjern on\_area\_entered fra paddle, og tilføj den i game i stedet \- lad funktionen opdatere en lokal variabel '\_score'.  
3. Tilgå Label i game.gd og opdater når scoren opdateres.  
4. Fjern Gem efter kollision.  
5. Skriv en funktion som stopper alt (timer, loop over 'children') og få game\_over til at kalde denne.  
6. Slå loop til for mp3 filen. Tilføj den herefter som baggrundsmusik i en 'AudioStreamPlayer' Node.  
7. Tilføj 'AudioStreamPlayer2D' med lydeffekten 'spell1\_0.wav'. I game.gd, afspil lyden når der gives point i Game scenen.  
8. Preload 'explode.wav' i toppen af scriptet & i en nye funktion 'play\_explosion() \-\> void' kør explode lydfilen på 'AudioStreamPlayer2D'.

### Detaljeret Forklaring

1. Gå ind i Game scenen, marker root og tryk på plusset. Søg en "Label" node frem; dette er ikke en Node2D men derimod en **Control** node. Skriv teksten "00000" i tekst-feltet i inspectoren og observer i 2D-view at teksten dukker op på din skærm. Under *Control \-\> Theme Overrides*, vælg 'Font Sizes' 48 og 'Colors' til noget du syntes er pænt (brug gerne alle 3). Du kan evt. brug sampling og vælge en farve der er i spilvinduet. Flyt gerne label lidt ind så den ikke er direkte i 0,0 :)  
   1. Control (under Game)  
   2. Omdøb til **Label**  
   3. tekst \= “00000” (inspektor)  
   4. *Theme Overrides*.Font Sizes \= 48   
   5. *Theme Overrides*.Font.Colors \= vælge selv  
   6. Flyt label i 2D  
2. Gå til **paddle** scenen og   
   1. disconnect signalet for **area entered**, (er måske i Game(scene) \-\> Paddle(noden))  
   2. slet funktionen i koden (\_on\_paddle\_area\_entered)  
   3. Naviger herefter til **Game** scenen og connect paddle area entered signalet direkte til game.gd.   
      1. tjek at signal connection nu er i game.gd  
   4. I toppen a game.gd  
      1. Lav en int variabel i toppen af den som starter med at være 0 og   
      2. i \_on\_paddle\_area\_entered  opdater denne med 1 hver gang signalet modtages.  
3. Vi kan tilgå børn af noden direkte i vores script ved hjælp af *$Label*, men dett kan give ret mange problemer hvis vi skal tilgå den samme node mange steder og vi lige pludselig omdøber noden.   
   1. Lav en variabel med *@onready* annotation som henter label ind, og sætter   
   2. i **\_on\_paddle\_area\_entered** sæt   
      1. **score\_label.text \= "%05d" % \_score**   
      2. tager et tal (d) og front-pad med 0 til 5 digits, formateret med \_score som tallet.  
4. I samme funktion, tilføj at den   
   1. 'area' der kollideres med får kaldt *queue\_free()*  
5. Lav en ny function ***'stop\_all() \-\> void'*** som stopper timeren (hent denne ind som en variabel ligesom det blev gjort med label) og definér derefter et for-loop over listen **'get\_children()'** hvor du får hvert barn i listen kalder *'.set\_process(false)'*. Slet print-statement i game\_over funktionen, og erstat med at kalde denne funktion.

   func stop\_all() \-\> void:

   	timer.stop()

   	for c in get\_children():

   		c.set\_process(false)

6. Tilføj function **game\_over**  
   1. kalder stop\_all  
7. i **spawn\_gem** connect **new\_gem.gem\_off\_screen.connect(game\_over)**  
8. Tilføj nu en *'**AudioStreamPlayer**'* til Game scenen og slå 'Autoplay' til samt sæt volumen lidt ned. Tilføj mp3-filen i stream feltet.  
   1. For '**bgm\_action\_5.mp3**':   
      1. Dobbeltklik.  
         1. Slå her '**Loop**' til for mp3-filen og  
         2. Klik *reimport*.   
   2. Inspektor \-\> vælge **autoplay**  
9. Tilføj en *'**AudioStreamPlayer2D'*** \- det der gør denne anderledes er at den spiller lyden fra en specifik lokation, hvilket giver en bedre oplevelse for folk med surround sound / høretelefoner.   
   1. Brug lydeffekten '**spell1\_0.wav**' som stream  
   2. Importer noden øverst i game.gd ligesom vi gjorde med 'label'. I funktionen hvor vi opdaterer scoren og fjerner gem, opdater positionen på lyd-afspilleren til gem positionen og afspil derefter lyden.

10. Preload *'explode.wav'* i toppen af game.gd script; dette kan gøres med drag-ctrl-drop. Lav en ny funktion **'play\_explosion()'** som gør (1) stopper AudioStreamPlayer2D, (2) sætter AudioStreamPlayer2D.stream til den preloadede scene og (3) starter AudioStreamPlayer2D. Kald denne nye funktion i game\_over.

    func play\_explosion() \-\> void:

    	audio\_stream\_player\_2d.stop()

    	audio\_stream\_player\_2d.stream \= EXPLODE

    	audio\_stream\_player\_2d.play()

    

## LEKTION 5 \- FRI LEG

Her kan børnene frit vælge en retning at arbejde videre og forbedre spillet. De kan blandt andet overveje følgende idéer eller køre med deres egne:

- (Begynder) Gems falder langsomt til at starte med men falder hurtigere over tid eller efter x antal point.  
- (Medium) Tilføj en anden farve gem som giver flere point. Overvej om denne skal være en seperat scene og generering eller om du tilfældigt skifter mellem de 2 typer.  
- (Medium) Lav en start-knap \-\> (Avanceret) herefter kør tilbage til skærm med start-knap på game-over \-\> (Avanceret) kan du vise en highscore på start-skærmen?

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPwAAABQCAYAAAA9dRjyAAAPTElEQVR4Xu2dWZMVRRaA/TsayBZsSgt0N26gNKCyyY6K7G40IIgL+yZgq2i4sbjihgsg7gKKQvikvPsyExMzEzEx8zYxEZPDlxHnzqlTt+rWbejuous8fMHtqqysupf7ZZ7Mqjz3mmuvvTY4jlMNrrEbHMfpv7jwjlMhXHjHqRAuvONUCBfecSqEC+84FcKFd5wK0WPCL+oKCez+Zss5TlWZOXNmeOedd8IXX3wRfvvtt/DHH3+k+PXXX8OcOXNSx1quOuHffPPN8Msvv0R+/vnn8OWXX4bNmzeHgQMHpso2A3VNmTIltV3o6OiI55S/v/3223DvvfemyjnOlQbZL168GEF6K7tw4cKF1LGWHhfebs+iaHmE37VrV7j55pvDLbfcEubPnx8/hL1796bKNoML75SVzz77rCa1fl0Pe6ylV4S3vbjFls8D4Z988snEtrlz54Zz586FIUOGpMoXxYV3yspVIbzGCm6x5fOoJ/y4ceOijO3t7fHv8ePHh5dffjl8//33UcydO3eGwYMH18qPHTs2vP766+HMmTPh888/D5MnT04JP23atPDhhx+GH3/8MZ5z3rx5ucLfcccd4a233op18p+ycuXKcN1116Wu33GaxQpvseXzyBX+/vvvD0uXLk3Iwmu2sc+WzyJL7KztedQT/p577onCDh8+PI7lT506FZ577rkY8iPip59+WjuG/UhOgzBhwoQo9rvvvpsQngbjp59+Ck888USsY/HixeHEiROZwt90003hhx9+CGvWrAltbW0x4mD/qlWrUtfvOM1yub26Jld4xEYUvriIDrxmG/ts+SyyxM7anocWnh60tbU1HD16NLz66qu1MiNGjAgDBgyo/b1+/fpw+PDh+Hr27NmxF9bh/9SpU6PMIjyTgEeOHEmc9/HHH88U/qmnngr79+9PlKeH//jjjxPbHKc79JrwWvDOzs6IbgBs+SyyxM7angfC0xsLSPjGG2+EUaNG1cogPA3S7t27o7gIzkwn+9auXRvee++9RJ3XX399ooc/ePBglFiXIYrIEp7znz17Ng4hBM7JNl2H43SHXhMetPTdkR2yxM7anoeepWfMjtx6/w033BBDesboy5YtC3fffXfsnbXwRAT6mEGDBiV6eIR/5plnEmUI/fOE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>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIcAAAAVCAYAAABsSf1CAAAER0lEQVR4Xu2ZyUvkWhSHqxsaeqZRS5yqS2lnxQkXigOCiqD4BOE5j4giIoIoKDbigLPi7EpocGEvVHDxBOEJgiP6d7w/4O16e7p+hz4hnShWrNYkRS0+bu5NJffk3C/nQsoREhJC/kZwcLAl0MZlNxzaATuDBel9/57m37wxnYF372wvil/IgeR/f/2ayOGgfz1ybHj6ZvPPhw8cT0RQkG0F8Qs5Ij2Jx0LExcVZijK3m+MKyGEiXz0l/ODjR4qNjVXQLpQZIA7IEfSremjjtjq2lwNJxx6PUq4WIz4+nhISEkwBc98lh90E8Ss55I0VMRITE01BLYid5GhsbKSuri6lb1gOl8tF3d3dlJqaqjvnC5mZmRQaGqobf4j75MAiJSUlKfT391NPTw91dnbS/Pw8JScnU1lZ2W+/8YaGhgbdmBYRxBs5IiIiaHJyknJzc2ljY0N3/jlBTvB80jcsB2hublaOOzo6aGZmRunPzc3R8PAwH29tbdHa2hpPij4EWF1dpYqKCu6np6fT9PS08luA47q6OlpZWeEEl5eXU319PVVVVeniAHfJIVVDvWCHh4e6RcSbUl1dTVdXV1RbW8tjp6entLOzQ/v7+9yfnZ2li4sLKioqUq5Bi9+MjIzo7mlUDtxfjsPCwig/P195ZowNDQ0pOQIFBQVKvnp7e6m9vZ1ll/MTExMsm3aex+CzHEJJSQknGm+/VABZbAkeFQetyCESpaWlKZUjKiqKcnJyeHxqaooT5XQ6dfMJ3soBtre36fz8nOeShd7d3eVjWWjIgTYvL4/b7Oxsbm9ubpRrIHtra6tyHy1G5JAcqZFnVr/FS0tL3GrlkPOQDPFER0fr7uctPm8r4C45KisruS0sLKSFhQU+lgcfHBzktq2tTVlA9BGMXC9yZGVlcanFGGRCorRzqTEih3B7e6ss9OjoKB9DbLQiB4SFBKg4WCT1NWiLi4vp8vJSd29gRA6pHJGRkTwfqqY888DAgPI7yeV9csh5yDw+Pk4xMTG6uR7C522ltLT0ty1AgBwoi4uLi7ptJSUlhfsZGRm8rTQ1NSl9dclcXl7mVrutaGNQ460cmOvo6IiOj4/5WBYa5fv6+porgVYOtJAD1UXkODs743Zvb4/GxsZ0YhiVA7S0tND6+jrV1NRwX/3MyKV62+7r6+NtY3Nzk+VALuVlBMjnY7cVn+Uwglagp8BbOe7j5OSEq93BwYHu3GMxKsdjUVeOP8Ef2VashK9yPAXPJcdTE5DjCQjIYRHuksPsj2AgIIcFQMIn376lb58+6eQwEzt+IdXiUJdDGdSWSSuDtzTvyxf68eKF7k83LJBZYP4UT1yQA30Ig1i18VsZv5ADif/v1Sv6/+VLWve8pQK2mudG5p52OlmMvz5/DshhJiLI3y6XqWKoQQypnipmVzHAg3K43W7+emdl8EVVCA8PtxTq2LRxWxGst6z9T9gOjxXAgPXNAAAAAElFTkSuQmCC>