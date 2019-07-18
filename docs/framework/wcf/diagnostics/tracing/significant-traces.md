---
title: Bedeutende Ablaufverfolgungen
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: c230c65b4d3fd45c4905d4ae5f4cbbf90e10faad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784949"
---
# <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen
Dieses Thema enthält einige der hauptablaufverfolgungen von Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Bedeutende Ablaufverfolgungen  
  
|Ablaufverfolgung|Beschreibung|  
|-----------|-----------------|  
|Nachrichtenablaufverfolgung|Die Ablaufverfolgung wird ausgegeben, wenn eine WCF-Nachricht von der nachrichtenprotokollierung angemeldet ist funktioln bei der `System.ServiceModel.MessageLogging` -Ablaufverfolgungsquelle aktiviert ist. Durch  Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, die auch vom Attribut "Message Source" in der Nachrichtenprotokoll-Ablaufverfolgung angegeben werden.|  
|"Nachricht empfangen"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine WCF-Nachricht empfangen wird, wenn die `System.ServiceModel` -Ablaufverfolgungsquelle Information oder Stufe ' ausführlich ' aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|"Nachricht gesendet"-Ablaufverfolgung|Diese Ablaufverfolgung wird ausgegeben, wenn eine WCF-Nachricht gesendet wird, wenn die `System.ServiceModel` -Ablaufverfolgungsquelle Information oder Stufe ' ausführlich ' aktiviert ist. Diese Ablaufverfolgung ist notwendig, um den Nachrichtenkorrelationspfeil in der Aktivitätsdiagrammansicht zu sehen.|  
|Abrufen von ChannelEndpointElement|Diese Ablaufverfolgung wird in einer Construct-Channel-Factory auf Informationsebene ausgegeben. Die Verfolgung beinhaltet eine Beschreibung des Endpunkts, mit dem der Client kommuniziert (Remoteadresse, Bindung, Vertragsname).|  
|Abrufen des ServiceElement|Diese Ablaufverfolgung wird im Construct-Diensthost auf Informationsebene ausgegeben. Sie liefert eine Beschreibung des Dienstvertrags und der Bindung.|  
|SocketConnection erstellen|Diese Ablaufverfolgung wird in der ersten "Verarbeiten"-Aktion, die vom Client durchgeführt wird, und in der "Bytes erhalten"-Aktivität im Dienst ausgegeben. Sie liefert die lokalen und remoten IP-Adressen. Sie wird auf Informationsebene ausgegeben.|
