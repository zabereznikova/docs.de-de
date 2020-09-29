---
title: Serverlose Architektur – Serverlose Apps
description: Untersuchung verschiedener Architekturen und Apps, die von serverlosen Architekturen unterstützt werden, einschließlich Web-Apps, Mobile und IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: f7d80ce3957c2ad90a67ae6ba1fc2786af30fcc1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171714"
---
# <a name="serverless-architecture"></a>Serverlose Architektur

Es gibt viele Ansätze für die Verwendung von [serverlosen](https://azure.com/serverless) Architekturen. In diesem Kapitel werden Beispiele für gängige Architekturen erläutert, die serverlose Funktionen integrieren. Außerdem werden Probleme behandelt, die möglicherweise zusätzliche Herausforderungen darstellen oder bei der Implementierung von serverlosen Funktionen spezielle Überlegungen erforderlich machen. Schließlich werden mehrere Entwurfsbeispiele bereitgestellt, die verschiedene serverlose Anwendungsfälle veranschaulichen.

Serverlose Hosts verwenden häufig eine vorhandene containerbasierte- oder PaaS-Schicht, um die serverlosen Instanzen zu verwalten. Azure Functions basiert z.B. auf [Azure App Service](/azure/app-service/). App Service wird zum horizontalen Hochskalieren von Instanzen und zum Verwalten der Laufzeit verwendet, die Azure Functions-Code ausführt. Für Windows-basierte Funktionen wird der Host als PaaS ausgeführt und skaliert die .NET-Laufzeit horizontal hoch. Bei Linux-basierten Funktionen nutzt der Host Container.

![Azure Functions-Architektur](./media/azure-functions-architecture.png)

WebJobs Core bietet einen Ausführungskontext für die Funktion. Die Language Runtime führt Skripts und Bibliotheken aus und hostet das Framework für die Zielsprache. Beispielsweise wird Node.js zum Ausführen von JavaScript-Funktionen und .NET Framework zum Ausführen von C#-Funktionen verwendet. Weitere Informationen zu Sprach- und Plattformoptionen finden Sie weiter unten in diesem Kapitel.

Einige Projekte können ggf. von einem „ganzheitlichen“ Ansatz für serverlose Instanzen profitieren. Anwendungen, die sich stark auf Microservices stützen, können alle Microservices mithilfe von serverlosen Technologien implementieren. Die Mehrheit der Apps ist hybrid, folgt einem n-schichtigen Entwurf und verwendet serverlose Instanzen für die Komponenten, bei denen dies sinnvoll sind, da die Komponenten modular und unabhängig voneinander skalierbar sind. Um diese Szenarien zu verstehen, werden in diesem Abschnitt einige gängige Architekturbeispiele erläutert, die serverlose Instanzen verwenden.

## <a name="full-serverless-back-end"></a>Vollständiges serverloses Back-End

Das vollständige serverlose Back-End eignet sich ideal für verschiedene Arten von Szenarien, insbesondere bei der Erstellung von neuen oder „Greenfield“-Anwendungen. Eine Anwendung mit einem großen Oberfläche von APIs kann davon profitieren, jede API als serverlose Funktion zu implementieren. Apps, die auf einer Microservicesarchitektur basieren, sind ein weiteres Beispiel, das als vollständiges serverloses Back-End implementiert werden kann. Die Microservices kommunizieren untereinander über verschiedene Protokolle. Spezifische Szenarien sind:

- API-basierte SaaS-Produkte (Beispiel: Finanzzahlungesprozessor).
- Nachrichtengesteuerte Anwendungen (Beispiel: Geräteüberwachungslösung).
- Apps, die sich auf die Integration zwischen Diensten konzentrieren (Beispiel: Anwendung für Flugticketbuchung).
- Prozesse, die regelmäßig ausgeführt werden (Beispiel: Timerbasiertes Bereinigen einer Datenbank).
- Apps, die sich auf Datentransformation konzentrieren (Beispiel: Import ausgelöst durch Dateiupload).
- ETL-Prozesse (Extrahieren, Transformieren und Laden)

Es gibt weitere, spezifischere Anwendungsfälle, die später in diesem Dokument behandelt werden.

## <a name="monoliths-and-starving-the-beast"></a>Monolithische Anwendungen und „Aushungern der Bestie“

Eine gängige Herausforderung besteht darin, eine vorhandene monolithische Anwendung in die Cloud zu migrieren. Der am wenigsten riskante Ansatz besteht darin, mithilfe von „Lift and Shift“ eine vollständige Migration zu virtuellen Computern auszuführen. Viele Unternehmen bevorzugen es, die Migration als Gelegenheit zu nutzen, um ihre Codebasis zu modernisieren. Ein praktischer Ansatz für die Migration wird als „Aushungern der Bestie“ bezeichnet. In diesem Szenario wird die monolithische Anwendung zunächst „unverändert“ migriert. Anschließend werden ausgewählte Dienste modernisiert. In einigen Fällen ist die Signatur des Diensts mit dem Original identisch: Er wird einfach als Funktion gehostet. Clients werden so aktualisiert, dass Sie den neuen Dienst anstelle des monolithischen Endpunkts verwenden. In der Zwischenzeit ermöglichen Schritte wie Datenbankreplikation es Microservices, ihren eigenen Speicher zu hosten, auch wenn Transaktionen noch von der monolithischen Anwendung verarbeitet werden. Schließlich werden alle Clients zu den neuen Diensten migriert. Die monolithische Anwendung wird „ausgehungert“ (ihre Dienste werden nicht mehr aufgerufen), bis alle Funktionen ersetzt wurden. Die Kombination aus serverlosen Instanzen und Proxys kann einen Großteil dieser Migration ermöglichen.

![Serverlose Migration von monolithischen Anwendungen](./media/serverless-monolith-migration.png)

Weitere Informationen zu diesem Ansatz finden Sie in diesem Video: [Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102) (Migrieren einer App zur Cloud mit serverlosen Azure Functions).

## <a name="web-apps"></a>Web-Apps

Web-Apps sind hervorragende Kandidaten für serverlose Anwendungen. Heutzutage gibt es zwei gängige Ansätze für Web-Apps: servergesteuert und clientgesteuert (z.B. Single-Page-Anwendung oder SPA). Servergesteuerte Web-Apps verwenden in der Regel eine Middlewareschicht, um API-Aufrufe zum Rendern der Web-UI auszugeben. SPA-Anwendungen nehmen Aufrufe der REST-API direkt aus dem Browser vor. In beiden Szenarien können serverlose Instanzen die Middleware- oder REST-API-Anforderung unterstützen, indem die erforderliche Geschäftslogik bereitgestellt wird. Eine gängige Architektur ist die Einrichtung eines schlanken statischen Webservers. Die Single-Page-Anwendung (SPA) stellt HTML-, CSS-, JavaScript- und andere Browserressourcen bereit. Die Web-App stellt dann eine Verbindung mit einem Microservices-Back-End her.

## <a name="mobile-back-ends"></a>Mobile-Back-Ends

Das ereignisgesteuerte Paradigma von serverlosen Apps macht sie zu idealen Mobile-Back-Ends. Das mobile Gerät löst die Ereignisse aus, und der serverlose Code wird ausgeführt, um Anforderungen zu erfüllen. Wenn sie ein serverloses Modell nutzen, können Entwickler die Geschäftslogik verbessern, ohne ein vollständiges Anwendungsupdate bereitstellen zu müssen. Der serverlose Ansatz ermöglicht es Teams auch, Endpunkte gemeinsam zu nutzen und parallel zu arbeiten.

Mobile-Entwickler können Geschäftslogik entwickeln, ohne zu Experten auf der Serverseite zu werden. Bisher waren Mobile-Apps mit lokalen Diensten verbunden. Das Entwickeln der Dienstschicht erforderte ein Verständnis der Serverplattform und des Programmierparadigmas. Entwickler haben mit Vorgängen gearbeitet, um Server bereitzustellen und entsprechend zu konfigurieren. Manchmal wurden Tage oder sogar Wochen für das Entwickeln einer Bereitstellungspipeline aufgewendet. Alle diese Herausforderungen werden durch serverlose Instanzen gelöst.

Das serverlose Modell abstrahiert die serverseitigen Abhängigkeiten und ermöglicht es dem Entwickler, sich auf die Geschäftslogik zu konzentrieren. Beispielsweise kann ein Mobile-Entwickler, der Apps mithilfe eines JavaScript-Frameworks erstellt, auch mit JavaScript serverlose Funktionen erstellen. Der serverlose Host verwaltet das Betriebssystem, eine Node.js-Instanz zum Hosten des Codes, Paketabhängigkeiten usw. Für den Entwickler wird ein einfacher Satz von Eingaben und eine Standardvorlage für Ausgaben bereitgestellt. Sie können sich dann auf das Entwickeln und Testen der Geschäftslogik konzentrieren. Sie sind daher in der Lage, vorhandene Fähigkeiten zu nutzen, um die Back-End-Logik für die Mobile-App zu erstellen, ohne neue Plattformen erlernen zu müssen oder zu einem „serverseitigen Entwickler“ zu werden.

![Serverloses Mobile-Back-End](./media/serverless-mobile-backend.png)

Die meisten Cloudanbieter bieten mobile-basierte serverlose Produkte, die den gesamten Lebenszyklus der Mobile-Entwicklung vereinfachen. Die Produkte können die Bereitstellung von Datenbanken automatisieren, um Daten persistent zu speichern, DevOps-Bedenken berücksichtigen, cloudbasierte Builds und Testframeworks bereitstellen und die Möglichkeit bieten, Geschäftsprozesse in der vom Entwickler bevorzugten Sprache zu programmieren. Ein mobile-zentrierter, serverloser Ansatz kann den Prozess optimieren. Das serverlose Modell beseitigt den enormen Mehraufwand für die Bereitstellung, Konfiguration und Verwaltung von Servern für das Mobile-Back-End.

## <a name="internet-of-things-iot"></a>Internet der Dinge (IoT)

IoT bezieht sich auf physische Objekte, die miteinander vernetzt sind. Diese werden mitunter auch als „verbundene Geräte“, „intelligente Geräte“ oder „Smart Devices“ bezeichnet. Es kann alles von Autos bis hin zu Verkaufsautomaten vernetzt werden und Informationen zum Warenbestand bis hin zu Sensordaten wie Temperatur und Feuchtigkeit senden. Im Unternehmen bietet IoT Verbesserungen des Geschäftsprozesses durch Überwachung und Automatisierung. IoT-Daten können verwendet werden, um das Klima in einem großen Lager zu regulieren oder den Warenbestand durch die Lieferkette nachzuverfolgen. IoT kann Chemikalienverluste erkennen und die Feuerwehr rufen, wenn Rauch entdeckt wird.

Die schiere Menge an Geräten und Informationen erfordert oft eine ereignisgesteuerte Architektur zur Weiterleitung und Verarbeitung von Nachrichten. Das serverlose Modell ist aus verschiedenen Gründen eine ideale Lösung:

- Es ermöglicht Skalierung, wenn sich die Menge der Geräte und Daten erhöht.
- Es ermöglicht das Hinzufügen neuer Endpunkte zur Unterstützung neuer Geräte und Sensoren.
- Es ermöglicht die unabhängige Versionsverwaltung, damit Entwickler die Geschäftslogik für ein bestimmtes Gerät aktualisieren können, ohne dass das gesamte System bereitgestellt werden muss.
- Resilienz und weniger Ausfallzeiten.

Die Allgegenwärtigkeit von IoT hat zu mehreren serverlosen Produkten geführt, die sich speziell auf IoT-Belange konzentrieren, beispielsweise [Azure IoT Hub](/azure/iot-hub). Die serverlose Architektur automatisiert Aufgaben wie Geräteregistrierung, Richtlinienerzwingung, Nachverfolgung und sogar Bereitstellung von Code auf Geräten in der *Edge-Umgebung*. „Edge“ bezieht sich auf Geräte wie Sensoren und Aktoren, die zwar mit dem Internet verbunden, aber kein aktiver Teil davon sind.

>[!div class="step-by-step"]
>[Zurück](architecture-approaches.md)
>[Weiter](serverless-architecture-considerations.md)
