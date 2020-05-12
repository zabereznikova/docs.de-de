---
title: Architekturprinzipien
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Architekturprizipien
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: e291888bee25a9c87259560ca4b12635ee73c3c7
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975406"
---
# <a name="architectural-principles"></a>Architekturprinzipien

> „Wenn Architekten Gebäude so bauen würden, wie Programmierer Programme erstellen, würde der erste Specht, der auftauchen würde, die Zivilisation zerstören.“  
> _\- Gerald Weinberg_

Sie sollten Softwarelösungen mit der Verwaltbarkeit im Hinterkopf entwickeln und entwerfen. Die Prinzipien, die in diesem Artikel erläutert werden, können Ihnen bei Entscheidungen bezüglich der Architektur helfen, wodurch Sie ordentliche und verwaltbare Anwendungen erstellen können. Im Allgemeinen begleiten Sie diese Prinzipien in Richtung der Erstellung von Anwendungen aus einzelnen Komponenten, die nicht eng an andere Teile Ihrer Anwendung gebunden sind, sondern die eher über explizite Schnittstellen oder Nachrichtensysteme kommunizieren.

## <a name="common-design-principles"></a>Allgemeine Entwurfsprinzipien

### <a name="separation-of-concerns"></a>Separation of Concerns

Ein Leitprinzip beim Entwickeln ist das **Separation of Concerns**. Dieses Prinzip macht geltend, dass Software basierend auf der Arbeit, die von dieser ausgeführt wird, getrennt werden soll. Ein Beispiel hierfür ist eine Anwendung, die Logik zur Identifizierung von wichtigen Elementen enthält, die dem Benutzer angezeigt werden sollen, und die diese Elemente in einer Art und Weise formatiert, sodass diese auffälliger werden. Das Verhalten, das dafür verantwortlich ist, welche Elemente formatiert werden, sollte vom für das Formatieren der Elemente verantwortliche Verhalten getrennt werden, da dies separate Aspekte sind, die nur zufällig miteinander in Verbindung stehen.

Anwendungen können – architektonisch gesehen – logisch erstellt werden, um diesen Prinzipien zu folgen, indem das grundlegende Geschäftsverhalten von der Infrastruktur und der Logik der Benutzeroberfläche getrennt wird. Im Idealfall sollten sich Geschäftsregeln und Logik in einem separaten Projekt befinden, das nicht von anderen Projekten in der Anwendung abhängig sein darf. Dadurch kann sichergestellt werden, dass das Geschäftsmodell einfach zu testen ist und sich entwickeln kann, ohne eng an Details der untergeordneten Implementierung geknüpft zu sein. Die Separation of Concerns spielt im Hinblick auf die Verwendung von Schichten in Anwendungsarchitekturen eine wichtige Rolle.

### <a name="encapsulation"></a>Kapselung

Unterschiedliche Teile einer Anwendung müssen die **Kapselung** verwenden, um sie von anderen Teile der Anwendung zu isolieren. Anwendungskomponenten und -schichten sollten ihre interne Implementierung anpassen können, ohne dass Fehler bei ihren Komponenten verursacht werden, solange nicht gegen externe Verträge verstoßen wird. Durch die ordnungsgemäße Verwendung der Kapselung kann die lose Kopplung und Modularität in Anwendungsdesigns erreicht werden, da Objekte und Pakete durch alternative Implementierung ersetzt werden können, solange dieselbe Schnittstelle beibehalten wird.

In Klassen erfolgt die Kapselung durch Verringern des Zugriffs auf den internen Zustand der Klasse von außerhalb. Wenn ein Akteur von außerhalb den Zustand des Objekts manipulieren will, sollte dies durch eine klar definierte Funktion (oder einen Eigenschaftensetter) erfolgen und nicht über den Direktzugriff auf den privaten Zustand des Objekts. Anwendungskomponenten und Anwendungen selbst müssen ebenso klar definierte Schnittstellen für die Verwendung durch ihre Komponenten vorweisen und nicht zulassen, dass ihr Zustand direkt geändert werden kann. Dadurch kann das interne Design der Anwendung über einen Zeitraum weiterentwickelt werden, ohne dass die Sorge besteht, dass durch diese Aktion Fehler bei Komponenten auftritt, solange die öffentlichen Verträge bestehen.

### <a name="dependency-inversion"></a>Abhängigkeitsumkehr

Die Abhängigkeitsrichtung innerhalb der Anwendung sollte sich in Richtung der Abstraktion bewegen, nicht in Richtung Implementierungsdetails. Die meisten Anwendungen werden so geschrieben, dass die Kompilierzeitabhängigkeit in Richtung der Laufzeitausführung geht. Dadurch wird ein direktes Abhängigkeitsdiagramm erzeugt. Das heißt, wenn Modul A eine Funktion in Modul B aufruft, die eine Funktion in Modul C aufruft, hängt A zur Kompilierzeit von B ab, das von C abhängt, wie in Abbildung 4-1 gezeigt.

![Diagramm der direkten Abhängigkeit](./media/image4-1.png)

**Abbildung 4-1.** Diagramm der direkten Abhängigkeit

Durch die Anwendung des Prinzips der Abhängigkeitsumkehr kann A Methoden auf einer Abstraktion abrufen, die von B implementiert wird. So kann B von A zur Laufzeit aufgerufen werden, jedoch kann B von einer Schnittstelle abhängig sein, die von A zur Kompilierzeit kontrolliert wird (das bedeutet, dass die typische Kompilierzeitabhängigkeit *umgekehrt* wird). Der Ablauf der Programmausführung bleibt zur Laufzeit unverändert, jedoch bedeutet die Einführung von Schnittstellen, dass unterschiedliche Implementierungen dieser Schnittstellen einfach mit eingeschlossen werden können.

![Diagramm der umgekehrten Abhängigkeit](./media/image4-2.png)

**Abbildung 4-2**. Diagramm der umgekehrten Abhängigkeit

Die **Abhängigkeitsumkehrung** ist ein wichtiger Bestandteil beim Erstellen von lose gekoppelten Anwendungen, da die Implementierungsdetails so geschrieben werden können, dass sie von übergeordneten Abstraktionen abhängig sind und diese implementieren, anstatt andersherum. Die sich daraus ergebenden Anwendungen können besser getestet werden, sind modular und deshalb auch besser verwaltbar. Die Methode der *Abhängigkeitsinjektion* wird durch das nachfolgende Prinzip der Abhängigkeitsumkehrung ermöglicht.

### <a name="explicit-dependencies"></a>Explizite Abhängigkeiten

**Methoden und Klassen sollten explizit alle benötigten zusammenarbeitenden Objekte erfordern, um ordnungsgemäß zu funktionieren.** Damit Klassen sich in einem gültigen Zustand befinden bzw. ordnungsgemäß funktionieren können, bieten Klassenkonstruktoren die Möglichkeit, dass Klassen die dafür benötigen Elemente identifizieren können. Wenn Sie Klassen identifizieren, die konstruiert und aufgerufen werden können, die jedoch nur ordnungsgemäß funktionieren, wenn bestimmte globale Komponenten bzw. Komponenten der Infrastruktur vorhanden sind, sind diese Klassen Ihren Kunden gegenüber *unehrlich*. Der Konstruktorvertrag sagt aus, dass der Kunde nur die angegebenen Elemente benötigt (wenn möglich auch nichts, wenn die Klasse nur einen parameterlosen Konstruktor verwendet), aber zur Laufzeit wird angegeben, dass das Objekt etwas anderes benötigt.

Durch Befolgen des expliziten Abhängigkeitsprinzips sind Ihre Klassen und Methoden gegenüber den Kunden ehrlich, wenn es um die Elemente geht, die sie benötigen, um ordnungsgemäß zu arbeiten. Dadurch dokumentiert Ihr Code vermehrt selbst, und Ihr Codierungsvertrag wird benutzerfreundlicher, da Benutzer größeres Vertrauen in dem Zusammenhang entwickeln, dass wenn sie das bereitstellen, was für Methoden oder Konstruktorparameter erforderlich ist, sich die Objekte, mit denen sie arbeiten, zur Laufzeit ordnungsgemäß verhalten.

### <a name="single-responsibility"></a>Prinzip der einzigen Verantwortung (Single Responsibility)

Das Prinzip der einzigen Verantwortung gilt für ein objektorientiertes Design, kann aber auch als Architekturprinzip ähnlich der Separation of Concerns angesehen werden. Es besagt, dass Objekte nur eine Verantwortung haben dürfen und dass sie nur einen Grund für eine Änderung haben dürfen. Dies bedeutet, dass das Objekt nur dann geändert werden muss, wenn die Art und Weise, wie es seine einzige Aufgabe durchführt, aktualisiert werden muss. Wenn Sie dieses Prinzip befolgen, können Sie mehr lose gekoppelte und modulare Systeme erstellen, da viele Teile des neuen Verhalten als neue Klassen implementiert werden können, und so wird vorhandenen Klassen keine zusätzliche Verantwortung hinzugefügt. Das Hinzufügen neuer Klassen ist immer sicherer als das Ändern vorhandener Klassen, da noch kein Code von den neuen Klassen abhängig ist.

In einer monolithischen Anwendung können wir das Prinzip der einzigen Verantwortung allgemein auf die Schichten in der Anwendung anwenden. Die Präsentationsverantwortung muss im Benutzeroberflächenprojekt verbleiben, während die Datenzugriffsverantwortung innerhalb eine Infrastrukturprojekts beibehalten werden sollte. Geschäftslogik sollte im Anwendungskernprojekt verbleiben, wo sie einfach getestet werden kann und sich unabhängig von anderen Verantwortungen entwickeln kann.

Wenn dieses Prinzip auf die Anwendungsarchitektur angewendet wird und bis zu ihrem logischen Endpunkt reicht, erhalten Sie Microservices. Ein bestimmter Microservice muss über eine einzige Verantwortung verfügen. Wenn Sie das Verhalten eines Systems erweitern müssen, ist es in der Regel am besten, dies durch Hinzufügen von zusätzlichen Microservices zu tun, anstatt Verantwortung zu einem vorhandenen Verhalten hinzuzufügen.

[Weitere Informationen zur Microservicearchitektur](https://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>Don't Repeat Yourself (DRY)

Die Anwendung sollte kein Verhalten angeben, das mit einem bestimmten Konzept in mehreren Bereichen im Zusammenhang steht, da dies eine bekannte Fehlerquelle ist. Zu einem späteren Zeitpunkt können geänderte Anforderungen dazu führen, dass dieses Verhalten geändert werden muss. Es ist wahrscheinlich, dass mindestens eine Instanz des Verhaltens nicht aktualisiert werden kann, und das führt zu einem inkonsistenten Verhalten des Systems.

Kapseln Sie die Logik in einem Programmierungskonstrukt anstatt sie zu duplizieren. Machen Sie dieses Konstrukt zur einzelnen Autorität über dieses Verhalten. Ein anderer Teil der Anwendung, die dieses Verhalten erfordert, verwendet dann dieses neue Konstrukt.

> [!NOTE]
> Verknüpfen Sie keine Verhaltensmuster, die sich nur durch Zufall wiederholen. Auch wenn zwei unterschiedliche Konstanten über den gleichen Wert verfügen, bedeutet das nicht, dass Sie nur eine Konstante besitzen dürfen, wenn diese sich konzeptuell gesehen auf unterschiedliche Dinge beziehen.

### <a name="persistence-ignorance"></a>Ignorieren der Persistenz

Das **Ignorieren der Persistenz** (Persistence Ignorance, PI) bezieht sich auf Typen, die beibehalten werden müssen, deren Code jedoch von der Wahl der Persistenztechnologie nicht beeinflusst wird. Solche Typen werden in .NET häufig als „Plain Old CLR Objects“ (POCOs) bezeichnet, da sie nicht von einer bestimmten Basisklasse erben oder eine bestimmte Schnittstelle implementieren müssen. Das Ignorieren der Persistenz ist wertvoll, weil das Geschäftsmodell so auf unterschiedliche Weise beibehalten werden kann, wodurch zusätzliche Flexibilität für die Anwendung garantiert werden kann. Die Wahl der Persistenz kann sich mit der Zeit von einer Datenbanktechnologie zur anderen ändern, oder es sind möglicherweise zusätzliche Persistenzformen entsprechend der Komponente erforderlich, mit der die Anwendung gestartet wurde (z. B. mithilfe eines Redis-Caches oder mit Azure Cosmos DB zusätzlich zu einer relationalen Datenbank).

Einige Beispiele für Verstöße gegen dieses Prinzip:

- Eine erforderliche Basisklasse

- Eine erforderliche Schnittstellenimplementierung

- Klassen, die für die Speicherung von sich selbst verantwortlich sind (z. B. das Muster „Aktiver Datensatz“)

- Erforderlicher parameterloser Konstruktor

- Eigenschaften, die ein virtuelles Schlüsselwort erfordern

- Eigens für die Persistenz erforderliche Attribute

Die Anforderung, dass Klassen über eines der oben genannten Features oder Verhalten verfügen müssen hat zur Folge, dass die Kopplung zwischen Typen beibehalten werden muss, sowie die Wahl der Persistenztechnologie. So wird es schwieriger, zukünftig neue Strategien für den Datenzugriff zu realisieren.

### <a name="bounded-contexts"></a>Kontextgrenzen

**Kontextgrenzen** stellen ein zentrales Muster im domänengesteuerten Design dar. Sie bieten die Möglichkeit, mit der Komplexität in großen Anwendungen und Organisation umzugehen, indem eine Aufteilung in einzelne konzeptuelle Module erfolgt. Jedes konzeptuelle Modul stellt einen Kontext dar, der von anderen Kontexten getrennt (also gebunden) ist und sich unabhängig entwickeln kann. Jede Kontextgrenze sollte idealerweise ihre eigenen Namen für interne Konzepte auswählen und über exklusiven Zugriff auf den eigenen persistenten Speicher verfügen können.

Anstatt eine Datenbank mit anderen Anwendungen zu teilen, sollten einzelne Webanwendungen darin bestrebt sein, mindestens die eigene Kontextgrenze darzustellen, mit eigenem persistenten Speicher für ihr Geschäftsmodell. Die Kommunikation zwischen Kontextgrenzen erfolgt über Programmschnittstellen und nicht über eine freigegebene Datenbank. So können Geschäftslogik und Ereignisse als Reaktion auf auftretende Änderungen erfolgen. Kontextgrenzen sind Microservices eng zugeordnet. Diese sind ebenso ideal als ihre eigenen individuellen Kontextgrenzen implementiert.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [JAVA Design Patterns: Principles (JAVA-Entwurfsmuster: Prinzipien)](https://java-design-patterns.com/principles/)
- [Kontextgrenze](https://martinfowler.com/bliki/BoundedContext.html)

>[!div class="step-by-step"]
>[Zurück](choose-between-traditional-web-and-single-page-apps.md)
>[Weiter](common-web-application-architectures.md)
