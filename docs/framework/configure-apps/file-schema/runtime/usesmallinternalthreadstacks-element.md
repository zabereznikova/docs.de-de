---
title: '&lt;UseSmallInternalThreadStacks&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2558423b412333a4d6ac9f650ad8ff3dab449d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt; Element
Fordert an, dass die common Language Runtime (CLR) Speicher reduzieren verwenden, indem Sie explizite Stack-Größe angeben, wenn es bestimmte Threads, die sie intern verwendet erstellt, anstatt die Standardgröße des Stapel für diese Threads.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<UseSmallInternalThreadStacks >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob anfordern, die die CLR verwenden expliziter Stapelgrößen statt die standardmäßige Stapelgröße, wenn sie bestimmte Threads erstellt, die intern verwendet. Die explizite Stapelgrößen sind kleiner als die Standardstapelgröße 1 MB.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Anforderungsgrößen Sie explizite Stapel.|  
|false|Verwenden Sie die Standardgröße des Stapel an. Dies ist die Standardeinstellung für die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselements wird verwendet, um reduzierte virtueller Arbeitsspeicher-Verwendung in einem Prozess anzufordern, da die expliziten Threadgrößen, die die CLR für die internen Threads verwendet werden, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße sind.  
  
> [!IMPORTANT]
>  Dieses Element ist eine Anforderung an die CLR anstatt eine zwingende Voraussetzung nicht erfüllt. In der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], die Anforderung wird nur für die X86 berücksichtigt Architektur. Dieses Element möglicherweise in künftigen Versionen der CLR vollständig ignoriert, oder durch explizite Stack-Größe, die immer für ausgewählte interne Threads verwendet werden ersetzt werden.  
  
 Angeben, dass dieses Konfigurationselements Geschäftsbeziehungen Zuverlässigkeit kleiner virtueller Arbeitsspeicher verwendet, wenn die CLR die Anforderung berücksichtigt da kleinere Stapel potenziell Stapel vornehmen können führt zu einem Überlauf wahrscheinlicher ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie um anzufordern, dass die CLR verwenden explizite Stapel für bestimmte Threads Größen, die intern verwendet wird.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
