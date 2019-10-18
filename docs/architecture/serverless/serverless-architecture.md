---
title: Server lose Architektur-Server Lose apps
description: Untersuchung verschiedener Architekturen und apps, die von Server losen Architekturen unterstützt werden, einschließlich Web-Apps, Mobile Apps und IOT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 838dcd7b41df0d8297e1ae10f9c04a8d5b83b332
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522407"
---
# <a name="serverless-architecture"></a>Serverlose Architektur

Es gibt viele Ansätze für die Verwendung [Server loser](https://azure.com/serverless) Architekturen. In diesem Kapitel werden Beispiele für gängige Architekturen erläutert, die Server lose integrieren. Außerdem werden Probleme behandelt, die möglicherweise zusätzliche Herausforderungen darstellen oder bei der Implementierung von Server losen Überlegungen erforderlich sind. Schließlich werden mehrere Entwurfs Beispiele bereitgestellt, die verschiedene Server lose Anwendungsfälle veranschaulichen.

Server lose Hosts verwenden häufig eine vorhandene Container basierte-oder-pas-Schicht, um die Server losen Instanzen zu verwalten. Azure Functions basiert z. b. auf [Azure App Service](https://docs.microsoft.com/azure/app-service/). Der APP Service wird zum horizontalen hochskalieren von Instanzen und zum Verwalten der Laufzeit verwendet, die Azure Functions Code ausführt. Für Windows-basierte Funktionen wird der Host als "Pas" ausgeführt, und die .NET-Laufzeit wird horizontal hochskaliert. Bei Linux-basierten Funktionen nutzt der Host Container.

![Azure Functions-Architektur](./media/azure-functions-architecture.png)

Der webjobs-Kern bietet einen Ausführungs Kontext für die Funktion. Die Language Runtime führt Skripts aus, führt Bibliotheken aus und hostet das Framework für die Zielsprache. Beispielsweise wird Node. js zum Ausführen von JavaScript-Funktionen verwendet, und der .NET Framework wird zum C# Ausführen von Funktionen verwendet. Weitere Informationen zu Sprach-und Platt Form Optionen finden Sie weiter unten in diesem Kapitel.

Einige Projekte können von einem "All-in"-Ansatz für Server lose genutzt werden. Anwendungen, die sich stark auf Mikro Services stützen, können alle Mikro Dienste mithilfe von Server losen Technologien implementieren. Bei den meisten apps handelt es sich um Hybridlösungen, die einem N-Tier-Design folgen und Server lose für die Komponenten verwenden, die sinnvoll sind, da die Komponenten modular und unabhängig skalierbar sind. Um diese Szenarien zu verstehen, werden in diesem Abschnitt einige gängige Architekturbeispiele erläutert, die Server lose verwenden.

## <a name="full-serverless-back-end"></a>Vollständiges Server Loses Back-End

Das vollständige Server lose Back-End eignet sich ideal für verschiedene Arten von Szenarien, insbesondere bei der Erstellung von neuen oder "grünen field"-Anwendungen. Eine Anwendung mit einem großen Oberflächen Bereich von APIs kann davon profitieren, jede API als Server lose Funktion zu implementieren. Apps, die auf der microservices-Architektur basieren, sind ein weiteres Beispiel, das als vollständiges Server Loses Back-End implementiert werden kann. Die-Webdienste kommunizieren untereinander über verschiedene Protokolle. Zu den spezifischen Szenarien zählen:

- API-basierte SaaS-Produkte (Beispiel: Finanzzahlungen-Prozessor).
- Nachrichten gesteuerte Anwendungen (Beispiel: Geräte Überwachungslösung).
- Apps, die sich auf die Integration zwischen Diensten konzentrieren (Beispiel: Anwendung für die Fluggesellschaft).
- Prozesse, die regelmäßig ausgeführt werden (z. b. Zeit Geber basiertes Bereinigen der Datenbank).
- Apps, die sich auf die Datentransformation konzentrieren (Beispiel: Import ausgelöst durch Datei Upload).
- Extrahieren Sie Prozesse zum Transformieren und laden (ETL).

Es gibt weitere, spezifischere Anwendungsfälle, die später in diesem Dokument behandelt werden.

## <a name="monoliths-and-starving-the-beast"></a>Monolithen und "hungern des Tieres"

Eine gängige Herausforderung besteht darin, eine vorhandene monolithische Anwendung in die Cloud zu migrieren. Der am wenigsten riskante Ansatz besteht darin, vollständig auf virtuelle Computer zu migrieren. Viele Unternehmen bevorzugen die Migration als Gelegenheit, um die Codebasis zu modernisieren. Ein praktischer Ansatz für die Migration wird als "hungern des Tieres" bezeichnet. In diesem Szenario wird die monolithische "as is" migriert, um mit zu beginnen. Anschließend werden die ausgewählten Dienste modernisiert. In einigen Fällen ist die Signatur des Dienstanbieter mit dem Original identisch: Es wird einfach als Funktion gehostet. Clients werden so aktualisiert, dass Sie den neuen Dienst anstelle des monolithischen Endpunkts verwenden. In der Zwischenzeit ermöglichen durch Schritte wie z. b. die Daten Bank Replikation auch dann, wenn Transaktionen weiterhin von der monolithischen verarbeitet werden, ihre eigenen Speicher zu hosten Schließlich werden alle Clients zu den neuen Diensten migriert. Der monolithische Wert ist "verhungert" (seine Dienste werden nicht mehr aufgerufen), bis alle Funktionen ersetzt wurden. Die Kombination aus Server losen und Proxys kann einen Großteil dieser Migration ermöglichen.

![Migration von Server losen monolithischen](./media/serverless-monolith-migration.png)

Weitere Informationen zu diesem Ansatz finden Sie im Video: [bringen Sie Ihre APP in die Cloud mit Server losem Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>Web-Apps

Web-Apps sind hervorragend für Server lose Anwendungen geeignet. Heutzutage gibt es zwei gängige Ansätze für Web-Apps: Server gesteuert und Client gesteuert (z. b. Single-Page-Anwendung oder Spa). Server gesteuerte Web-Apps verwenden in der Regel eine middlewareebene, um API-Aufrufe zum renderingbedarf der Webbenutzer Oberfläche auszugeben Spa-Anwendungen machen Rest-API-Aufrufe direkt aus dem Browser. In beiden Szenarien kann Server Lose die Middleware-oder Rest-API-Anforderung unterstützen, indem die erforderliche Geschäftslogik bereitgestellt wird. Eine gängige Architektur ist die Einrichtung eines einfachen statischen Webservers. Die Single-Page-Anwendung (Spa) bietet HTML-, CSS-, JavaScript-und andere browserassets. Die Web-App stellt dann eine Verbindung mit einem Back-End für die Webdienste her

## <a name="mobile-back-ends"></a>Mobile Back-Ends

Das ereignisgesteuerte Paradigma von Server losen apps stellt sie ideal als Mobile Back-Ends dar. Das Mobile Gerät löst die Ereignisse aus, und der Server lose Code wird ausgeführt, um Anforderungen zu erfüllen. Wenn Sie ein Server Loses Modell nutzen, können Entwickler die Geschäftslogik verbessern, ohne ein vollständiges Anwendungs Update bereitstellen zu müssen. Der Server lose Ansatz ermöglicht es Teams auch, Endpunkte gemeinsam zu nutzen und parallel zu arbeiten.

Mobile Entwickler können Geschäftslogik entwickeln, ohne zu Experten auf der Serverseite zu werden. Bisher waren Mobile Apps mit lokalen Diensten verbunden. Das Entwickeln der Dienst Schicht erforderte das Verständnis der Server Plattform und des Programmier Paradigmas. Entwickler haben mit Vorgängen gearbeitet, um Server bereitzustellen und entsprechend zu konfigurieren. Manchmal wurden Tage oder sogar Wochen für das Entwickeln einer Bereitstellungs Pipeline aufgewendet. Alle diese Herausforderungen werden von Serverless gelöst.

Serverless abstrahiert die serverseitigen Abhängigkeiten und ermöglicht es dem Entwickler, sich auf die Geschäftslogik zu konzentrieren. Beispielsweise kann ein mobiler Entwickler, der Apps mithilfe eines JavaScript-Frameworks erstellt, auch Server lose Funktionen mit JavaScript erstellen. Der Server lose Host verwaltet das Betriebssystem, eine Node. js-Instanz zum Hosten des Codes, Paketabhängigkeiten usw. Dem Entwickler wird ein einfacher Satz von Eingaben und eine Standardvorlage für Ausgaben bereitgestellt. Sie können sich dann auf das entwickeln und Testen der Geschäftslogik konzentrieren. Sie sind daher in der Lage, vorhandene Fähigkeiten zu nutzen, um die Back-End-Logik für die Mobile App zu erstellen, ohne neue Plattformen erlernen zu müssen oder "serverseitiger Entwickler" zu werden.

![Server Loses mobiles Back-End](./media/serverless-mobile-backend.png)

Die meisten cloudanbieter bieten Mobile Server lose Produkte, die den gesamten Lebenszyklus der mobilen Entwicklung vereinfachen. Die Produkte können die Bereitstellung von Datenbanken automatisieren, um Daten beizubehalten, devops-Probleme zu behandeln, cloudbasierte Builds und Test-Frameworks bereitzustellen und Geschäftsprozesse mithilfe der bevorzugten Sprache des Entwicklers zu schreiben. Nach einem mobilen Server losen Ansatz kann der Prozess optimiert werden. Serverless entfernt den enormen mehr Aufwand für die Bereitstellung, Konfiguration und Wartung von Servern für das Mobile Back-End.

## <a name="internet-of-things-iot"></a>Internet der Dinge (IoT)

IOT bezieht sich auf physische Objekte, die miteinander vernetzt sind. Sie werden mitunter auch als "verbundene Geräte" oder "intelligente Geräte" bezeichnet. Alles von Autos und Automaten kann verbunden sein und Informationen von der Inventur bis hin zu Sensordaten, z. b. Temperatur und Luftfeuchtigkeit, senden. Im Unternehmen bietet IOT Verbesserungen des Geschäftsprozesses durch Überwachung und Automatisierung. IOT-Daten können verwendet werden, um das Klima in einem großen Warehouse zu regulieren oder die Inventur durch die Lieferkette nachzuverfolgen. IOT kann chemische Lecks erkennen und die feuerwehrabteilung anrufen, wenn Rauch erkannt wird.

Die schiere Menge von Geräten und Informationen ist häufig eine ereignisgesteuerte Architektur zum Weiterleiten und Verarbeiten von Nachrichten. Serverless ist aus verschiedenen Gründen eine ideale Lösung:

- Ermöglicht die Skalierung, wenn sich die Menge der Geräte und Daten erhöht.
- Ermöglicht das Hinzufügen neuer Endpunkte zur Unterstützung neuer Geräte und Sensoren.
- Ermöglicht die unabhängige Versionsverwaltung, damit Entwickler die Geschäftslogik für ein bestimmtes Gerät aktualisieren können, ohne dass das gesamte System bereitgestellt werden muss.
- Resilienz und weniger Ausfallzeiten.

Die pervasiativität von IOT führte zu mehreren Server losen Produkten, die sich speziell auf IOT-Probleme konzentrieren, wie z. b. [Azure IOT Hub](https://docs.microsoft.com/azure/iot-hub). Serverless automatisiert Aufgaben wie z. b. Geräteregistrierung, Richtlinien Erzwingung, Nachverfolgung und sogar Bereitstellung von Code auf Geräten im *Edge*-Bereich. Der Edge bezieht sich auf Geräte wie Sensoren und Server, die mit dem Internet verbunden sind, aber nicht aktiv sind.

>[!div class="step-by-step"]
>[Zurück](architecture-approaches.md)
>[Weiter](serverless-architecture-considerations.md)
