---
title: 'Azure Logic Apps: Serverlose Apps'
description: Azure Logic Apps ermöglicht das Erstellen automatisierter skalierbarer Workflows, die Apps und Daten übergreifend in Clouddienste und lokale Systeme integrieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 11fdf5b5f176eb0d66eee6dde7638d3eae1e1f55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171844"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic Apps](/azure/logic-apps) bietet eine serverlose Engine zum Erstellen automatisierter Workflows zur Integration von Anwendungen und Daten zwischen Clouddiensten und lokalen Systemen. Workflows werden mithilfe eines visuellen Designers erstellt. Sie können Workflows auf der Grundlage von Ereignissen oder Timern auslösen, Connectors für Integrationsanwendungen nutzen und B2B-Kommunikation (Business-to-Business) ermöglichen. Logic Apps ist nahtlos in Azure Functions integriert.

![Azure Logic Apps-Logo](./media/logic-apps-logo.png)

Logic Apps können weitaus mehr, als nur Ihre Clouddienste (z.B. Funktionen) mit Cloudressourcen (wie Warteschlangen und Datenbanken) zu verbinden. Sie können auch lokale Workflows mit dem lokalen Gateway orchestrieren. Beispielsweise können Sie die Logik-App verwenden, um eine lokal gespeicherte SQL-Prozedur als Reaktion auf ein cloudbasiertes Ereignis oder bedingte Logik in Ihrem Workflow auszulösen. Erfahren Sie mehr über das [Herstellen einer Verbindung mit lokalen Datenquellen mit dem lokalen Azure-Datengateway](/azure/analysis-services/analysis-services-gateway).

![Logic Apps-Architektur](./media/logic-apps-architecture.png)

Wie Azure Functions starten Sie Logik-App-Workflows mit einem Trigger. Es gibt viele Trigger, aus denen Sie wählen können. Die folgende Abbildung zeigt nur einige der beliebtesten von Hunderten, die verfügbar sind.

![Logic Apps-Trigger](./media/logic-app-triggers.png)

Nachdem die App ausgelöst wurde, können Sie den visuellen Designer verwenden, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen. Alle Daten, die in einem vorherigen Schritt erfasst wurden, können in nachfolgenden Schritten verwendet werden. Der folgende Workflow lädt URLs aus einer CosmosDB-Datenbank. Er findet URLs mit dem Host `t.co` und sucht dann auf Twitter nach diesen. Wenn entsprechende Tweets gefunden werden, aktualisiert er die Dokumente mit den zugehörigen Tweets, indem eine Funktion aufgerufen wird.

![Logik-App-Workflow](./media/logic-app-workflow.png)

Das Logic Apps-Dashboard zeigt den Verlauf der Ausführung Ihrer Workflows an und ob jede Ausführung erfolgreich abgeschlossen wurde. Sie können zu jeder beliebigen Ausführung navigieren und die von den einzelnen Schritten verwendeten Daten zur Problembehandlung untersuchen. Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können und die sich gut für komplexe Unternehmensworkflows eignen.

Weitere Informationen finden Sie unter [Azure Logic Apps](/azure/logic-apps).

>[!div class="step-by-step"]
>[Zurück](application-insights.md)
>[Weiter](event-grid.md)
