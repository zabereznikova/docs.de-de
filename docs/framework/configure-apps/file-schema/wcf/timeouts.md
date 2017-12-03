---
title: '&lt;timeOuts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da80ab797078e1fe912ccbfff07d7fb2da49664e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttimeoutsgt"></a>&lt;timeOuts&gt;
Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.  
  
 \<System. ServiceModel >  
\<Client >  
\<Endpunkt >  
\<Host >  
\<TimeOuts >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das für das Schließen des Diensthosts zulässige Zeitintervall angibt.|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das für das Öffnen des Diensthosts zulässige Zeitintervall angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Host >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
