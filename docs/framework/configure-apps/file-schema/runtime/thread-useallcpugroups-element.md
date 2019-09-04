---
title: <Thread_UseAllCpuGroups>-Element
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e964f1b2861926803b0449be06cbfd9567ac74a3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252275"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups >-Element

Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**  

## <a name="syntax"></a>Syntax

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob verwaltete Threads von der Laufzeit auf alle CPU-Gruppen verteilt werden.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Verwaltete Threads werden von der Laufzeit nicht auf mehrere CPU-Gruppen verteilt. Dies ist die Standardeinstellung.|
|`true`|Die Laufzeit verteilt verwaltete Threads auf mehrere CPU-Gruppen, wenn der Computer über mehrere CPU-Gruppen verfügt und das [ \<gccpugroup->](gccpugroup-element.md) Element aktiviert ist.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Hinweise

Wenn ein Computer über mehrere CPU-Gruppen verfügt, wird durch Aktivieren dieses Elements die Laufzeit angewiesen, verwaltete Threads auf alle CPU-Gruppen zu verteilen. Um dieses Feature verwenden zu können, müssen Sie auch das [ \<> Element gccpugroup](gccpugroup-element.md) aktivieren, das Garbage Collection auf alle CPU-Gruppen erweitert und beim Erstellen und Ausgleichen von Heaps alle Kerne berücksichtigt. Zum Aktivieren des [ \<gccpugroup->](gccpugroup-element.md) Elements muss das [ \<gcserver->](gcserver-element.md) Element aktiviert werden. Wenn diese Elemente nicht aktiviert sind, hat das Aktivieren des Elements `<Thread_UseAllCpuGroups>` keine Auswirkungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird dargestellt, wie Unterstützung für mehrere CPU-Gruppen aktiviert wird.

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [\<Gccpugroup-> Element](gccpugroup-element.md)
