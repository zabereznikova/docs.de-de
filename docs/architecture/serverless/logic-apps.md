---
title: Azure Logic apps Server Lose apps
description: Azure Logic apps ermöglichen das entwickeln automatisierter skalierbarer Workflows, die apps und Daten in Clouddienste und lokale Systeme integrieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577453"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic apps](https://docs.microsoft.com/azure/logic-apps) bietet eine Server lose Engine zum Erstellen automatisierter Workflows zum Integrieren von apps und Daten zwischen Cloud-Diensten und lokalen Systemen. Workflows werden mithilfe eines visuellen Designers erstellt. Sie können Workflows auf der Grundlage von Ereignissen oder Timern initiieren und Connectors für Integrationsanwendungen nutzen und die B2B-Kommunikation (Business-to-Business) vereinfachen. Logic apps nahtlos in Azure Functions integriert.

![Azure Logic apps Logo](./media/logic-apps-logo.png)

Logic Apps können mehr tun, als nur Ihre Clouddienste (z. b. Funktionen) mit cloudressourcen (wie Warteschlangen und Datenbanken) zu verbinden. Sie können auch lokale Workflows mit dem lokalen Gateway orchestrieren. Beispielsweise können Sie die Logik-App verwenden, um eine lokale gespeicherte SQL-Prozedur als Reaktion auf ein cloudbasiertes Ereignis oder eine bedingte Logik in Ihrem Workflow zu initiieren. Erfahren Sie mehr über das [Herstellen einer Verbindung mit lokalen Datenquellen mit dem lokalen Azure-Daten Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Logic apps-Architektur](./media/logic-apps-architecture.png)

Wie Azure Functions starten Sie Logik-App-Workflows mit einem-Triggern. Es gibt viele Trigger, aus denen Sie auswählen können. Die folgende Erfassung zeigt nur einige der gängigsten, die von Hunderten verfügbar sind.

![Logic apps Trigger](./media/logic-app-triggers.png)

Nachdem die APP ausgelöst wurde, können Sie den visuellen Designer verwenden, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen. Alle Daten, die in einem vorherigen Schritt erfasst wurden, können in nachfolgenden Schritten verwendet werden. Der folgende Workflow lädt URLs aus einer cosmosdb-Datenbank. Es findet diejenigen, die einen Host von `t.co` haben, und sucht dann auf Twitter nach diesen. Wenn entsprechende tweets gefunden werden, aktualisiert Sie die Dokumente mit den zugehörigen Tweets, indem eine Funktion aufgerufen wird.

![Logik-App-Workflow](./media/logic-app-workflow.png)

Das Logic Apps Dashboard zeigt den Verlauf der Ausführung Ihrer Workflows und ob jede Ausführung erfolgreich abgeschlossen wurde. Sie können zu jeder beliebigen Testlauf navigieren und die Daten überprüfen, die von den einzelnen Schritten zur Problembehandlung verwendet werden. Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können und die sich gut für komplexe Unternehmens Workflows eignen.

Weitere Informationen finden Sie unter [Azure Logic apps](https://docs.microsoft.com/azure/logic-apps).

>[!div class="step-by-step"]
>[Zurück](application-insights.md)
>[Weiter](event-grid.md)
