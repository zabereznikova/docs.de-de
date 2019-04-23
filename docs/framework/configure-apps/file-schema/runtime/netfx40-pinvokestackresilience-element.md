---
title: <NetFx40_PInvokeStackResilience>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 725bd715f6e70dff08929e58d588a3d8561d5011
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224233"
---
# <a name="netfx40pinvokestackresilience-element"></a>\<NetFx40_PInvokeStackResilience >-Element
Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 \<configuration>  
\<runtime>  
<NetFx40_PInvokeStackResilience>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen erkennt Deklarationen und behebt automatisch auf 32-Bit-Plattformen zur Laufzeit den Stapel.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`0`|Die Common Language Runtime verwendet schneller Interop-Marshalling-Architektur eingeführt, die der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die nicht erkannt und Korrektur falsche Plattformaufrufdeklarationen. Dies ist die Standardeinstellung.|  
|`1`|Die Common Language Runtime verwendet langsameren Übergängen, die Erkennung und Behebung fehlerhafter Plattformaufrufdeklarationen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element können Sie eine Abstimmung zwischen schneller interop-Marshalling für Laufzeit resilienz gegen fehlerhafter Plattformaufruf Deklarationen.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], eine optimierte Interop-Marshalling-Architektur bietet eine deutliche leistungsverbesserung für Übergänge von verwaltetem Code an nicht verwalteten Code. In früheren Versionen von .NET Framework das Marshalling Ebene erkannt falsch Plattformaufrufmethode Deklarationen auf 32-Bit-Plattformen und automatisch korrigiert den Stapel. Die neue Architektur für Marshalling entfällt dieser Schritt. Daher sind Übergänge sehr schnell, aber es wird eine falsche Plattform aufrufen Deklaration einen Programmfehler verursachen können.  
  
 Um falsche Deklarationen zu erkennen, während der Entwicklung zu erleichtern, wurde der Visual Studio-Debuggingumgebung verbessert. Die [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggens (MDA) informiert Sie über falschen Deklarationen aufrufen, wenn Ihre Anwendung mit dem angefügten Debugger ausgeführt wird.  
  
 Szenarien, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren, und haben falsche Plattformaufrufdeklarationen, können Sie verwenden, die `NetFx40_PInvokeStackResilience` Element. Die Konfigurationsdatei der Anwendung mit diesem Element hinzugefügt `enabled="1"` "OPTS" in einem Kompatibilitätsmodus, mit dem Verhalten früherer Versionen von .NET Framework, was zu langsameren Übergängen. Assemblys, die auf früheren Versionen von .NET Framework kompiliert wurden, werden automatisch von der Teilnahme in diesem Kompatibilitätsmodus, und dieses Element ist nicht erforderlich.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel gezeigt ist wie für höhere resilienz gegen falsche optionale Plattformaufrufe Deklarationen für eine Anwendung, was zu langsameren Übergängen zwischen verwalteten und nicht verwaltetem Code.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
