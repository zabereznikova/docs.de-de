---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 193000acf2f3c8a0eddb2552559ee40a0f5fced9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:  
  
### <a name="listenipaddress"></a>ListenIPAddress  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die IP-Adresse, auf der der Peerknoten Meldungen abhört.  
  
### <a name="port"></a>Port  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerchannel-Meldungen verarbeitet.  
  
### <a name="security"></a>Sicherheit  
 Datentyp: PeerSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Peertransportsicherheitseinstellungen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
