---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: f7349bf61082c5d8e5bd4249e01b8835a1861cb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934262"
---
# <a name="privacynoticeat"></a>\<privacyNoticeAt>
Stellt ein Konfigurationselement dar, das einen in der `wsFederationHttp`-Bindung verwendeten Datenschutzhinweis angibt.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<privacyNotice>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`url`|Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.|  
|`version`|Eine ganze Zahl, die die Version dieses Datenschutzhinweises angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
