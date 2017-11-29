---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cfb6981947b457d5fdad59e96bdcd6937b9abd02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltenablewebscriptgt"></a>&lt;enableWebScript&gt;
Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<EnableWebScript >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt den Satz an Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Verhalten sollte nur verwendet werden, zusammen mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung oder [ \<WebMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) Binding-Element.  Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [AJAX-Integration und JSON-Unterstützung](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<WebHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
