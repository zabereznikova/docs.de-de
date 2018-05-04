---
title: '&lt;synchronousReceive&gt;-Element'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: af1ca2ee1fe3c03c33f05e0c30c7b843b3720a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsynchronousreceivegt-element"></a>&lt;synchronousReceive&gt;-Element
Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet. Es enthält keine Attribute oder untergeordnete Elemente.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<Verhalten >  
\<SynchronousReceive >  
  
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
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden. Windows Communication Foundation (WCF) gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal. Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
