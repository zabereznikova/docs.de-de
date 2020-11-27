---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269014"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement

PeerTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die IP-Adresse, auf der der Peerknoten Meldungen abhört.  
  
### <a name="port"></a>Port  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerkanalnachrichten verarbeitet.  
  
### <a name="security"></a>Sicherheit  

 Datentyp: PeerSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Peertransportsicherheitseinstellungen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
