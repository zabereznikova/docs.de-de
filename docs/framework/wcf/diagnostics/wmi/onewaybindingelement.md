---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47de8c2449c46b12b8d10ac2a5269a18d1454f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Klasse OneWayBindingElement definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Datentyp: ChannelPoolSettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Kanalpool-Einstellungen.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von akzeptierten Kanälen.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob das Paket geroutet werden kann.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
