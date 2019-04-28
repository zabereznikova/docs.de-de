---
title: <gcServer>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd91cf0179ef9731c456b41fdc865e3eacdb33eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674154"
---
# <a name="gcserver-element"></a>\<GcServer >-Element
Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.  
  
 \<configuration>  
\<runtime>  
\<gcServer>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die Garbage Collection auf dem Server ausführt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Garbage Collection wird nicht auf dem Server ausgeführt. Dies ist die Standardeinstellung.|  
|`true`|Die Garbage Collection wird auf dem Server ausgeführt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime (CLR) unterstützt zwei Arten der Garbage Collection: die Garbage Collection auf der Arbeitsstation, die auf allen Systemen verfügbar ist, und die Garbage Collection auf dem Server, die auf Systemen mit mehreren Prozessoren verfügbar ist. Mit dem `<gcServer>`-Element steuern Sie die Art der von der CLR ausgeführten Garbage Collection. Mithilfe der <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>-Eigenschaft können Sie bestimmen, ob die Garbage Collection auf dem Server aktiviert ist.  
  
 Für Computer mit einem Prozessor stellt die Garbage Collection auf der Arbeitsstation (Standardeinstellung) in der Regel die schnellste Lösung dar. Auf Computern mit zwei Prozessoren kann die Arbeitsstation- oder die Serveroption verwendet werden. Sind mehr als zwei Prozessoren vorhanden, stellt die Garbage Collection auf dem Server in der Regel die schnellste Lösung dar.  
  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden. Wenn es in der Computerkonfigurationsdatei enthalten ist, wird es ignoriert.  
  
> [!NOTE]
>  In .NET Framework 4 und früheren Versionen ist die gleichzeitige Garbage Collection nicht verfügbar, wenn die Garbage Collection auf dem Server aktiviert ist. Ab [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] erfolgt die Garbage Collection auf dem Server gleichzeitig. Um Garbagecollection für nicht-parallele Server verwenden möchten, legen die `<gcServer>` Element `true` und die [ \<GcConcurrent >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) zu `false`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Garbage Collection auf dem Server aktiviert.  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Zum Deaktivieren der gleichzeitigen Garbagecollection](gcconcurrent-element.md#to-disable-background-garbage-collection)
