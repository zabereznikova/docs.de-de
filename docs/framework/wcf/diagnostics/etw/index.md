---
title: Analytische Ablaufverfolgung per ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962044"
---
# <a name="analytic-tracing-with-etw"></a>Analytische Ablaufverfolgung per ETW
Analytische Ablaufverfolgung von Windows Communication Foundation (WCF) bietet eine Möglichkeit zum Erfassen von Diagnoseinformationen während der Ausführung eines WCF-Diensts. Analytische Ablaufverfolgung von WCF-Ereignisse werden an wichtigen Punkten im WCF-Stapel zum ermöglichen der Behebung von WCF-Dienste in einer produktionsumgebung ausgegeben. Analytische Ablaufverfolgung für WCF-Dienste hat nur minimale Auswirkungen auf die Leistung eines produktservers, der als Host [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF-Dienste wie diese Ereignisse sehr effizient in eine Sitzung für Event Tracing for Windows (ETW) ausgegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die analytische Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Erläutert, wie die analytische Ablaufverfolgung von WCF in funktioniert [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Dynamisches Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.  
  
 [Konfigurieren der Ablaufverfolgung des Nachrichtenflusses](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.  
  
 [Ereignisreferenz der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
