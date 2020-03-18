---
ms.openlocfilehash: 33178637c4fcfb21e8190c3d2593f09326ea5995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73166635"
---
# <a name="github-issues-process-and-policy"></a>Prozess und Richtlinien zu GitHub-Issues

Die Ziele des Prozesses lauten wie folgt:

1. Sicherstellen, dass Fehler oder Ausfälle in unserer Dokumentation den Kundenerfolg nicht beeinträchtigen
1. Reagieren auf Kundenfeedback und Anliegen
1. Kontinuierliche Verbesserung der Benutzererfahrung für Volumenlizenzkunden
1. Weitere Details zur Kundenzufriedenheit durch offenen Dialog zu Herausforderungen und Lösungen

Das Verfahren besteht aus zwei Stufen, um die Reaktionsfähigkeit während der Priorisierung von Aufgaben sicherzustellen. In der ersten Stufe wird das Issue diagnostiziert und selektiert. In der zweiten Stufe wird das Issue aufgelöst. Wenn ein Issue einfach und dringlich ist, können die beiden Stufen kombiniert werden.

Der Prozess umfasst Aufgaben mit festen Zeitzuweisungen:

- Jedes Teammitglied verbringt an jedem Werktag bis zu einer halben Stunden mit der [Klassifizierung eingehender Issues](#diagnosis-phase), einschließlich der anfänglichen Antworten. Dadurch wird sichergestellt, dass wir auf neue Issues schnell reagieren können.
- Jedes Teammitglied verbringt bis zu einem halben Tag pro Woche mit der [Aktualisierung von Dokumenten](#resolution-phase), um die von Kunden generierten GitHub-Issues zu bearbeiten.

## <a name="diagnosis-phase"></a>Diagnosephase

Jedes Teammitglied verbringt bis zu 30 Minuten pro Werktag mit der Kategorisierung neuer Issues. Wir beantworten die folgenden Fragen:

- Ist das Issue ein Issue zur Dokumentation oder zum Produkt?
- Ist es kein Issue, sondern handelt es sich vielmehr um eine Frage, die besser in eine Forum oder auf eine Supportwebsite passt?
- Welche Priorität hat das Issue?
- In welchem Bereich wird dieses Issue verwaltet?

Wenn diese Fragen nicht in der ersten Überprüfung beantwortet werden können, stellen wir in den Kommentaren klärende Fragen.

Es gibt verschiedene Arten von Issues, die während der Diagnose- und Selektierungsphase geschlossen werden:

- **Kudos:** Wir bedanken uns und schließen das Issue.
- **Produktissue:** Issues, die sich auf das Produkt beziehen und nicht auf die Dokumentation, werden geschlossen. Wir führen ggf. auch zusätzliche Aktionen durch, wie unten beschrieben.
- **Verstöße gegen Verhaltensregeln:** Diese Issues werden geschlossen und gemeldet, wenn der [Verstoß gegen die Verhaltensregeln](https://dotnetfoundation.org/code-of-conduct) die Meldung und Blockierung rechtfertigt.
- **Duplikate:** Duplikate werde geschlossen und mit einem Kommentar versehen, der auf das bereits vorhandene Issue verweist.
- **doc-ok:** Der Kunde liegt falsch, und die Dokumentation ist richtig.
- **Forum:** Issues, die Supportanfragen oder Forumanfragen sind, werden an Stack Overflow und andere Supportwebsites weitergeleitet und geschlossen.

### <a name="actions-on-product-issues"></a>Aktions- oder Produktissues

Abhängig von der Art des Produktissues haben wir folgende Optionen:

- Übertragen des Issues an das entsprechende Produktrepository
- Schließen des Issues als Duplikat vorhandener Produktanforderungen
- Schließen des Issues mit der Empfehlung, es im Produktrepository zu öffnen

Die Auswertung der richtigen Vorgehensweise ist subjektiv. Die Teammitglieder entscheiden nach eigenem Ermessen über die richtige Aktion.

### <a name="actions-on-content-issues"></a>Aktionen zu Issues über Inhalte

Für andere Issues geht das Team wie folgt vor:

- Zuweisen einer Priorität
- Zuweisen eines Meilensteins, normalerweise „Backlog“
- Bewerten, ob ein Issue ein Kandidat für die Bezeichnung „up for grabs“ oder für die [Projekte für Mitwirkende an der .NET Community](https://github.com/dotnet/docs/projects/35) ist

Prioritätsstufen basieren auf den folgenden Richtlinien, sind jedoch subjektiv. Die Meilensteine sind ebenfalls subjektiv und basieren auf anderen Prioritäten wie aktuelle Zeitpläne zu Produktreleases und bevorstehende Launches.

- **P0:** Das Fehlen einer Dokumentation oder ein Fehler hindert Kunden daran, ein gängiges Szenario zu meistern.
  - **P0**-Issues werden innerhalb der folgenden drei Wochen behoben und haben Vorrang vor bereits geplanten Aufgaben.
- **P1:** Durch das Fehlen einer Dokumentation oder einen Fehler wird ein gängiges Szenario erheblich erschwert, oder andere bekannte Szenarios werden blockiert.
  - **P1**-Issues werden rechtzeitig geplant. Häufig werden P1-Issues für einen bevorstehenden Meilenstein geplant.
- **P2:** Issues, die zu geringfügigen Unannehmlichkeiten führen oder einen Artikel mit niedriger Seitenansicht beeinflussen.
  - **P2**-Issues werden generell behoben, wenn ein Artikel aus Gründen höherer Priorität aktualisiert wird.
- **P3:** Issues, die Anforderungen für Grenzfallszenarios darstellen.
  - **P3**-Issues werden ins Backlog platziert und für ein Update berücksichtigt, wenn Artikel aus Gründen höherer Priorität aktualisiert werden.

Teammitglieder verbringen einen begrenzten Zeitraum mit der Diagnose und Selektierung, damit sie mit geplanten Aufgaben schnell vorankommen. Jedes Teammitglied verbringt höchstens 30 Minuten pro Tag mit der Diagnose und der Selektierung.

Die Bezeichnung **up-for-grabs** wird angewendet, wenn ein Issue ein guter Kandidat für ein Communitymitglied (möglicherweise der Autor) ist, das die Fehlerbehebung übermitteln kann. Jedes Teammitglied, das die Bezeichnung **up-for-grabs** anwendet, hilft Communitymitgliedern dabei, sich durch den Pull Request-Erstellungsprozess zu arbeiten (oder findet jemanden, der helfen kann). Issues mit der Bezeichnung „up for grabs“ werden oft zu [Projekten für Communitybeiträge](https://github.com/dotnet/docs/projects/35) hinzugefügt.

> HINWEIS: Wir haben erst kürzlich die vorherige Konvention übernommen. Die Person, die die Bezeichnung hinzugefügt hat, kann Sie an ein anderes Teammitglied verweisen, das Ihnen weiterhelfen kann.

## <a name="resolution-phase"></a>Auflösungsphase

Die von Kunden generierten Issues werden als Teil der Planung für geplante Aufgaben gewichtet. Jedes Teammitglied plant vier Stunden pro Woche ein, um die von Kunden generierten Issues mit der höchsten Priorität zu beheben.

Die Auflösung der Issues folgt basierend auf der Prioritätsstufe, die während der Diagnose festgelegt wurde. Die eingehenden Issues von Kunden werden zusammen mit anderen Aufgaben mit ähnlicher Priorität priorisiert.

- **P0:** Sobald es erforderlich ist, während der nächsten drei Wochen
- **P1:** Mit anderen geplanten P1-Aufgaben eingeplant, d. h. normalerweise in den nächsten drei Monaten
- **P2:** Mit anderen geplanten P2-Aufgaben eingeplant, P2-Probleme werden regelmäßig basierend auf Bereich und Sichtbarkeit geplant. Häufig werden P2-Issues behoben, wenn ein Artikel aktualisiert wird.
- **P3:** Keine Garantie auf ein festes Datum. Wenn ein Artikel aktualisiert wird, untersuchen wir das Backlog auf andere Issues zum gleichen Artikel.

Issues können auf Grundlage neuen Feedbacks und Daten zur Artikelsichtbarkeit neu priorisiert werden.
