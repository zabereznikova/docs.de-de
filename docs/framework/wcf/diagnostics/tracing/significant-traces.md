---
title: Bedeutende Ablaufverfolgungen
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 9ad7c217b528cb2ad22169c1aea6391462bab1ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248669"
---
# <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen

In diesem Thema werden einige der wichtigsten Ablauf Verfolgungen aufgelistet, die von Windows Communication Foundation (WCF) ausgegeben werden.  
  
## <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen  
  
|Trace|BESCHREIBUNG|  
|-----------|-----------------|  
|Nachrichtenablaufverfolgung|Die Ablauf Verfolgung wird ausgegeben, wenn eine WCF-Nachricht von der Nachrichten Protokollierungsfunktion protokolliert wird, wenn die Ablauf `System.ServiceModel.MessageLogging` Verfolgungs Quelle aktiviert ist. Durch  Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, die auch vom Attribut "Message Source" in der Nachrichtenprotokoll-Ablaufverfolgung angegeben werden.|  
|"Nachricht empfangen"-Ablaufverfolgung|Diese Ablauf Verfolgung wird ausgegeben, wenn eine WCF-Nachricht empfangen wird, wenn die Ablauf `System.ServiceModel` Verfolgungs Quelle auf Information-oder ausführliche-Ebene aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|"Nachricht gesendet"-Ablaufverfolgung|Diese Ablauf Verfolgung wird ausgegeben, wenn eine WCF-Nachricht gesendet wird, wenn die Ablauf `System.ServiceModel` Verfolgungs Quelle auf Information-oder ausführliche-Ebene aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|Abrufen von ChannelEndpointElement|Diese Ablaufverfolgung wird in einer Construct-Channel-Factory auf Informationsebene ausgegeben. Die Verfolgung beinhaltet eine Beschreibung des Endpunkts, mit dem der Client kommuniziert (Remoteadresse, Bindung, Vertragsname).|  
|Abrufen des ServiceElement|Diese Ablaufverfolgung wird im Construct-Diensthost auf Informationsebene ausgegeben. Sie liefert eine Beschreibung des Dienstvertrags und der Bindung.|  
|SocketConnection erstellen|Diese Ablaufverfolgung wird in der ersten "Verarbeiten"-Aktion, die vom Client durchgeführt wird, und in der "Bytes erhalten"-Aktivität im Dienst ausgegeben. Sie liefert die lokalen und remoten IP-Adressen. Sie wird auf Informationsebene ausgegeben.|
