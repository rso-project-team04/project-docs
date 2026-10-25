# Sistem za upravljanje energije v pametnem domu

### Skupina, člani:
Skupina *__(ime - todo)__* (4): Gašper Suhadolnik, Gašper Harej


### Opis projekta:
Namen projekta je razviti cloud-native rešitev za pomoč uporabnikom pri upravljanju energije v pametnem domu. Sistem bo uporabnikom omogočal nadzor in spremljanje pametnih naprav, bodisi ročno ali avtomatizirano, z uporabo avtomatiziranih pravil. Sistem bo poleg tega tudi ponujal nasvete za zmanjšanje porabe.
<!-- todo: dopolni -->

### Ogrodje in razvojno okolje
todo
<!-- todo: pregled, opis -->

### Shema arhitekture
![shema](images/shema.jpg "Title")
todo
<!-- todo - potrebno izboljšati izgled, po potrebi dopolniti -->


### Seznam funkcionalnosti mikrostoritev
__device-service__:
* vklop, izklop posamezne naprave
* dodajanje nove naprave
* odstranitev naprave
* pregled stanja naprave (vklop, izklop, trenutna poraba energije)

__telemetry-service__:
* spremljanje porabe energije naprav
* shranjevanje podatkov o porabi energije naprav

__automation-service__:
* avtomatični vklop ali izklop naprav ob določenih časih glede na postavljena pravila
* dodajanje (tudi odstranitev, enable, disable) pravil za avtomatični vklop in izklop naprav

__insights-service__:
* analiza porabe energije
* generiranje nasvetov o možnosti zmanjšanja porabe energije


### Primeri uporabe
| #  | Ime     | Opis    | Udeležene mikrostoritve |
| -  | ------- | ------- | - |
| 1  | Dodajanje nove naprave | Uporabnik doda novo napravo v sistem spremljanja energije. | device-service |
| 2  | Upravljanje naprav | Uporabnik ročno vklopi ali izklopi napravo. Pri odločitvi si lahko pomaga s trenutnim stanjem naprave (vklopljena, izklopljena, povprečna poraba), ki je prikazano na uporabniškem vmesniku. | device-service |
| 3  | Nastavitev urnika vklopa in izklopa naprave | Uporabnik ustvari pravilo za avtomatični vklop ali izklop naprave.  | automation-service |
| 4  | Pregled porabe posamezne naprave v določenem obdobju | Uporabnik izbere napravo s seznama in ob tem se mu prikaže graf porabe te naprave v doloečnem obdobju (dan, teden, mesec). | telemetry-service |
| 5  | Predlogi za zmanjšanje porabe    | Uporabnik zahteva nasvet oz. priporočila za zmanjšanje porabe. Ob kliku na gumb, se zajamejo podatki iz telemetry-service in avtomatičnih pravil in v ustrezni obliki posredujejo llm-u, ki vrne predloge za zmanjšanje porabe ali prilagoditev določenega pravila. | insights-service, telemetry-service, automation-service |

todo
<!-- todo - dodati se ksnga -->

