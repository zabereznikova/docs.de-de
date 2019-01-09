---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 9ba54dc1744751efe4efad04f829cccce1244e0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145673"
---
# <a name="ltwebhttpgt"></a>&lt;webHttp&gt;
Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an. Dieses Verhalten, bei der Verwendung in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standardbindung, aktiviert das Webprogrammiermodell für einen Windows Communication Foundation (WCF)-Dienst.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<Verhalten >  
\<WebHttp >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format. Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen. Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.|  
|defaultBodyStyle|Gibt den Standardtextstil der zurückgegebenen Nachrichten an. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Web.WebMessageBodyStyle> und [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Gibt das Standardformat für ausgehende Antwortnachrichten an. Weitere Informationen finden Sie unter [WCF Web-HTTP-Formatierung](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Ruft das Flag ab bzw. legt das Flag fest, das angibt, ob ein FaultException-Element generiert wird, wenn ein interner Serverfehler (HTTP-Statuscode: 500) auftritt.|  
|helpEnabled|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob die Hilfeseite aktiviert ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt den Satz an Endpunktverhalten an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [AJAX-Integration und JSON-Unterstützung](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
