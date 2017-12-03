---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bb730a00358f771408ff0431ff2ab77623354a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbackdebuggt"></a>&lt;callbackDebug&gt;
Legt Dienstdebugging für ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Rückrufobjekt fest.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<CallbackDebug >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.<br /><br /> Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren. **Vorsicht:** zurückgeben, verwaltete Ausnahmeinformationen an Clients kann ein Sicherheitsrisiko sein. Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
