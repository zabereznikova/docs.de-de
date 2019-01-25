---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: d84184febd6db3f233aae6fe558b8e0f50a9cb82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608835"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
