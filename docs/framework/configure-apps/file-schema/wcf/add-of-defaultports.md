---
title: '&lt;add&gt; von &lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2aa63c7a5e730b2fb45f614cb2fe5f88444cee4a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a>&lt;add&gt; von &lt;defaultPorts&gt;
Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<ServiceBehaviors >  
\<Verhalten >  
\<UseRequestHeadersForMetadataAddress >  
\<DefaultPorts >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Port|Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.|  
|scheme|Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DefaultPorts >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
