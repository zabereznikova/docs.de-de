---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698459"
---
# <a name="xmlelement"></a>\<xmlElement>
Gibt ein XML-Element an, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.  
  
 \<system.ServiceModel>  
\<bindings>  
\<wsFederatedBinding>  
\<binding>  
\<security>  
\<message>  
\<tokenRequestParameters>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|xmlElement|Eine Zeichenfolge, die ein XML-Element angibt, das bei der Anforderung eines Tokens im Textkörper an den Sicherheitstokendienst gesendet wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|Eine Auflistung von Tokenanforderungsparametern. Jeder Parameter ist ein XML-Element.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
