---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430484"
---
# <a name="gccpugroup-element"></a>\<gccpugroup >-Element

Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<gccpugroup >**

## <a name="syntax"></a>Syntax

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Garbage Collection unterstützt mehrere CPU-Gruppen nicht. Dies ist die Standardeinstellung.|
|`true`|Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.|

### <a name="child-elements"></a>Untergeordnete Elemente

None.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Hinweise

Wenn ein Computer über mehrere CPU-Gruppen verfügt und Server Garbage Collection aktiviert ist (siehe das [\<gcserver >](gcserver-element.md) -Element), erweitert das Aktivieren dieses Elements Garbage Collection auf alle CPU-Gruppen und übernimmt beim Erstellen und Ausgleichen von Heaps alle Kerne.

> [!NOTE]
> Dieses Element gilt nur für Garbage Collection-Threads. Damit die Laufzeit Benutzerthreads über alle CPU-Gruppen hinweg verteilen kann, müssen Sie auch das [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) -Element aktivieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird das Aktivieren der Garbage Collection für mehrere CPU-Gruppen veranschaulicht.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [So deaktivieren Sie die parallele Garbage Collection](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
