---
title: '&lt;add&gt; von &lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 516c615248c95ef3107664b996f457fb80b46373
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;add&gt; von &lt;baseAddresses&gt;
Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.  
  
 \<System. ServiceModel >  
\<Client >  
\<Endpunkt >  
\<Host >  
\<BaseAddresses >  
\<BaseAddress-Element >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`baseAddress`|Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<BaseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Eine Auflistung von `baseAddress`-Elementen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
