---
title: Gcheapcount-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283072"
---
# <a name="gcheapcount-element"></a>\<gcheapcount > Element

Gibt die Anzahl von Heaps/Threads an, die für Server Garbage Collection verwendet werden sollen.

\<Konfigurations > \
&nbsp;&nbsp;\<Lauf Zeit > \
&nbsp;&nbsp;&nbsp;&nbsp;\<gcheapcount >

## <a name="syntax"></a>Syntax

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br />Gibt die Anzahl von Heaps an, die für Server Garbage Collection verwendet werden sollen. Die tatsächliche Anzahl von Heaps ist die Mindestanzahl der von Ihnen angegebenen Heaps und der Anzahl der Prozessoren, die Ihr Prozess verwenden darf. |

#### <a name="enabled-attribute"></a>aktiviertes Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`nn`|Die Anzahl von Heaps, die für Server-GC verwendet werden sollen.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Hinweise

Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist. Ab .NET Framework 4.6.2 können Sie das **gcheapcount** -Element verwenden, um die Anzahl von Heaps einzuschränken, die von der Anwendung für die Server-GC verwendet werden. Das Einschränken der Anzahl von Heaps, die für Server GC verwendet werden, ist besonders nützlich für Systeme, die mehrere Instanzen einer Serveranwendung ausführen.

**Gcheapcount** wird in der Regel zusammen mit zwei anderen Flags verwendet:

- [Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind.

- [Gcheapaffinitizemask](gcheapaffinitizemask-element.md): steuert die Affinität von GC-Threads/Heaps mit CPUs.

Wenn **gcheapcount** festgelegt und **gcnoaffininitize** deaktiviert ist (Standardeinstellung), gibt es eine Affinität zwischen den *NN* -GC-Threads/Heaps und den ersten *NN* -Prozessoren. Sie können das **gcheapaffinitizemask** -Element verwenden, um anzugeben, welche Prozessoren von den Server-GC-Heaps des Prozesses verwendet werden. Andernfalls überschneidet sich die Prozessorauslastung, wenn mehrere Server Prozesse auf einem System ausgeführt werden.

Wenn **gcheapcount** festgelegt und **gcnoaffininitize** aktiviert ist, schränkt der Garbage Collector die Anzahl der Prozessoren ein, die für die Server-GC verwendet werden, aber keine GC-Heaps und-Prozessoren.

## <a name="example"></a>Beispiel

Das folgende Beispiel gibt an, dass eine Anwendung Server-GC mit 10 Heaps/Threads verwendet. Da Sie nicht möchten, dass sich diese Heaps mit Heaps von anderen Anwendungen auf dem System überlappen, verwenden Sie **gcheapaffinitizemask** , um anzugeben, dass der Prozess die CPUs 0 bis 9 verwenden soll.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

Im folgenden Beispiel werden Server-GC-Threads nicht zugeordnet und die Anzahl der GC-Heaps/Threads auf 10 beschränkt.

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
- [Gcnoaffinitize-Element](gcnoaffinitize-element.md)
- [Gcheapaffinitizemask-Element](gcheapaffinitizemask-element.md)
- [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
