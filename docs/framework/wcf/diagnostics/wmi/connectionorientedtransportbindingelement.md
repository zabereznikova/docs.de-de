---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 5ec2ae0db7239ff0c376ab4a8f050cc4f1df4f71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683970"
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die ConnectionOrientedTransportBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die ConnectionOrientedTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zeitraum, der angibt, wie viel Zeit für die Durchführung der Kanalinitialisierung aufgewendet werden kann, bevor eine Zeitüberschreitung vorliegt.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Puffergröße, die zum Übertragen eines Teils der serialisierten Meldung vom Client oder Dienst verwendet wird.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Größe des zu verwendenden Puffers.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das maximale Zeitintervall, das als Teil einer Nachricht oder vollständigen Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender asynchroner Annahmethreads, die für die Verarbeitung eingehender Verbindungen beim Dienst zur Verfügung stehen.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl ausstehender Verbindungen.  
  
### <a name="transfermode"></a>TransferMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
