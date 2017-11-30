---
title: Architekturprinzipien
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Architekturprinzipien
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 20524c8aa0e64fd40a1a4a6811063557f74074d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
#<a name="architectural-principles"></a>Architekturprinzipien

> "Wenn Generatoren Gebäude erstellt die Möglichkeit Programmierer schrieb Programme aus, und die erste Woodpecker, die kamen würde Civilization zerstört."  
> _\-Gerald Weinberg_

## <a name="summary"></a>Zusammenfassung

Sie sollten zu entwickeln und Entwerfen von softwarelösungen mit Verwaltbarkeit. Die Prinzipien, die in diesem Abschnitt können Sie gegen architekturbezogene Entscheidungen Systeminstallation, bei der sauberen, leicht verwaltbare Anwendungen führt. Im Allgemeinen werden dieser Prinzipien durch führen Sie bei der Erstellung von Anwendungen aus diskreten Komponenten, die nicht eng an anderen Teilen der Anwendung verknüpft sind, sondern vielmehr, kommunizieren über explizite Schnittstellen oder messaging-Systeme.

## <a name="common-design-principles"></a>Allgemeine Entwurfsprinzipien

### <a name="separation-of-concerns"></a>Trennung von Anliegen

Ist ein Leitprinzip beim Entwickeln von **Trennung von Anliegen**. Dieses Prinzip bestätigt, dass Software getrennt werden, sollten basierend auf den Arten von Arbeitsschritten, die er ausführt. Betrachten Sie beispielsweise eine Anwendung, enthält die Logik zum Identifizieren von wichtige Elemente, die dem Benutzer angezeigt und formatiert diese Elemente auf eine bestimmte Weise zu noch deutlicher zu machen. Das Verhalten, die verantwortlich für die Wahl, welche Elemente formatieren verbleiben soll, getrennt von das Verhalten, die verantwortlich für das die Elemente formatieren, da dies separate Aspekte sind, die nur zufällig miteinander verknüpft sind.

Anwendungen können architektonisch, logisch erstellt werden, um dieses Prinzip folgen, durch die Trennung von Business Kernverhalten von Infrastruktur und Benutzer Schnittstelle Logik. Im Idealfall sollten Geschäftsregeln und Geschäftslogik in einem separaten Projekt befinden, das nicht von anderen Projekten in der Anwendung abhängig sollten. Dadurch wird sichergestellt, dass das Geschäftsmodell einfach ist testen und ohne wird auf niedriger Ebene Implementierungsdetails eng gekoppelt weiterentwickeln können. Trennung von Anliegen ist eine wichtige Überlegung hinter der Verwendung von Ebenen Anwendungsarchitektur.

### <a name="encapsulation"></a>Kapselung

Verschiedene Teile einer Anwendung die zu verwendende **Kapselung** , anderen Teilen der Anwendung zu isolieren. Anwendungskomponenten und Ebenen sollte Anpassen ihrer interne Implementierung ohne Unterbrechung ihrer Mitarbeiter als externe Verträge nicht verletzt werden. Richtige Verwendung von Kapselung hilft zu erreichen, lose Kopplung und Modularität bei Anwendungs-Designs, da Objekte und Pakete mit alternative Implementierungen ersetzt werden können, solange die gleiche Schnittstelle beibehalten wird.

In Klassen erfolgt für die Kapselung von außerhalb der Zugriff auf den internen Zustand der Klasse beschränken. Wenn externer Akteur den Zustand des Objekts ändern möchte, sollten sie über ein klar definierte Funktion (oder Setter für eine Eigenschaft) Aufgabe ausführen, statt später durch direkten Zugriff auf den privaten Status des Objekts. Ebenso sollten Anwendungskomponenten und Anwendungen selbst genau definierte Schnittstellen für ihre Mitarbeiter verwenden, statt ihren Status direkt geändert werden, sodass verfügbar machen. Dadurch werden interne Anwendungsentwurf, stetig weiterentwickelt werden, ohne dass dadurch Projektmitarbeiter, sodass unterbrochen wird so lange die öffentliche Verträge verwaltet werden.

### <a name="dependency-inversion"></a>Die Umkehrung der Abhängigkeit

Die Richtung der Beziehung innerhalb der Anwendung sollte in die Richtung der Abstraktion, nicht Implementierungsdetails. Die meisten Anwendungen werden geschrieben, sodass Abhängigkeit zur Kompilierungszeit in Richtung der laufzeitausführung fließen. Dadurch wird ein direkter Abhängigkeitsdiagramm erzeugt. D. h. wenn Modul ein Aufrufe eine Funktion im Modul B, der aufgerufen wird, eine Funktion im C-Modul, und Kompilieren Zeit ein werden von B, die von C abhängig ist abhängig, wie in Abbildung 4 – 1 gezeigt.

![](./media/image4-1.png)

**Abbildung 4 – 1.** Direkte Abhängigkeitsdiagramm angezeigt.

Anwenden des Prinzips der Abhängigkeit Umkehrung A zum Aufrufen von Methoden für eine Abstraktion, die B implementiert, wodurch für eine aufzurufende B zur Laufzeit, ermöglicht jedoch für B, um eine Schnittstelle abhängig von gesteuert ein zum Zeitpunkt der Kompilierung (also *invertieren* die typische Abhängigkeit zur Kompilierungszeit). Zur Laufzeit der Fluss der Ausführung des Programms bleibt unverändert, aber die Einführung von Schnittstellen bedeutet, dass verschiedene Implementierungen dieser Schnittstellen leicht eingesteckt werden können.

![](./media/image4-2.png)

**Abbildung 4-2.** Invertierte Abhängigkeitsdiagramm.

**Die Umkehrung der Abhängigkeit** ist ein wesentlicher Bestandteil des lose verbundene Anwendungen erstellen, da Implementierungsdetails auf hängen, und Implementieren der höheren Ebene Abstraktionen, anstatt den umgekehrten geschrieben werden können. Die resultierenden Anwendungen werden daher einfach zu testender, modulare und verwaltbar. Das Geübte *Abhängigkeitsinjektion* erfolgt gemäß das Prinzip der Abhängigkeit Umkehrung möglich.

### <a name="explicit-dependencies"></a>Expliziten Abhängigkeiten

**Klassen und Methoden sollten explizit zusammenarbeitenden Objekte erfordern, die sie benötigen, um richtig zu funktionieren.** Klassenkonstruktoren bieten die Möglichkeit für Klassen, die Dinge identifizieren benötigten damit in einem gültigen Zustand ist und ordnungsgemäß funktioniert. Wenn Sie Klassen definiert haben, erstellt und aufgerufen werden kann, aber die funktioniert nur ordnungsgemäß, wenn bestimmte globalen oder Infrastruktur Komponenten vorhanden sind, werden diese Klassen werden *unehrlichen* mit ihren Clients. Der Konstruktor Vertrag ist mitteilen, dass der Client, den es nur benötigt, um die Dinge angegebene (möglicherweise nichts, wenn die Klasse nur einen Standardkonstruktor verwendet wird), aber dann zur Laufzeit, die er das Objekt wird etwas anderes wirklich benötigt.

Gemäß das Prinzip der expliziten Abhängigkeiten sind die Klassen und Methoden wird ehrlich mit ihren Clients zu, was sie benötigen, um zu funktionieren. Dadurch wird Ihr Code Weitere selbstdokumentierend und die Codierung Verträge Benutzerfreundlicher, da Benutzer stammen, die vertrauen, solange sie bieten, was in der Form der Methode erforderlich ist oder Parameter des Konstruktors, die Objekte, mit der Sie arbeiten, verhält sich ordnungsgemäß zur Laufzeit.

### <a name="single-responsibility"></a>Einzelne Verantwortung

Das Prinzip der einzigen Verantwortung eines objektorientierten Entwurfs betrifft, aber kann auch als eine architektonische Prinzip Trennung von Anliegen ähnlich betrachtet werden. Sie gibt an, dass Objekte nur eine Verantwortung sollte und dass sie, nur ein Grund zum Ändern aufweisen sollen. Insbesondere ist die einzige Situation, in der das Objekt geändert werden soll, wenn die Art und Weise, in der er seine Aufgaben ausführt, die aktualisiert werden muss. Nach diesem Prinzip hilft Ihnen bei der mehr erzeugen lose gekoppelten und modulare Systeme seit vielen Arten von Verhalten können implementiert werden als neue Klassen und nicht durch Hinzufügen von zusätzlichen dafür verantwortlich, vorhandene Klassen. Hinzufügen von neuen Klassen ist immer sicherer als die vorhandene Klassen ändern, da kein Code noch hängt von den neuen Klassen.

In einer Anwendung aufgrund eines monolithischen können dem Prinzip der einzelnen Verantwortung auf hoher Ebene auf die Ebenen in der Anwendung angewendet werden. Präsentation Verantwortung sollte in der Benutzeroberfläche Project bleiben, während Daten zugreifen sollten Verantwortung innerhalb eines Projekts Infrastruktur beibehalten werden. Geschäftslogik sollten im Anwendungsprojekt Core beibehalten werden, wo es leicht getestet werden und unabhängig von anderen Aufgaben weiterentwickeln kann.

Wenn dieses Prinzip ist auf die Anwendungsarchitektur angewendet und ausgeführt, um einen logischen Endpunkt, erhalten Sie Microservices. Eine bestimmte Microservice sollte eine einzelne Verantwortung verfügen. Wenn Sie das Verhalten eines Systems erweitern müssen, ist es normalerweise besser zu diesem Zweck durch Hinzufügen von zusätzlichen Microservices anstatt durch Verantwortung mit einer vorhandenen Arbeitsaufgabe hinzufügen.

[Erfahren Sie mehr über Microservices-Architektur](http://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>Wiederholen Sie nicht selbst (DIREKTSIGNAL)

Angeben des Verhaltens in Bezug auf einen bestimmten Konzepts an mehreren Stellen, da dies eine häufige Ursache der Fehler ist, ist die Anwendung vermeiden. Zu einem späteren Zeitpunkt wird eine Änderung im Anforderungen erforderlich, Ändern dieses Verhalten und die Wahrscheinlichkeit, dass mindestens eine Instanz des Verhaltens wird nicht aktualisiert werden, führt zu inkonsistentem Verhalten des Systems.

Anstatt Duplizierung Logik kapseln Sie es in ein Programmiermodell. Stellen Sie die Autorität für die einzelne über dieses Verhalten zu erstellen und haben eine andere Komponente der Anwendung, die dieses Verhalten des neuen Konstrukts erforderlich ist.

> [!NOTE]
> Vermeiden Sie das Binden von Verhalten, die nur zufällig wiederkehrende ist. Z. B. nur verwendet werden, weil beide zwei unterschiedliche Konstanten den gleichen Wert aufweisen, impliziert dies nicht, dass Sie nur eine Konstante ist, haben sollten, wenn grundsätzlich auf unterschiedliche Dinge sie verweisen.

### <a name="persistence-ignorance"></a>Persistenz Unkenntnis

**Persistenz Unkenntnis** (PI) bezieht sich auf Typen, die beibehalten werden müssen, aber deren Code ist nicht betroffen, durch die Auswahl der Persistenz-Technologie. Solche Typen in .NET werden manchmal als Plain Old CLR Objects (POCOs), bezeichnet, da sie nicht von einer bestimmten Basisklasse zu erben oder eine bestimmte Schnittstelle implementieren müssen. Persistenz Unkenntnis ist hilfreich, da die gleichen Geschäftsmodell in mehrerer Hinsicht bietet zusätzliche Flexibilität bei der Anwendung beibehalten werden kann. Persistenz-Optionen können im Laufe der Zeit aus einer Datenbank-Technologie in eine andere ändern oder weitere Formen der Persistenz können zusätzlich zu den mit dem Start der Anwendung erforderlich sein (z. B. bei Verwendung einer Redis-Cache oder Azure DocumentDb zusätzlich zu einer relationale Datenbank).

Einige Beispiele für Verstöße gegen dieses Prinzip:

-   Eine erforderliche Basisklasse

-   Eine erforderliche Schnittstelle-Implementierung

-   Klassen, die verantwortlich für das Speichern von sich selbst (z. B. den aktiven Datensatz-Muster)

-   Erforderliche Standardkonstruktor

-   Eigenschaften erfordern virtual-Schlüsselwort

-   Persistenz-spezifische erforderliche Attribute

Die Anforderung, dass Klassen Änderungen an den oben genannten Funktionen oder Verhalten haben fügt Kopplung zwischen den Typen beibehalten werden und die Auswahl der Persistenz-Technologie, weshalb es schwieriger, neue Daten für Zugriffsmethoden in der Zukunft zu verwenden.

### <a name="bounded-contexts"></a>Gebundene Kontexte

**Begrenzt die Kontexte** werden von einem zentralen Muster im Driven Design. Sie bieten eine Möglichkeit bewältigt Fortschritts Komplexität in großen Anwendungen oder Organisationen, durch die in separaten konzeptionelle Module unterteilen. Jedes konzeptionellen Modul darstellt, klicken Sie dann einen Kontext, der von anderen Kontexten getrennt ist (also begrenzt), und können unabhängig voneinander weiterentwickelt. Jede gebundene Kontext sollte idealerweise für Konzepte darin einen eigenen Namen auswählen und exklusiven Zugriff haben sollten, um einen eigenen Persistenzspeicher.

Zumindest sollten einzelne Webanwendungen bemühen, werden ihre eigenen gebundene Kontext, mit ihren eigenen Persistenzspeicher für ihr Geschäftsmodell, statt eine Datenbank mit anderen Anwendungen gemeinsam nutzen. Kommunikation zwischen den Kontexten gebundene tritt auf, über die programmgesteuerten Schnittstellen, anstatt über eine freigegebene Datenbank, die Geschäftslogik ermöglicht, und platzieren Sie Ereignisse werden als Reaktion auf Änderungen, die stattfinden. Begrenzt Kontexten Zuordnung eng an Microservices, die idealerweise auch als ihre eigenen einzelne gebundene Kontexte implementiert werden.

> ### <a name="references--modern-web-applications"></a>Verweise – moderner Webanwendungen
> - **Trennung von Anliegen**  
> <http://deviq.com/Separation-of-Concerns/>
> - **Kapselung** <http://deviq.com/encapsulation/>
> - **Abhängigkeit Umkehrung Prinzip**  
> <http://deviq.com/Dependency-Inversion-Principle/>
> - **Expliziten Abhängigkeiten Prinzip**  
> <http://deviq.com/Explicit-Dependencies-Principle/>
> - **Nicht selbst wiederholen**  
> <http://deviq.com/Don-t-Repeat-Yourself/>
> - **Persistenz Unkenntnis**  
> <http://deviq.com/Persistence-ignorance/>
> - **Gebundene Kontext**  
> <https://martinfowler.com/bliki/BoundedContext.HTML>

> [!div class="step-by-step"]
[Vorherigen] (Choose-between-traditional-web-and-single-page-apps.md) [weiter] (Common-Web-Anwendung-architectures.md)
