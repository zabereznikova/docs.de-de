---
title: '&lt;DNS&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 6125bf157d04a1b0298a183465d11a18ac3786f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltdnsgt"></a>&lt;DNS&gt;
Gibt die erwartete Identität des Servers an. Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält. Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.  
  
 Weitere Informationen zum Festlegen des Werts Element finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<identity>  
\<DNS >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Wert|Der DNS des Zertifikats. DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen. Benutzer können die Anzeigenamen, wie z. B. merken [ http://go.microsoft.com/fwlink/?prd=10929 ](http://go.microsoft.com/fwlink/?prd=10929) oder [ http://go.microsoft.com/fwlink/?LinkID=96165 ](http://go.microsoft.com/fwlink/?LinkID=96165), leichter merken als zahlenbasierte Adressen, beispielsweise 207.46.131.137.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
