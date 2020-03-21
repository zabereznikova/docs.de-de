---
title: gcConcurrent-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400980"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent>-Element

Gibt an, ob die Common Language Runtime die Garbage Collection auf einem separaten Thread ausführt.

[\<Konfiguration>](../configuration-element.md)\
&nbsp;&nbsp;[\<Laufzeit>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a>Syntax

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attributes

|attribute|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br />Gibt an, ob die Runtime die Garbage Collection gleichzeitig ausführt.|

#### <a name="enabled-attribute"></a>aktiviertes Attribut

|value|Beschreibung|
|-----------|-----------------|
|`false`|Führt die Garbage Collection nicht gleichzeitig aus.|
|`true`|Die Garbage Collection wird gleichzeitig ausgeführt. Dies ist die Standardoption.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Bemerkungen

Vor .NET Framework 4 unterstützte die Garbage Collection auf Arbeitsstation die gleichzeitige Garbage Collection, die die Garbage Collection im Hintergrund in einem separaten Thread durchführte. In .NET Framework 4 wurde die gleichzeitige Garbage Collection durch Background-GC ersetzt, das auch die Garbage Collection im Hintergrund für einen separaten Thread ausführt. Ab .NET Framework 4.5 wurde die Hintergrundsammlung in der Servergarbage-Auflistung verfügbar. Das **gcConcurrent-Element** steuert, ob die Laufzeit entweder gleichzeitige oder Hintergrund-Garbage Collection durchführt, ob sie verfügbar ist, oder ob sie die Garbage Collection im Vordergrund ausführt.

### <a name="to-disable-background-garbage-collection"></a>So deaktivieren Sie die Hintergrund-Garbage Collection

> [!WARNING]
> Ab .NET Framework 4 wird die gleichzeitige Garbage Collection durch die Garbage Collection im Hintergrund ersetzt. Die Begriffe *gleichzeitig* und *Hintergrund* werden in der .NET Framework-Dokumentation austauschbar verwendet. Um die Garbage Collection im Hintergrund zu deaktivieren, verwenden Sie das **gcConcurrent-Element,** wie in diesem Artikel beschrieben.

Standardmäßig verwendet die Runtime gleichzeitige Garbage Collection oder Garbage Collection im Hintergrund, die für Wartezeiten optimiert ist. Wenn Ihre Anwendung intensive Benutzerinteraktion bedingt, belassen Sie die parallele Garbage Collection aktiviert, damit die Pausenzeiten der Anwendung für die Ausführung der Garbage Collection minimiert werden. Wenn Sie `enabled` das Attribut des **gcConcurrent-Elements** auf `false`festlegen, verwendet die Laufzeit eine nicht gleichzeitige Garbage Collection, die für den Durchsatz optimiert ist.

Die folgende Konfigurationsdatei deaktiviert die Garbage Collection im Hintergrund:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

Wenn die Computerkonfigurationsdatei eine **gcConcurrentSetting-Einstellung** enthält, wird der Standardwert für alle .NET Framework-Anwendungen definiert. Die Einstellung in der Computerkonfigurationsdatei setzt die Einstellung in der Anwendungskonfigurationsdatei außer Kraft.

Weitere Informationen zur gleichzeitigen Garbage Collection und zur Garbage Collection im Hintergrund finden Sie im Artikel ["Concurrent Garbage Collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)", ["Hintergrundarbeitsstation"-](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)und ["Hintergrundserver-Garbage](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) Collection"-Abschnitte im Artikel [Grundlagen der Garbage Collection.](../../../../standard/garbage-collection/fundamentals.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Garbage Collection im Hintergrund aktiviert:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [Grundlagen der Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)
