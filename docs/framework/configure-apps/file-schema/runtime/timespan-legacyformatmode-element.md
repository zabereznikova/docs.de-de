---
title: <TimeSpan_LegacyFormatMode>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f16a2bbd2470b4aec9e95ab67ccb0e736c4c6d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920689"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode >-Element

Bestimmt, ob die Laufzeit Legacy Verhalten bei Formatierungs Vorgängen mit <xref:System.TimeSpan?displayProperty=nameWithType> Werten beibehält.

\<Konfigurations > \
\<Lauf Zeit > \
\<TimeSpan_LegacyFormatMode>

## <a name="syntax"></a>Syntax

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Legacy Formatierungs <xref:System.TimeSpan?displayProperty=nameWithType> Verhalten mit-Werten verwendet.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Die Laufzeit stellt das Legacy Formatierungs Verhalten nicht wieder her.|
|`true`|Die Laufzeit stellt das Legacy Formatierungs Verhalten wieder her.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Hinweise

Beginnend mit dem .NET Framework 4 implementiert die <xref:System.TimeSpan?displayProperty=nameWithType> -Struktur die <xref:System.IFormattable> -Schnittstelle und unterstützt Formatierungs Vorgänge mit standardmäßigen und benutzerdefinierten Format Zeichenfolgen. Wenn eine Methode für die Methode einen nicht unterstützten Format Bezeichner oder eine Format Zeichenfolge <xref:System.FormatException>erkennt, wird eine ausgelöst.

In früheren Versionen der .NET Framework wurde die <xref:System.TimeSpan> -Struktur nicht implementiert <xref:System.IFormattable> , und es wurden keine Format Zeichenfolgen unterstützt. Viele Entwickler haben jedoch fälschlicherweise angenommen, <xref:System.TimeSpan> dass eine Reihe von Format Zeichenfolgen unterstützt und Sie in zusammen [gesetzten Formatierungs Vorgängen](../../../../standard/base-types/composite-formatting.md) <xref:System.String.Format%2A?displayProperty=nameWithType>mit Methoden wie verwendet. Wenn ein Typ eine Format Zeichenfolge implementiert <xref:System.IFormattable> und unterstützt, lösen Aufrufe von Formatierungs Methoden mit nicht unterstützten Format Zeichenfolgen normalerweise einen <xref:System.FormatException>aus. Da <xref:System.TimeSpan> jedoch nicht implementiert <xref:System.IFormattable>hat, hat die Laufzeit die Format Zeichenfolge ignoriert und stattdessen <xref:System.TimeSpan.ToString?displayProperty=nameWithType> die-Methode aufgerufen. Dies bedeutet, dass die Format Zeichenfolgen zwar keine Auswirkung auf den Formatierungs Vorgang haben, das vorhanden sein aller <xref:System.FormatException>dings nicht zu einer führte.

In Fällen, in denen Legacy Code eine kombinierte Formatierungs Methode und eine ungültige Format Zeichenfolge übergibt und dieser Code nicht erneut kompiliert werden kann `<TimeSpan_LegacyFormatMode>` , können Sie das Legacy <xref:System.TimeSpan> Verhalten mit dem-Element wiederherstellen. Wenn Sie `enabled` das-Attribut dieses Elements auf <xref:System.TimeSpan.ToString?displayProperty=nameWithType> `true`festlegen, führt die kombinierte Formatierungs Methode dazu, dass anstelle <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>von aufgerufen wird, <xref:System.FormatException> und wird nicht ausgelöst.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.TimeSpan> -Objekt instanziiert und versucht, es mit der <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode zu formatieren, indem eine nicht unterstützte Standardformat Zeichenfolge verwendet wird

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Wenn Sie das Beispiel auf dem .NET Framework 3,5 oder einer früheren Version ausführen, wird die folgende Ausgabe angezeigt:

```
12:30:45
```

Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel auf dem .NET Framework 4 oder einer höheren Version ausführen:

```
Invalid Format
```

Wenn Sie jedoch die folgende Konfigurationsdatei zum Verzeichnis des Beispiels hinzufügen und dann das Beispiel für die Version .NET Framework 4 oder höher ausführen, ist die Ausgabe identisch mit der Ausgabe, die im Beispiel erstellt wird, wenn Sie auf .NET Framework 3,5 ausgeführt wird.

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
