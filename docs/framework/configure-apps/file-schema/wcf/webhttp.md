---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 795e61b9054d2ea9276970988018c50099bcbe17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129648"
---
# <a name="webhttp"></a>\<webHttp>
Dieses Element gibt anhand der Konfiguration <xref:System.ServiceModel.Description.WebHttpBehavior> in einem Endpunkt an. Dieses Verhalten, bei der Verwendung in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standardbindung, aktiviert das Webprogrammiermodell für einen Windows Communication Foundation (WCF)-Dienst.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<webHttp>  
  
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

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [AJAX-Integration und JSON-Unterstützung](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
