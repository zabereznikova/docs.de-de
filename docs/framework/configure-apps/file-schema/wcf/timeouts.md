---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 8a8a352380fe6eedb41ead089405e7b79fad29fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272774"
---
# <a name="timeouts"></a>\<timeOuts>
Stellt ein Konfigurationselement dar, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host>  
\<timeOuts>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
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
|[\<host>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Ein Konfigurationselement, das Einstellungen für einen Diensthost angibt.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
