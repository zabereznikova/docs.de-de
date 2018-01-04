---
title: Bedeutende Ablaufverfolgungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6641fe633585caf6cbf068a804430f9171e5ece0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen
Dieses Thema führt einige der Hauptablaufverfolgungen auf, die von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ausgegeben werden.  
  
## <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen  
  
|Ablaufverfolgung|Beschreibung|  
|-----------|-----------------|  
|Nachrichtenablaufverfolgung|Die Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht von der Nachrichtenprotokollierungsfunktion bei Aktivierung der `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle protokolliert wird. Durch  Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, die auch vom Attribut "Message Source" in der Nachrichtenprotokoll-Ablaufverfolgung angegeben werden.|  
|"Nachricht empfangen"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht empfangen wird, wenn die `System.ServiceModel`-Ablaufverfolgungsquelle auf der Stufe "Information" oder "Ausführlich" aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|"Nachricht gesendet"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht gesendet wird, sofern die `System.ServiceModel`-Ablaufverfolgungsquelle auf der Stufe Information oder Ausführlich aktiviert wurde. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|Abrufen von ChannelEndpointElement|Diese Ablaufverfolgung wird in einer Construct-Channel-Factory auf Informationsebene ausgegeben. Die Verfolgung beinhaltet eine Beschreibung des Endpunkts, mit dem der Client kommuniziert (Remoteadresse, Bindung, Vertragsname).|  
|Abrufen des ServiceElement|Diese Ablaufverfolgung wird im Construct-Diensthost auf Informationsebene ausgegeben. Sie liefert eine Beschreibung des Dienstvertrags und der Bindung.|  
|SocketConnection erstellen|Diese Ablaufverfolgung wird in der ersten "Verarbeiten"-Aktion, die vom Client durchgeführt wird, und in der "Bytes erhalten"-Aktivität im Dienst ausgegeben. Sie liefert die lokalen und remoten IP-Adressen. Sie wird auf Informationsebene ausgegeben.|
