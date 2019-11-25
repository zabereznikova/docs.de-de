---
title: 'Wichtige Erkenntnisse: Serverlose Apps'
description: Der serverlose Ansatz bietet viele Vorteile und weist seine eigenen Herausforderungen auf. Eine Zusammenfassung der wichtigsten Erkenntnisse dieses Handbuchs.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ae9fc47bf07a7e28688942b856b4743ae7aadc36
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577243"
---
# <a name="conclusion"></a>Zusammenfassung

In diesem Artikel werden die wichtigsten Erkenntnisse dieses Leitfadens zusammengefasst.

**Vorteile der Verwendung einer serverlosen Lösung.** Serverlose Lösungen bieten den wichtigen Vorteil von Kosteneinsparungen, da serverlose Architekturen in einem Modell mit nutzungsbasierter Bezahlung implementiert werden. Der serverlose Ansatz ermöglicht das unabhängige Skalieren, Testen und Bereitstellen einzelner Komponenten Ihrer Anwendung. Ein serverloser Ansatz eignet sich für die Implementierung von Microservicesarchitekturen und kann vollständig in eine DevOps-Pipeline integriert werden.

**Code als Bereitstellungseinheit.** Eine serverlose Lösung abstrahiert die Hardware, das Betriebssystem und die Laufzeit von der Anwendung. Serverlos ermöglicht die Konzentration auf Geschäftslogik im Code als Bereitstellungseinheit.

**Trigger und Bindungen.** Der serverlose Ansatz erleichtert Integration in Speicher, APIs und andere Cloudressourcen. Azure Functions bietet Trigger zum Ausführen von Code und Bindungen für die Interaktion mit Ressourcen.

**Microservices.** Die Microservicesarchitektur wird zum bevorzugten Ansatz für verteilte und große oder komplexe unternehmenskritische Anwendungen, die auf mehreren unabhängigen Subsystemen in Form von autonomen Diensten basieren. In einer auf Microservices basierenden Architektur wird die Anwendung als Sammlung von Diensten erstellt, die unabhängig voneinander entwickelt, getestet, mit Versionsangaben versehen, bereitgestellt und skaliert werden. Serverlos ist eine Architektur, die sich gut zum Erstellen dieser Dienste eignet.

**Serverlose Plattformen.** Der serverlose Ansatz dreht sich nicht nur um Code. Plattformen, die serverlose Architekturen unterstützen, umfassen serverlose Workflows und Orchestrierung, serverloses Messaging und serverlose Ereignisdienste sowie serverlose Datenbanken.

**Herausforderungen eines serverlosen Ansatzes.** Bei einer serverlosen Lösung ergeben sich Herausforderungen im Zusammenhang mit der Entwicklung verteilter Anwendungen, z.B. fragmentierte und unabhängige Datenmodelle, Resilienz, Versionsverwaltung und Dienstermittlung. Ein serverloser Ansatz ist möglicherweise nicht ideal für zeitintensive Prozesse oder Komponenten geeignet, die von einer engeren Kopplung profitieren.

**Serverlose Lösung als Tool, nicht als Toolbox.** Eine serverlose Architektur ist keine exklusive Lösung für die Anwendungsarchitektur. Es handelt sich um ein Tool, das als Teil einer Hybridanwendung genutzt werden kann, die herkömmliche Schichten, monolithische Back-Ends und Container enthalten kann. Eine serverlose Lösung kann verwendet werden, um vorhandene Lösungen zu verbessern, und stellt keinen Ansatz des Typs „Alles oder nichts“ für die Anwendungsentwicklung dar.

>[!div class="step-by-step"]
>[Vorherige](serverless-business-scenarios.md)
