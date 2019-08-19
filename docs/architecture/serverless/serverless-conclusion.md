---
title: Wichtige Annahmen-Server Lose apps
description: Serverless bietet viele Vorteile und hat seine eigenen Herausforderungen. Eine Zusammenfassung der wichtigsten Annahmen dieses Handbuchs.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ae9fc47bf07a7e28688942b856b4743ae7aadc36
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577243"
---
# <a name="conclusion"></a>Schlussbemerkung

Die folgenden wichtigen Annahmen sind die wichtigsten Schlussfolgerungen aus dieser Anleitung.

**Vorteile der Server losen Verwendung.** Server lose Lösungen bieten den wichtigen Vorteil der Kosteneinsparung, da Server lose Modelle in einem Modell mit Nutzungs basierter Bezahlung implementiert werden. Serverless ermöglicht das unabhängige skalieren, testen und Bereitstellen einzelner Komponenten Ihrer Anwendung. Serverless eignet sich für die Implementierung von microservicesarchitekturen und ist vollständig in eine devops-Pipeline integriert.

**Code als Bereitstellungs Einheit.** Server lose abstrahiert die Hardware, das Betriebssystem und die Laufzeit von der Anwendung Weg. Serverless ermöglicht das konzentrieren auf Geschäftslogik im Code als Bereitstellungs Einheit.

**Trigger und Bindungen.** Server lose erleichtert-Integration in Speicher, APIs und andere cloudressourcen. Azure Functions bietet Trigger zum Ausführen von Code und Bindungen für die Interaktion mit Ressourcen.

**Microservices.** Die microservices-Architektur wird zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf microservices basierenden Architektur wird die Anwendung als eine Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, versioniert, bereitgestellt und skaliert werden können. Serverless ist eine Architektur, die sich gut zum aufbauen dieser Dienste eignet.

**Server lose Plattformen.** Serverless ist nicht nur der Code. Plattformen, die Server lose Architekturen unterstützen, umfassen Server lose Workflows und Orchestrierung, Server Loses Messaging und Ereignis Dienste und Server lose Datenbanken.

**Server lose Herausforderungen.** Mit Server less werden Herausforderungen im Zusammenhang mit der Entwicklung verteilter Anwendungen eingeführt, wie z. b. fragmentierte und unabhängige Datenmodelle, Resilienz, Versionsverwaltung und Dienst Ermittlung. Serverless eignet sich möglicherweise nicht für Prozesse mit langer Ausführungsdauer oder für Komponenten, die von einer engeren Kopplung profitieren.

**Server loser als Tool, nicht die Toolbox.** Serverless ist nicht die exklusive Lösung für die Anwendungsarchitektur. Dabei handelt es sich um ein Tool, das als Teil einer Hybrid Anwendung genutzt werden kann, die herkömmliche Ebenen, monolithische Back-Ends und Container enthalten kann. Serverless kann verwendet werden, um vorhandene Lösungen zu verbessern, und stellt keinen all-oder Nothing-Ansatz für die Anwendungsentwicklung dar.

>[!div class="step-by-step"]
>[Vorherige](serverless-business-scenarios.md)
