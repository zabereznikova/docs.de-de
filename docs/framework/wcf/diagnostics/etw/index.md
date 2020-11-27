---
title: Analytische Ablaufverfolgung per ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4bb31eeac7c5d3c8c30f66090b07de9f8af4d5a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274620"
---
# <a name="analytic-tracing-with-etw"></a>Analytische Ablaufverfolgung per ETW

Die analytische Ablauf Verfolgung von Windows Communication Foundation (WCF) bietet eine Möglichkeit zum Erfassen von Diagnoseinformationen während der Ausführung eines WCF-Dienstanbieter. WCF-analytische Ablauf Verfolgungs Ereignisse werden an wichtigen Punkten im WCF-Stapel ausgegeben, um die Problembehandlung von WCF-Diensten in einer Produktionsumgebung zu ermöglichen. Die analytische Ablauf Verfolgung für WCF-Dienste wirkt sich nur minimal auf die Leistung eines Produkt Servers aus, der WCF-Dienste hostet, [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] da diese Ereignisse sehr effizient an eine Ereignis Ablauf Verfolgung für Windows (ETW)-Sitzung ausgegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Übersicht über die analytische Ablaufverfolgung](analytic-tracing-overview.md)  
 Erläutert, wie die analytische WCF-Ablauf Verfolgung in funktioniert [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .  
  
 [Dynamisches Aktivieren der analytischen Ablaufverfolgung](dynamically-enabling-analytic-tracing.md)  
 Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.  
  
 [Konfigurieren der Ablaufverfolgung des Nachrichtenflusses](configuring-message-flow-tracing.md)  
 Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.  
  
 [Ereignisverweis der analytischen Ablaufverfolgung](analytic-trace-event-reference.md)  
 Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
