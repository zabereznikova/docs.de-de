---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962955"
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
 Datentyp: string (Zeichenfolge)  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
