---
title: Kanalklasse
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197872"
---
# <a name="channel-class"></a>Kanalklasse
Kanal  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Kanalklasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Kanalklasse verfügt über die folgenden Eigenschaften.  
  
### <a name="localaddress"></a>LocalAddress  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der lokale Endpunkt für den Kanal.  
  
### <a name="ref"></a>ref  
 Datentyp: Endpunkt  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die dem Kanal zugeordnete Remoteadresse.  
  
### <a name="sessionid"></a>SessionId  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die aktuelle Sitzungs-ID (sofern vorhanden).  
  
### <a name="type"></a>Typ  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Kanaltyp.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.ChannelBase>
