---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e86b69b7d633fd99728936070e94da964e16de58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcallbacktimeoutsgt"></a>&lt;callbackTimeouts&gt;
Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<CallbackTimeOuts >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`transactionTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen. Die Standardeinstellung ist "00: 00:00".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
