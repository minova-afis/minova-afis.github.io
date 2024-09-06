# MINOVA Hub Web Entrance

Der Web-Zugang ist erreichbar unter [minova-afis.github.io](https://minova-afis.github.io)

Credentials sind: name=user, passwort=(admin-Passwort in unseren Apps)

Der Link kann mit weiteren Parametern versehen werden, um gleich an eine bestimmte Stelle in der Hub zu springen -- zum Beispiel auf ein bestimmtes Kundensystem, wie [OAS-AWB]()

## Parameter

Über Link-Parameter kann das Verhalten des Hub-Viewers angepasst werden

### Path

Root-Pfad im Modell-Baum, z.B. [?path=Environment/Remotes/OAS-AWB-AFIS-minova.service](https://minova-afis.github.io/?path=Environment/Remotes/OAS-AWB-AFIS-minova.service). Der Pfad zu jedem bel. Element, kann im Info-Feld ausgelesen werden: 

![grafik](https://github.com/user-attachments/assets/921fffac-65a1-449a-ae9d-1439d7f587c2)

### Host

Hub-Quelle. In der Regel ist es der Haupt-Hub (*https://saas-app.minova.com/minova/hub*). Für abgeschottete Kundensysteme, kann der neue ServiceController die "lokale" Hub (= REST Hub service) bereitstellen, sodass die Adresse der IP/DNS Addresse des Rechners, wo der ServiceController läuft, gleicht. 
