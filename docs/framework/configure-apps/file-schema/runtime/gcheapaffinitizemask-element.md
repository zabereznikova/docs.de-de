---
title: Gcheapaffinitizemask-Element
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978420"
---
# <a name="gcheapaffinitizemask-element"></a>\<gcheapaffinitizemask > Element

Definiert die Affinität zwischen GC-Heaps und einzelnen Prozessoren.

\<Konfigurations > \
&nbsp;&nbsp;\<Lauf Zeit > \
&nbsp;&nbsp;&nbsp;&nbsp;\<gcheapaffinitizemask >

## <a name="syntax"></a>Syntax

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br />Gibt die Affinität zwischen GC-Heaps und einzelnen Prozessoren an. |

#### <a name="enabled-attribute"></a>aktiviertes Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`nnnn`|Ein Dezimalwert, der eine Bitmaske bildet, die die Affinität zwischen Server-GC-Heaps und einzelnen Prozessoren definiert. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Hinweise

Standardmäßig werden Server-GC-Threads mit ihrer jeweiligen CPU hart verknüpft, sodass ein GC-Heap, ein Server-GC-Thread und ein Thread Server-GC-Thread für jeden Prozessor vorhanden ist. Beginnend mit .NET Framework 4.6.2 können Sie das **gcheapaffinitizemask** -Element verwenden, um die Affinität zwischen Server-GC-Heaps und-Prozessoren zu steuern, wenn die Anzahl der Heaps durch das **gcheapcount** -Element begrenzt ist.

**Gcheapaffinitizemask** wird in der Regel zusammen mit zwei anderen Flags verwendet:

- [Gcnoaffinitize](gcnoaffinitize-element.md): steuert, ob Server-GC-Threads/Heaps mit CPUs verknüpft sind. Das `enabled`-Attribut des [gcnoaffinitize](gcnoaffinitize-element.md) -Elements muss `false` (sein Standardwert) für die zu verwendende **gcheapaffinitizemask** -Einstellung sein.

- [Gcheapcount](gcheapcount-element.md): schränkt die Anzahl von Heaps ein, die vom Prozess für Server-GC verwendet werden. Standardmäßig gibt es für jeden Prozessor einen Heap.

**nnnn** ist eine Bitmaske, die als Dezimalwert ausgedrückt wird. Bit 0 von Byte 0 stellt den Prozessor 0 dar, Bit 1 von Byte 0 steht für Prozessor 1 usw. Beispiel:

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

Der Wert 1023 ist 0x3ff oder 0011 1111 1111b. Der Prozess verwendet 10 Prozessoren von Prozessor 0 bis Prozessor 9.

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

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Gcnoaffinitize-Element](gcnoaffinitize-element.md)
- [Gcheapcount-Element](gcheapcount-element.md)
- [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
