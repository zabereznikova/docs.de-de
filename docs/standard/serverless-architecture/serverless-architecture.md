---
title: Serverlose Architektur – serverlose apps
description: Die Auswertung von verschiedenen Architekturen und apps, die durch serverlose Architekturen, einschließlich Web-apps, Mobile Apps und IoT unterstützt werden.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 60d225d9794d5c15b0cd8e42800ccad4d7872756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967792"
---
# <a name="serverless-architecture"></a>Serverlose Architektur

Es gibt viele Ansätze mit [serverlose](http://azure.com/serverless) Architekturen. In diesem Kapitel werden Beispiele für allgemeine Architekturen, die serverlose integriert. Er behandelt auch bedenken, die möglicherweise zusätzliche Herausforderungen darstellen, oder benötigen zusätzliche Überlegung beim serverlosen implementieren. Schließlich sind einige entwurfsbeispielen bereitgestellt, die verschiedene serverlose Anwendungsfälle veranschaulichen.

Serverlose Hosts verwenden häufig eine vorhandene containerbasierte oder PaaS-Schicht, um die serverlose-Instanzen zu verwalten. Azure Functions basiert beispielsweise auf [Azure App Service](https://docs.microsoft.com/azure/app-service/). App Service wird verwendet, um Instanzen skalieren und Verwalten von der Runtime, die Azure Functions-Code ausgeführt wird. Für Windows-basierten Funktionen out der Host ausgeführt wird, als PaaS und skaliert die .NET Runtime. Für Linux-basierten Funktionen nutzt der Host Container.

![Azure Functions-Architektur](./media/azure-functions-architecture.png)

Das WebJobs-Core bietet einen Ausführungskontext für die Funktion. Der Language Runtime Skripts ausgeführt, führt der Bibliotheken und hostet das Framework für die Zielsprache. Z. B. Node.js wird verwendet, um JavaScript-Funktionen und .NET Framework wird verwendet, um die C#-Funktionen ausgeführt werden. Erfahren Sie mehr zu Sprache und Plattform-Optionen in diesem Kapitel.

Einige Projekte können von einer "umfassendste" Ansatz zum serverlosen profitieren. Anwendungen, die häufig auf Microservices basieren, können alle Microservices mit serverloser Technologie implementieren. Die meisten apps sind hybride, ein N-Tier-Design und serverlose für die Komponenten, die sinnvoll, da die Komponenten modular und unabhängig skalierbar sind. Damit dieser Szenarien sinnvoll sein können, führt in diesem Abschnitt durchlaufen einige gängige architekturbeispiele, die serverlose verwenden.

## <a name="full-serverless-back-end"></a>Vollständige serverlose Back-end

Das vollständige serverlose Back-End ist ideal für verschiedene Arten von Szenarien, insbesondere, wenn neu erstellen oder "green-Field"-Anwendungen. Eine Anwendung mit einer großen Oberfläche der APIs kann davon profitieren, implementieren jede API als eine serverlose Funktion. Apps, die auf Microservices-Architektur basieren, sind ein weiteres Beispiel, das als vollständige serverlose Back-End implementiert werden kann. Die Microservices über verschiedene Protokolle miteinander kommunizieren. Bestimmte Szenarien:

* API-basierte SaaS-Produkten (Beispiel: finanzielle Zahlungen-Prozessor).
* Nachrichtengesteuerter Anwendungen (Beispiel: Lösung für die geräteüberwachung).
* Apps mit dem Schwerpunkt Integration zwischen Diensten (Beispiel: Fluggesellschaft buchungsanwendung).
* Prozesse, die in regelmäßigen Abständen ausgeführt werden (Beispiel: Timer-basierten Datenbank bereinigen).
* Apps mit dem Schwerpunkt Datentransformation (Beispiel: Importieren von Dateiuploads ausgelöst).
* Extrahieren Sie, Transformieren und laden (ETL)-Prozesse.

Es gibt andere, spezifische Anwendungsfälle, die weiter unten in diesem Dokument behandelt werden.

## <a name="monoliths-and-starving-the-beast"></a>Mehr als Monolithen entwickelt und "belegen die Beast"

Eine gängige Herausforderung ist eine vorhandene monolithische Anwendung in die Cloud migrieren. Der ungefährlichste Ansatz besteht darin "lift and shift" ausschließlich auf virtuellen Computern. Viele Unternehmen möchten die Migration als Gelegenheit nutzen, um ihre Codebasis zu modernisieren. Eine praktische Methode zum Migrieren von heißt "belegen die Beast." In diesem Szenario wird die monolithische Anwendung migriert, "wie besehen" für den Einstieg. Anschließend werden die ausgewählten Dienste modernisiert. In einigen Fällen die Signatur des Diensts mit dem Original identisch ist: einfach gehostet wird als Funktion. Clients werden aktualisiert, um den neuen Dienst statt der monolithischen Anwendung-Endpunkt zu verwenden. In der Zwischenzeit ermöglichen Schritte aus, wie z. B. die Replikation der Microservices einen eigenen Speicher hosten, selbst wenn Transaktionen immer noch durch die monolithische Anwendung verarbeitet werden. Schließlich werden alle Clients die neuen Dienste migriert. Die monolithische Anwendung ist "blockiert" (seine Dienste nicht mehr aufgerufen), bis alle Funktionen ersetzt wurde. Die Kombination von serverlosen und Proxys können ein Großteil dieser Migration erleichtern.

![Serverlose Monolith-migration](./media/serverless-monolith-migration.png)

Weitere Informationen zu diesem Ansatz wird das Video: [Bringen Sie Ihre app in die Cloud mit serverlosen Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>Web-Apps

Web-apps sind gute Kandidaten für die serverlose Anwendungen. Heutzutage werden zwei allgemeine Ansätze zum Web-apps: Server, keysetgesteuerte und Client-gesteuerte (z. B. Single Page Application oder SPA). Servergesteuerte Web-apps verwenden eine Middleware-Ebene in der Regel zum Ausstellen von API-Aufrufe an die Web-Benutzeroberfläche zu rendern. SPA-Anwendungen Aufrufe von REST-API direkt über den Browser. In beiden Szenarien serverlose das Middleware oder die REST-API-Anforderung durch die Bereitstellung der erforderlichen Geschäftslogik aufnehmen kann. Eine allgemeine Architektur ist zum Einrichten eines einfachen Webservers für statisch. Die Single-Page Application (SPA) dient, HTML, CSS, JavaScript und andere Browser-Objekte. Die Web-app wird dann mit einer Microservices-Back-End verbunden.

## <a name="mobile-back-ends"></a>Mobile back-ends

Das Paradigma ereignisgesteuerte serverlose Apps eignen sie sich hervorragend als Back-Ends für mobile. Das mobile Gerät löst Ereignisse aus, und der serverlose Code ausgeführt wird, um Anforderungen zu erfüllen. Nutzen eines serverlosen Modells ermöglicht Entwicklern, die Geschäftslogik zu verbessern, ohne ein Update für die vollständige Anwendung bereitstellen zu müssen. Der serverlosen Ansatzes kann Teams zum Teilen von Endpunkten und arbeiten parallel.

Mobile-Entwickler können Geschäftslogik ohne Experten auf der Serverseite zu erstellen. Mobile apps in der Vergangenheit mit lokalen Diensten verbunden ist. Erstellen die Dienstschicht erforderlich, verstehen die Server-Plattform und Programmierung Paradigma. Entwickler arbeitet mit Vorgängen zum Server bereitstellen und konfigurieren sie entsprechend. Manchmal Tage oder sogar Wochen für aufgewendet wurden zum Erstellen einer Bereitstellungspipeline. All diese Herausforderungen werden durch serverlose adressiert.

Serverless abstrahiert die serverseitigen Abhängigkeiten, und es kann der Entwickler auf Geschäftslogik konzentrieren. Beispielsweise kann ein mobile-Entwickler, der apps mit JavaScript-Frameworks eines builds sowie serverlose Funktionen mit JavaScript erstellen. Die serverlose-Host verwaltet, das Betriebssystem, eine Node.js-Instanz zum Hosten des Codes, paketabhängigkeiten und mehr. Der Entwickler wird einen einfachen Satz von Eingaben und eine Standardvorlage für Ausgaben bereitgestellt werden. Sie können dann auf erstellen und testen die Geschäftslogik konzentrieren. Aus diesem Grund haben, können Ihre vorhandenen Kenntnisse nutzen, um die Back-End-Logik für die mobile app zu erstellen, ohne erfahren, neue Plattformen, oder werden Sie ein "serverseitige Entwickler".

![Serverlose Mobile back-end](./media/serverless-mobile-backend.png)

Die meisten Cloudanbieter bieten Mobile-basierte, serverlosen Produkte, die den gesamten mobilen Entwicklungslebenszyklus zu vereinfachen. Die Produkte können die Bereitstellung von Datenbanken zum Beibehalten von Daten, DevOps-Probleme behandeln, geben Sie cloudbasierte builds und Tests, Frameworks und die Möglichkeit, Skript-Geschäftsprozesse, die mithilfe des Entwicklers bevorzugte Sprache automatisieren. Einen Mobile Geräte konzipierte serverlose Ansatz folgen, kann den Prozess optimieren. Serverless entfernt den enormen Aufwand für die Bereitstellung, Konfiguration und Wartung von Servern für das mobile Back-End.

## <a name="internet-of-things-iot"></a>Internet der Dinge (IoT)

IoT bezieht sich auf physische Objekte, die miteinander vernetzt sind. Sie sind als "connected Devices" oder "intelligenten Geräten." bezeichnet Alles von Autos und Verkaufsautomaten möglicherweise verbunden sind und Informationen, die von Inventar bis hin zu Daten von triebwerksensoren wie Temperatur- und luftfeuchtigkeitsdaten senden. Im Unternehmen bietet IoT Business prozessverbesserungen durch die Überwachung und Automatisierung. IoT-Daten können verwendet werden, zum Steuern der Klima in einer umfassenden Warehouse oder Nachverfolgen von Inventar der Lieferkette. IoT kann chemischen Überläufe ermitteln und die Feuerwache Wenn Rauch erkannt wird.

Die schiere Menge der Geräte und häufig Informationen bestimmt eine ereignisgesteuerte Architektur, Route und Verarbeiten von Nachrichten. Serverlose ist eine ideale Lösung für verschiedene Gründe haben:

* Ermöglicht das Skalieren als die Anzahl der Geräte und Daten erhöht.
* Unterstützt das Hinzufügen neuer Endpunkte zur Unterstützung von neuen Geräten und Sensoren.
* Unabhängige versionsverwaltung vereinfacht, damit Entwickler die Geschäftslogik für ein bestimmtes Gerät aktualisiert werden können, ohne das gesamte System bereitstellen zu müssen.
* Resilienz und weniger Ausfallzeiten.

Die Verbreitung von IoT führt zur Anzeige mehrerer serverlose Produkte, deren Schwerpunkt liegt insbesondere auf IoT-Anforderungen, wie z. B. [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub). Serverless automatisiert Aufgaben wie z. B. Registrierung von Geräten, richtlinienerzwingung, nachverfolgen und sogar-Bereitstellung des Codes auf Geräte in *am Rand*. Der Rand bezieht sich auf Geräte wie Sensoren und stellantrieben, die mit verbunden sind, jedoch keiner aktiven Teil des Internets.

>[!div class="step-by-step"]
>[Zurück](architecture-approaches.md)
>[Weiter](serverless-architecture-considerations.md)
