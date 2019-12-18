---
title: Globalisierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die Globalisierungsaspekte einer .NET Core-App konfigurieren, z. B. wie japanische Datumsangaben analysiert werden.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 0571c64eff5b38aafa37026fb2ba7f4aef778beb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998840"
---
# <a name="run-time-configuration-options-for-globalization"></a>Laufzeitkonfigurationsoptionen für die Globalisierung

## <a name="invariant-mode"></a>Invarianter Modus

- Bestimmt, ob eine .NET Core-App im invarianten Globalisierungsmodus ausgeführt wird, ohne Zugriff auf kulturspezifischen Daten und Verhalten zu haben, oder ob sie Zugriff auf kulturelle Daten hat
- Standard: Die App wird mit Zugriff auf kulturelle Daten ausgeführt (`false`).
- Weitere Informationen finden sie unter [invarianter Globalisierungsmodus in .NET Core](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false` – Zugriff auf kulturelle Daten<br/>`true` – Ausführung im invarianten Modus |
| **Umgebungsvariable** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` – Zugriff auf kulturelle Daten<br/>`1` – Ausführung im invarianten Modus |

## <a name="era-year-ranges"></a>Jahreszeitraumbereiche

- Legt fest, ob Bereichsüberprüfungen für Kalender, die mehrere Zeiträume unterstützen, locker sind, oder ob Daten, die den Datumsbereich eines Zeitraums überschreiten, eine <xref:System.ArgumentOutOfRangeException>-Klasse auslösen.
- Standard: Bereichsüberprüfungen werden gelockert (`false`).
- Weitere Informationen finden Sie unter [Kalender, Zeiträume und Datumsbereiche: Gelockerte Bereichsüberprüfungen](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` – gelockerte Bereichsüberprüfungen<br/>`true` – Überschreitungen verursachen eine Ausnahme |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="japanese-date-parsing"></a>Japanische Datumsanalyse

- Bestimmt, ob eine Zeichenfolge, die entweder „1“ oder „Gannen“ als Jahresangabe enthält, erfolgreich analysiert wird, oder ob nur „1“ unterstützt wird.
- Standard: Zeichenfolgen, die entweder „1“ oder „Gannen“ als Jahresangabe enthalten, werden analysiert (`false`).
- Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` – „Gannen“ oder „1“ wird unterstützt<br/>`true` – nur „1“ wird unterstützt |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |

## <a name="japanese-year-format"></a>Japanisches Jahresformat

- Bestimmt, ob das erste Jahr eines japanischen Kalenderzeitraums als „Gannen“ oder als Zahl formatiert wird.
- Standard: Das erste Jahr wird als „Gannen“ formatiert (`false`).
- Weitere Informationen finden Sie unter [Darstellen von Daten in Kalendern mit mehreren Zeiträumen](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` – Formatierung als „Gannen“<br/>`true` – Formatierung als Zahl |
| **Umgebungsvariable** | Nicht zutreffend | Nicht zutreffend |
