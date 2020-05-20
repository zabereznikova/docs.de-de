---
title: Einführung in cloudbasierte Anwendungen
description: Erfahren Sie mehr über Cloud-Native Computing
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 6ec02a1388d6e0f26cdaa1f728f23a22ba52d735
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613940"
---
# <a name="introduction-to-cloud-native-applications"></a>Einführung in cloudbasierte Anwendungen

An einem anderen Tag, im Büro, an "The Next Big Thing".

Ihr Handy klingelt. Es ist Ihr benutzerfreundlicher Mitarbeiter, der Sie zweimal täglich über neue Aufträge aufruft.

Diesmal gibt es jedoch unterschiedliche Möglichkeiten: Start, Kapital und viel Geld.

Durch die Erwähnung der Cloud und der aktuellen Technologie werden Sie über den Edge übertragen.

Sie sind ein paar Wochen schneller, und Sie sind jetzt ein neuer Mitarbeiter in einer Entwurfs Sitzung, die eine wichtige eCommerce-Anwendung entwickelt. Sie konkurrieren mit den führenden eCommerce-Websites.

Wie wird Sie erstellt?

Wenn Sie die Anweisungen in den letzten 15 Jahren befolgen, werden Sie wahrscheinlich das in Abbildung 1,1 gezeigte System erstellen.

![Traditionelles monolithisches Design](./media/monolithic-design.png)

**(Abbildung 1-1)** . Traditionelles monolithisches Design

Sie erstellen eine große Kernanwendung, die ihre gesamte Domänen Logik enthält. Es umfasst Module wie z. b. Identität, Katalog, Reihenfolge und mehr. Die Core-App kommuniziert mit einer großen relationalen Datenbank. Der Kern macht Funktionen über eine HTML-Schnittstelle verfügbar.

Herzlichen Glückwunsch!  Sie haben soeben eine monolithische Anwendung erstellt.

Nicht alle ist schlecht. Monolithen bieten einige unterschiedliche Vorteile. Sie sind z. b. unkompliziert...

- build
- test
- Bereitstellen
- Problembehandlung
- Skalierung

Viele erfolgreiche apps, die heute vorhanden sind, wurden als Monolithen erstellt. Die APP ist ein Treffer und wird weiterentwickelt, Iterationen nach Iterationen werden hinzugefügt, und es werden mehr Funktionen hinzugefügt.

An einem gewissen Punkt können Sie jedoch nicht mit Unbehagen vertraut sein. Sie verlieren die Kontrolle über die Anwendung. Im Laufe der Zeit wird das Gefühl intensiver, und Sie geben schließlich einen Zustand ein, der als bezeichnet wird `Fear Cycle` .

- Die APP ist so überwältigend kompliziert geworden, dass Sie von keiner einzelnen Person verstanden wird.
- Sie befürchten, dass Änderungen vorgenommen werden. jede Änderung hat unbeabsichtigte und kostspielige Nebeneffekte.
- Neue Features/Korrekturen werden knifflig, zeitaufwändig und aufwendig zu implementieren.
- Jedes Release ist so klein wie möglich und erfordert eine vollständige Bereitstellung der gesamten Anwendung.
- Eine instabile Komponente kann das gesamte Systemabstürzen.
- Neue Technologien und Frameworks sind keine Option.
- Die Implementierung von Agile-Übermittlungs Methoden ist schwierig.
- Die Architektur Erosions Sätze werden in festgelegt, da sich die Codebasis mit nie enden "Sonderfällen" verschlechtert.
- Die Berater informieren Sie, dass Sie Sie neu schreiben müssen.

Viele Organisationen haben den monolithischen warteweg gelöst, indem Sie einen cloudbasierten Ansatz zum Aufbauen von Systemen eingeführt haben. In Abbildung 1-2 wird das gleiche System gezeigt wie das Anwenden von cloudbasierten Techniken und Verfahren.

![Native Cloud-Design](./media/cloud-native-design.png)

**Abbildung 1-2**. Native Cloud-Design

Beachten Sie, wie die Anwendung in einem Satz kleiner isolierter mikrodienste zerlegt wird. Jeder Dienst ist eigenständig und kapselt seinen eigenen Code, Ihre Daten und ihre Abhängigkeiten. Jede wird in einem Software Container bereitgestellt und von einem containerorchestrator verwaltet. Anstelle einer großen relationalen Datenbank besitzt jeder Dienst einen eigenen Datenspeicher, der sich je nach den Datenanforderungen unterscheidet. Beachten Sie, dass einige Dienste von einer relationalen Datenbank, aber von anderen in nosql-Datenbanken abhängen. Der Status eines Dienstanbieter wird in einem verteilten Cache gespeichert. Beachten Sie, dass der gesamte Datenverkehr über einen API-Gatewaydienst weitergeleitet wird, der für das Weiterleiten von Datenverkehr an die Back-End-Kerndienste und das Erzwingen vieler übergreifenden Am wichtigsten ist, dass die Anwendung die Features für Skalierbarkeit, Verfügbarkeit und Resilienz in modernen cloudplattformen vollständig nutzt.

### <a name="cloud-native-computing"></a>Cloud-Native Computing

Hmm... Wir haben soeben den Begriff " _Cloud Native_" verwendet. Der erste Gedanke könnte lauten: "Was genau bedeutet das?" Ein weiteres Branchen wörterwort, das von Softwareanbietern für die Markteinführung von Softwareanbietern mitentwickelt wird? "

Glücklicherweise ist es viel anders, und das Buch wird Ihnen hoffentlich helfen, Sie zu überzeugen.

Innerhalb kurzer Zeit ist die cloudbasierte Cloud ein Trend Trend in der Softwarebranche. Es ist eine neue Möglichkeit, große, komplexe Systeme zu entwickeln, einen Ansatz, der die modernen Software Entwicklungsverfahren, Technologien und cloudinfrastruktur in vollem Umfang nutzt. Der Ansatz ändert die Art und Weise, wie Sie Systeme entwerfen, implementieren, bereitstellen und operationalisieren.

Anders als der fortlaufende Hype, der unsere Branche steuert, ist die native Cloud _-Cloud eine echte_Lösung. Sehen Sie sich die [Cloud Native Computing Foundation](https://www.cncf.io/) (cncf) an, ein Konsortium aus mehr als 300 großen Unternehmen mit einer-Charta, um die cloudbasierte computingtechnologie über Technologie-und cloudstapel hinweg zu schaffen. Als eine der am stärksten einflussreichen Open Source-Gruppen hostet Sie viele der am schnellsten wachsenden Open Source-Projekte in GitHub. Dazu zählen Projekte wie [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Gesandter](https://www.envoyproxy.io/)und [GrpC](https://grpc.io/).

Cncf fördert ein Ökosystem von Open Source-und Vendor-Neutralität. Nach diesem Leitfaden werden in diesem Buch die cloudbasierten Prinzipien, Muster und bewährten Methoden vorgestellt, die Technologie agnostisch sind. Gleichzeitig werden die in der Microsoft Azure Cloud verfügbaren Dienste und Infrastrukturen zum Erstellen von cloudbasierten Systemen besprochen.

Was genau ist die Cloud Native? Setzen Sie sich zurück, und lassen Sie uns diese neue Welt erkunden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](definition.md)
