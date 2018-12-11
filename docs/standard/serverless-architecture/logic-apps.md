---
title: Azure Logic Apps – serverlose apps
description: Mit Azure Logic Apps ermöglichen die Entwicklung automatisierter skalierbarer Workflows, die apps integrieren und Daten übergreifend in Clouddienste und lokalen Systemen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 14670a8459db3b80b8fbe3139c2675321cf9592c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147947"
---
# <a name="azure-logic-apps"></a>Azure-Logik-Apps

[Mit Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) bietet eine serverlose-Engine zum Erstellen von automatisierten Workflows zum Integrieren von apps und Daten zwischen Cloud-Diensten und lokalen Systemen. Erstellen Sie Workflows, die mit einem visuellen Designer. Sie können basierend auf Ereignisse oder Timer und Connectors nutzen integrationsanwendungen Workflows auslösen und erleichtern die Kommunikation von Business-to-Business (B2B). Logik-Apps integriert sich nahtlos mit Azure Functions.

![Azure Logic Apps-logo](./media/logic-apps-logo.png)

Logik-Apps mit Cloud-Ressourcen (z. B. Warteschlangen und -Datenbanken) ist mehr als verbinden Sie einfach auf Ihre Cloud-Dienste (z. B. Funktionen) möglich. Sie können auch auf lokale Workflows mit dem lokalen Gateway orchestrieren. Die Logik-App können Sie beispielsweise eine lokale SQL gespeicherten Prozedur als Reaktion auf eine Cloud-basierten-Ereignis oder bedingte Logik in Ihrem Workflow auslösen. Erfahren Sie mehr über [eine Verbindung mit lokalen Datenquellen mit Azure On-Premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Logik-Apps-Architektur](./media/logic-apps-architecture.png)

Wie Azure Functions beginnen Sie mit einem Trigger-Logik-App-Workflows ein. Es gibt viele Trigger für die Sie auswählen. Die folgende Erfassung zeigt einige der gängigeren werden von Hunderten, die verfügbar sind.

![Logik-Apps-Trigger](./media/logic-app-triggers.png)

Sobald die app ausgelöst wird, können Sie den visuellen Designer, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen. In einem vorherigen Schritt an erfassten Daten ist für die Verwendung in den nachfolgenden Schritten verfügbar. Der folgende Workflow lädt URLs aus einer CosmosDB-Datenbank. Diejenigen mit einer Vielzahl gefundenen `t.co` sucht sie auf Twitter. Wenn entsprechende Tweets gefunden wird, aktualisiert sie die Dokumente mit der entsprechenden Tweets durch Aufrufen der Funktion.

![Logik-App-workflow](./media/logic-app-workflow.png)

Die Logik-Apps-Dashboard zeigt den Verlauf der ausgeführten Workflows und gibt an, ob Ausführen jeder abgeschlossenen erfolgreich oder nicht. In einer bestimmten Ausführung navigieren können und überprüfen Sie die Daten, die einzelnen Schritte zur Problembehandlung verwendet werden. Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können, und eignen sich hervorragend für komplexe Enterprise-Workflows.

Weitere Informationen finden Sie unter [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).

>[!div class="step-by-step"]
>[Zurück](application-insights.md)
>[Weiter](event-grid.md)