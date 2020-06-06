---
title: gcserver-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968950"
---
# <a name="gcserver-element"></a>\<gcServer>-Element

Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a>Syntax

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br />Gibt an, ob die Runtime die Garbage Collection auf dem Server ausführt.|

#### <a name="enabled-attribute"></a>aktiviertes Attribut

|Wert|BESCHREIBUNG|
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

## <a name="remarks"></a>Bemerkungen

Die Common Language Runtime (CLR) unterstützt zwei Arten der Garbage Collection: die Garbage Collection auf der Arbeitsstation, die auf allen Systemen verfügbar ist, und die Garbage Collection auf dem Server, die auf Systemen mit mehreren Prozessoren verfügbar ist. Verwenden Sie das **gcserver** -Element, um den Typ des Garbage Collection zu steuern, den die CLR ausführt. Mithilfe der <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>-Eigenschaft können Sie bestimmen, ob die Garbage Collection auf dem Server aktiviert ist.

Für Computer mit einem Prozessor stellt die Garbage Collection auf der Arbeitsstation (Standardeinstellung) in der Regel die schnellste Lösung dar. Auf Computern mit zwei Prozessoren kann die Arbeitsstation- oder die Serveroption verwendet werden. Sind mehr als zwei Prozessoren vorhanden, stellt die Garbage Collection auf dem Server in der Regel die schnellste Lösung dar. In den meisten Fällen deaktivieren Multiprozessor-Serversysteme die Server-GC und verwenden stattdessen die Arbeitsstations-GC, wenn viele Instanzen einer Server-App auf dem gleichen Computer ausgeführt werden.

Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden. Wenn es in der Computerkonfigurationsdatei enthalten ist, wird es ignoriert.

> [!NOTE]
> In .NET Framework 4 und früheren Versionen ist die gleichzeitige Garbage Collection nicht verfügbar, wenn die Garbage Collection auf dem Server aktiviert ist. Beginnend mit dem .NET Framework 4,5 ist der Server Garbage Collection gleichzeitig. Um nicht gleichzeitige Server Garbage Collection zu verwenden, legen Sie das **gcserver** -Element auf `true` und das [gcConcurrent-Element](gcconcurrent-element.md) auf fest `false` .

Ab .NET Framework 4.6.2 können Sie auch die folgenden Elemente verwenden, um Server GC zu konfigurieren:

- [Gcnoaffinitize](gcnoaffinitize-element.md): gibt an, ob zwischen Server-GC-Heaps und Prozessoren eine Affinität besteht. Standardmäßig ist für jeden Prozessor ein Server-GC-Heap vorhanden.

- [Gcheapcount](gcheapcount-element.md): schränkt die Anzahl von Heaps ein, die von einem Prozess verwendet werden.

- [Gcheapaffinitizemask](gcheapaffinitizemask-element.md): definiert die Affinität zwischen den verfügbaren Server-GC-Heaps und einzelnen Prozessoren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Server Garbage Collection aktiviert:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [So deaktivieren Sie die parallele Garbage Collection](gcconcurrent-element.md#to-disable-background-garbage-collection)
