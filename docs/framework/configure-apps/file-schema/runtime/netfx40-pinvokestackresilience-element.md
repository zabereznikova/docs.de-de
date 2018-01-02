---
title: '&lt;NetFx40_PInvokeStackResilience&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b17816ee6134dc6b3074256093c0cba07419baf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a>&lt;NetFx40_PInvokeStackResilience&gt; Element
Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 \<configuration>  
\<Common Language Runtime >  
< NetFx40_PInvokeStackResilience >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit falsche Plattform erkennt Plattformaufrufdeklarationen und behebt den Stapel automatisch zur Laufzeit auf 32-Bit-Plattformen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`0`|Die Common Language Runtime verwendet schnellere Interop-Marshalling-Architektur eingeführt, die der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die nicht erkannt und Updates falscher Plattformaufrufdeklarationen. Dies ist die Standardeinstellung.|  
|`1`|Die Common Language Runtime verwendet langsamer Übergänge, die erkennt und korrigiert falsche Plattform Plattformaufrufdeklarationen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element können Sie schneller Interop-Marshalling für Laufzeit-robusten Schutz vor falsche Plattform Plattformaufrufdeklarationen abwägen.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], eine optimierte Interop-Marshalling-Architektur bietet eine deutliche leistungsverbesserung für Übergänge von verwaltetem Code an nicht verwalteten Code. In früheren Versionen von .NET Framework die Marshalling Ebene erkannt falsche Plattformaufrufmethode Deklarationen auf 32-Bit-Plattformen und den Stapel automatisch korrigiert. Die neue Architektur Marshalling entfällt dieser Schritt. Daher sind Übergänge sehr schnell, aber eine falsche Plattformaufruf Deklaration können einen Anwendung Fehler verursachen.  
  
 Um während der Entwicklung falsche Deklarationen erkennen zu erleichtern, wurde die Visual Studio debuggen verbessert. Die [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Assistent für verwaltetes Debuggen (MDA) benachrichtigt Sie falsche Plattform Deklarationen aufgerufen wird, wenn Ihre Anwendung mit dem angefügten Debugger ausgeführt wird.  
  
 Adresse Szenarien, in denen Ihre Anwendung Komponenten verwendet, die nicht neu kompilieren und, dass wurden falsche Plattformaufrufdeklarationen, Sie können, die `NetFx40_PInvokeStackResilience` Element. Die Konfigurationsdatei der Anwendung mit diesem Element hinzugefügt `enabled="1"` "OPTS" in einem Kompatibilitätsmodus mit dem Verhalten früherer Versionen von .NET Framework, allerdings zum Preis einer langsameren Übergängen. Assemblys, die auf früheren Versionen von .NET Framework kompiliert wurden diesem Kompatibilitätsmodus werden automatisch festgelegt, und dieses Element ist nicht erforderlich.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel gezeigt ist wie erhöhte Stabilität gegen falsche aktiviert Plattformaufrufdeklarationen für eine Anwendung, allerdings zum Preis einer langsameren Übergänge zwischen verwalteten und nicht verwaltetem Code.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
