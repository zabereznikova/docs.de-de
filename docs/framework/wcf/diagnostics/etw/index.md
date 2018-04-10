---
title: Analytische Ablaufverfolgung per ETW
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a>Analytische Ablaufverfolgung per ETW
Mit der analytischen Ablaufverfolgung von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] können Sie die Diagnoseinformationen während der Ausführung eines [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Diensts erfassen. Die Ereignisse der analytischen Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] werden im [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Stapel an wichtigen Punkten ausgegeben, um in einer Produktionsumgebung die Problembehandlung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Diensten zu ermöglichen. Analytische Ablaufverfolgung für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Dienste hat minimale Auswirkungen auf die Leistung eines produktservers, der als Host [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Diensten wie diese Ereignisse sehr effizient in eine Sitzung für Event Tracing for Windows (ETW) ausgegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die analytische Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Erläutert, wie die analytische Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] funktioniert.  
  
 [Dynamisches Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.  
  
 [Konfigurieren der Ablaufverfolgung des Nachrichtenflusses](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.  
  
 [Ereignisreferenz der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
