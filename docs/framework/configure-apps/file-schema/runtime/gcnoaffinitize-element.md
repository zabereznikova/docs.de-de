---
title: Gcnoaffinitize-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978414"
---
# <a name="gcnoaffinitize-element"></a>\<gcnoaffinitize > Element

Gibt an, ob Server-GC-Threads mit CPUs verknüpft werden oder nicht.

\<Konfigurations > \
&nbsp;&nbsp;\<Lauf Zeit > \
&nbsp;&nbsp;&nbsp;&nbsp;\<gcnoaffinitize >

## <a name="syntax"></a>Syntax

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br />Gibt an, ob Server-GC-Threads/Heaps den auf dem Computer verfügbaren Prozessoren zugeordnet werden.|

#### <a name="enabled-attribute"></a>aktiviertes Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Affininitialisiert Server-GC-Threads mit CPUs. Dies ist die Standardeinstellung.|
|`true`|Fügt Server-GC-Threads nicht mit CPUs zu.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Hinweise

Standardmäßig sind Server-GC-Threads mit ihren jeweiligen CPUs hart miteinander initialisiert. Jeder verfügbare Prozessor des Systems verfügt über einen eigenen GC-Heap und-Thread. Dies ist in der Regel die bevorzugte Einstellung, da Sie die Cache Verwendung optimiert. Beginnend mit .NET Framework 4.6.2, indem das `enabled`-Attribut des **gcnoaffinitize** -Elements auf `false`festgelegt wird, können Sie angeben, dass Server-GC-Threads und-CPUs nicht eng gekoppelt werden sollen.

Sie können das **gcnoaffinitize** -Konfigurationselement allein angeben, um Server-GC-Threads nicht mit CPUs zu ordnen. Sie können es auch zusammen mit dem [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Heaps und-Threads zu steuern, die von einer Anwendung verwendet werden.

Wenn das `enabled`-Attribut des **gcnoaffinitize** -Elements `false` (der Standardwert) ist, können Sie auch das [gcheapcount](gcheapcount-element.md) -Element verwenden, um die Anzahl der GC-Threads und Heaps anzugeben, zusammen mit dem [gcheapaffinitizemask](gcheapaffinitizemask-element.md) -Element, um die Prozessoren anzugeben, denen die GC-Threads und Heaps zugeordnet sind.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden Server-GC-Threads nicht hart zugeordnet:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 begrenzt:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Gcheapaffinitizemask-Element](gcheapaffinitizemask-element.md)
- [Gcheapcount-Element](gcheapcount-element.md)
- [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
