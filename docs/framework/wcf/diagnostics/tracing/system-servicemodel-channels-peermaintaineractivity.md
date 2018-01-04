---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ed8a5718bb4a3a070f39a0dca35e2fdbc78f1b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
Das PeerMaintainer-Modul führt einen bestimmten Vorgang (Details innerhalb des Ablaufverfolgungsnachrichtentexts) aus.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung tritt während verschiedener PeerMaintainer-Vorgänge auf.  
  
 PeerMaintainer ist eine interne Komponente von PeerNode. Jede Minute &#8211; oder nach 32&#160;empfangenen Nachrichten &#8211; wird eine LinkUtility-Nachricht an die Nachbarn gesendet. Diese Nachricht enthält eine Statistik mit der Anzahl der ausgetauschten Nachrichten sowie mit Informationen dazu, wie viele der Nachrichten nützlich waren (also keine Duplikate und nicht manipuliert). Dadurch lässt sich das Verknüpfungsprogramm eines bestimmten Nachbarn ermitteln. Etwa alle fünf Minuten überprüft der Maintainer die Integrität der Nachbarverbindungen. Übersteigt die Anzahl von Nachbarverbindungen die Idealmenge, werden die am wenigsten nützlichen Verbindungen entfernt. Sind nicht genügend Verbindungen verfügbar, werden vom Maintainer neue Verbindungen eingerichtet.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
