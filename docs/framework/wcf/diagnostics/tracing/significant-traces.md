---
title: Bedeutende Ablaufverfolgungen
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 2dc5010874285ba14dae625fcbf92740eb1707b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen
In diesem Thema werden einige der hauptablaufverfolgungen ausgegeben, von der Windows Communication Foundation (WCF) aufgelistet.  
  
## <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen  
  
|Ablaufverfolgung|Beschreibung|  
|-----------|-----------------|  
|Nachrichtenablaufverfolgung|Die Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht von der Nachrichtenprotokollierungsfunktion bei Aktivierung der `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle protokolliert wird. Durch  Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, die auch vom Attribut "Message Source" in der Nachrichtenprotokoll-Ablaufverfolgung angegeben werden.|  
|"Nachricht empfangen"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht empfangen wird, wenn die `System.ServiceModel`-Ablaufverfolgungsquelle auf der Stufe "Information" oder "Ausführlich" aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|"Nachricht gesendet"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Nachricht gesendet wird, sofern die `System.ServiceModel`-Ablaufverfolgungsquelle auf der Stufe Information oder Ausführlich aktiviert wurde. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|Abrufen von ChannelEndpointElement|Diese Ablaufverfolgung wird in einer Construct-Channel-Factory auf Informationsebene ausgegeben. Die Verfolgung beinhaltet eine Beschreibung des Endpunkts, mit dem der Client kommuniziert (Remoteadresse, Bindung, Vertragsname).|  
|Abrufen des ServiceElement|Diese Ablaufverfolgung wird im Construct-Diensthost auf Informationsebene ausgegeben. Sie liefert eine Beschreibung des Dienstvertrags und der Bindung.|  
|SocketConnection erstellen|Diese Ablaufverfolgung wird in der ersten "Verarbeiten"-Aktion, die vom Client durchgeführt wird, und in der "Bytes erhalten"-Aktivität im Dienst ausgegeben. Sie liefert die lokalen und remoten IP-Adressen. Sie wird auf Informationsebene ausgegeben.|
