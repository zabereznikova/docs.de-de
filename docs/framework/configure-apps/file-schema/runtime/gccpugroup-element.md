---
title: <GCCpuGroup>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102891"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup> Element

Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a>Syntax

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob von der Garbage Collection mehrere CPU-Gruppen unterstützt werden.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|`false`|Garbage Collection unterstützt mehrere CPU-Gruppen nicht. Dies ist die Standardoption.|
|`true`|Bei Aktivierung auf dem Server werden mehrere CPU-Gruppen von Garbage Collection unterstützt.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Bemerkungen

Wenn ein Computer über mehrere CPU-Gruppen verfügt und die Garbage Collection des Servers aktiviert ist (siehe [ \<gcServer](gcserver-element.md)>-Element), erweitert dieses Element die Garbage Collection auf alle CPU-Gruppen und berücksichtigt alle Kerne beim Erstellen und Ausgleichen von Heaps.

> [!NOTE]
> Dieses Element gilt nur für Garbage Collection-Threads. Damit die Laufzeit Benutzerthreads auf alle CPU-Gruppen verteilen [ \<](thread-useallcpugroups-element.md) kann, müssen Sie auch die Thread_UseAllCpuGroups>-Element aktivieren.

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

## <a name="see-also"></a>Weitere Informationen

- [Laufzeiteinstellungsschema](index.md)
- [Konfigurationsdateischema](../index.md)
- [Deaktivieren der gleichzeitigen Garbage Collection](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../../../standard/garbage-collection/workstation-server-gc.md)
