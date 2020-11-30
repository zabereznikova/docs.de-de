---
title: Globalisierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die Globalisierungsaspekte einer .NET Core-App konfigurieren, z. B. wie japanische Datumsangaben analysiert werden.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: fc98e965093c28b75b9b66e4f1c9f147abd4680e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721911"
---
# <a name="run-time-configuration-options-for-globalization"></a>Laufzeitkonfigurationsoptionen für die Globalisierung

## <a name="invariant-mode"></a>Invarianter Modus

- Bestimmt, ob eine .NET Core-App im invarianten Globalisierungsmodus ausgeführt wird, ohne Zugriff auf kulturspezifischen Daten und Verhalten zu haben.
- Wenn Sie diese Einstellung weglassen, wird die App mit Zugriff auf die kulturellen Daten ausgeführt. Dies entspricht der Einstellung des Werts auf `false`.
- Weitere Informationen finden sie unter [invarianter Globalisierungsmodus in .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false` – Zugriff auf kulturelle Daten<br/>`true` – Ausführung im invarianten Modus |
| **MSBuild-Eigenschaft** | `InvariantGlobalization` | `false` – Zugriff auf kulturelle Daten<br/>`true` – Ausführung im invarianten Modus |
| **Umgebungsvariable** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` – Zugriff auf kulturelle Daten<br/>`1` – Ausführung im invarianten Modus |

### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>Jahreszeitraumbereiche

- Legt fest, ob Bereichsüberprüfungen für Kalender, die mehrere Zeiträume unterstützen, locker sind, oder ob Daten, die den Datumsbereich eines Zeitraums überschreiten, eine <xref:System.ArgumentOutOfRangeException>-Klasse auslösen.
- Wenn Sie diese Einstellung weglassen, werden Bereichsüberprüfungen gelockert. Dies entspricht der Einstellung des Werts auf `false`.
- Weitere Informationen finden Sie unter [Kalender, Zeiträume und Datumsbereiche: Gelockerte Bereichsüberprüfungen](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` – gelockerte Bereichsüberprüfungen<br/>`true` – Überschreitungen verursachen eine Ausnahme |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="japanese-date-parsing"></a>Japanische Datumsanalyse

- Bestimmt, ob eine Zeichenfolge, die entweder „1“ oder „Gannen“ als Jahresangabe enthält, erfolgreich analysiert wird, oder ob nur „1“ unterstützt wird.
- Wenn Sie diese Einstellung weglassen, werden Zeichenfolgen, die entweder „1“ oder „Gannen“ als Jahresangabe enthalten, erfolgreich analysiert. Dies entspricht der Einstellung des Werts auf `false`.
- Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` – „Gannen“ oder „1“ wird unterstützt<br/>`true` – nur „1“ wird unterstützt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="japanese-year-format"></a>Japanisches Jahresformat

- Bestimmt, ob das erste Jahr eines japanischen Kalenderzeitraums als „Gannen“ oder als Zahl formatiert wird.
- Wenn Sie diese Einstellung weglassen, wird das erste Jahr als „Gannen“ formatiert. Dies entspricht der Einstellung des Werts auf `false`.
- Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` – Formatierung als „Gannen“<br/>`true` – Formatierung als Zahl |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="nls"></a>NLS

- Bestimmt, ob .NET für Windows-Apps die NLS-Globalisierungs-APIs (National Language Support, Unterstützung der nationalen Sprache) oder ICU-Globalisierungs-APIs (International Components for Unicode, internationale Komponenten für Unicode) verwendet. .NET 5.0 und höhere Versionen verwenden ICU-Globalisierungs-APIs standardmäßig unter dem Windows 10-Update vom Mai 2019 und höheren Versionen.
- Wenn Sie diese Einstellung weglassen, verwendet .NET standardmäßig ICU-Globalisierungs-APIs. Dies entspricht der Einstellung des Werts auf `false`.
- Weitere Informationen finden Sie unter [Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows](../compatibility/globalization/5.0/icu-globalization-api.md).

| | Einstellungsname | Werte | Eingeführt |
| - | - | - | - |
| **runtimeconfig.json** | `System.Globalization.UseNls` | `false` – Verwenden von ICU-Globalisierungs-APIs<br/>`true` – Verwenden von NLS-Globalisierungs-APIs | .NET 5.0 |
| **Umgebungsvariable** | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | `false` – Verwenden von ICU-Globalisierungs-APIs<br/>`true` – Verwenden von NLS-Globalisierungs-APIs | .NET 5.0 |
