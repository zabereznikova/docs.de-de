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
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968907"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode>-Element

Bestimmt, ob die Laufzeit Legacy Verhalten bei Formatierungs Vorgängen mit Werten beibehält <xref:System.TimeSpan?displayProperty=nameWithType> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a>Syntax

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Legacy Formatierungs Verhalten mit- <xref:System.TimeSpan?displayProperty=nameWithType> Werten verwendet.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|BESCHREIBUNG|
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

## <a name="remarks"></a>Bemerkungen

Beginnend mit dem .NET Framework 4 implementiert die <xref:System.TimeSpan?displayProperty=nameWithType> -Struktur die <xref:System.IFormattable> -Schnittstelle und unterstützt Formatierungs Vorgänge mit standardmäßigen und benutzerdefinierten Format Zeichenfolgen. Wenn eine Methode für die Methode einen nicht unterstützten Format Bezeichner oder eine Format Zeichenfolge erkennt, wird eine ausgelöst <xref:System.FormatException> .

In früheren Versionen der .NET Framework wurde die <xref:System.TimeSpan> -Struktur nicht implementiert, <xref:System.IFormattable> und es wurden keine Format Zeichenfolgen unterstützt. Viele Entwickler haben jedoch fälschlicherweise angenommen, dass <xref:System.TimeSpan> eine Reihe von Format Zeichenfolgen unterstützt und Sie in zusammen [gesetzten Formatierungs Vorgängen](../../../../standard/base-types/composite-formatting.md) mit Methoden wie verwendet <xref:System.String.Format%2A?displayProperty=nameWithType> . Wenn ein Typ eine Format Zeichenfolge implementiert <xref:System.IFormattable> und unterstützt, lösen Aufrufe von Formatierungs Methoden mit nicht unterstützten Format Zeichenfolgen normalerweise einen aus <xref:System.FormatException> . Da jedoch <xref:System.TimeSpan> nicht implementiert hat <xref:System.IFormattable> , hat die Laufzeit die Format Zeichenfolge ignoriert und stattdessen die- <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode aufgerufen. Dies bedeutet, dass die Format Zeichenfolgen zwar keine Auswirkung auf den Formatierungs Vorgang haben, das vorhanden sein allerdings nicht zu einer führte <xref:System.FormatException> .

In Fällen, in denen Legacy Code eine kombinierte Formatierungs Methode und eine ungültige Format Zeichenfolge übergibt und dieser Code nicht erneut kompiliert werden kann, können Sie das Legacy Verhalten mit dem- `<TimeSpan_LegacyFormatMode>` Element wiederherstellen <xref:System.TimeSpan> . Wenn Sie das- `enabled` Attribut dieses Elements auf festlegen `true` , führt die kombinierte Formatierungs Methode dazu, dass anstelle von aufgerufen wird <xref:System.TimeSpan.ToString?displayProperty=nameWithType> <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> , und <xref:System.FormatException> wird nicht ausgelöst.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein-Objekt instanziiert <xref:System.TimeSpan> und versucht, es mit der-Methode zu formatieren, <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> indem eine nicht unterstützte Standardformat Zeichenfolge verwendet wird

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Wenn Sie das Beispiel auf dem .NET Framework 3,5 oder einer früheren Version ausführen, wird die folgende Ausgabe angezeigt:

```console
12:30:45
```

Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel auf dem .NET Framework 4 oder einer höheren Version ausführen:

```console
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

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
