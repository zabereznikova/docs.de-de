---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: fa14d4606303b2d67cf5ef845d428bb086680204
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938965"
---
# <a name="synchronousreceive-element"></a>\<synchronousreceive-> Element
Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet. Es enthält keine Attribute oder untergeordnete Elemente.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<synchronousreceive->  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden. Windows Communication Foundation (WCF) gibt für jeden akzeptierten Kanal einen neuen Thread für die Verschiebung aus. Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
