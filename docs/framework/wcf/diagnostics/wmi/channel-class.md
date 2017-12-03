---
title: Kanalklasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a>Kanalklasse
Kanal  
  
## <a name="syntax"></a>Syntax  
  
```  
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
