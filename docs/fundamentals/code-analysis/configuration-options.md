---
title: Konfigurieren von Code Analyse Regeln
description: Erfahren Sie, wie Sie Code Analyse Regeln in einer Analyse Konfigurationsdatei konfigurieren.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: af2ebb74786f0ae884ffee4636765cae43fcb23f
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "96591670"
---
# <a name="configuration-options-for-code-analysis"></a>Konfigurationsoptionen für die Code Analyse

Code Analyse Regeln verfügen über verschiedene Konfigurationsoptionen. Diese Optionen werden als Schlüssel-Wert-Paare in einer [Analyse Konfigurationsdatei](configuration-files.md) mithilfe der-Syntax angegeben `<option key> = <option value>` .

Die am häufigsten konfigurierten Optionen sind der Schweregrad einer Regel. Sie können den Schweregrad für alle Analyse Regeln konfigurieren, einschließlich [Code Qualitätsregeln](quality-rules/index.md) und Regeln für den [Code Stil](style-rules/index.md).

Sie können auch zusätzliche Optionen zum Anpassen des Regel Verhaltens konfigurieren:

- Code Qualitätsregeln verfügen über [zusätzliche Optionen](code-quality-rule-options.md) zum Konfigurieren des Verhaltens, z. b. die Methodennamen, auf die eine Regel angewendet werden soll.
- Code Formatregeln verfügen über [benutzerdefinierte Optionen für den Code Stil](code-style-rule-options.md).
- Analyse Regeln von Drittanbietern können eigene Konfigurationsoptionen mit benutzerdefinierten Schlüsselnamen und Wert Formaten definieren.

Die Syntax zum Konfigurieren des schwere Grads einer bestimmten Regel in einer [Analyse Konfigurationsdatei](configuration-files.md) lautet wie folgt:

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a>Allgemeine Optionen

Diese Optionen gelten für die Code Analyse als Ganzes. Sie können nicht nur auf eine einzelne Regel oder einen Satz von Regeln angewendet werden.

### <a name="exclude-generated-code"></a>Generierten Code ausschließen

Sie können zusätzliche Dateien und Ordner so konfigurieren, dass Sie als generierten Code behandelt werden, indem Sie `generated_code = true | false` der [Konfigurationsdatei](configuration-files.md)einen Eintrag hinzufügen. .NET Code Analyzer-Warnungen sind für generierte Code Dateien, z. b. vom Designer generierte Dateien, nicht nützlich, die Benutzer nicht bearbeiten können, um Verstöße zu beheben. In den meisten Fällen überspringen Code Analysen generierte Code Dateien und melden keine Verstöße gegen diese Dateien.

Standardmäßig werden Dateien mit bestimmten Dateierweiterungen oder automatisch generierten Datei Headern als generierte Code Dateien behandelt. Beispielsweise wird ein Dateiname, der mit oder endet, `.designer.cs` `.generated.cs` als generierter Code betrachtet. Mit dieser Konfigurationsoption können Sie zusätzliche Benennungs Muster angeben.

Fügen Sie z. b. den folgenden Eintrag hinzu, um alle Dateien zu behandeln, deren Name mit `.MyGenerated.cs` dem generierten Code endet:

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a>Regel spezifische Optionen

Regel spezifische Optionen können auf eine einzelne Regel, einen Regelsatz oder alle Regeln angewendet werden. Zu den Regel spezifischen Optionen gehören:

- [Schweregrad der Regel](#severity-level)
- [Spezifische Optionen für *Code Qualitäts* Regeln](code-quality-rule-options.md)

### <a name="severity-level"></a>Schweregrad

In der folgenden Tabelle werden die verschiedenen Regel Schweregrade angezeigt, die Sie für alle Analyse Regeln konfigurieren können, einschließlich [Codequalität](quality-rules/index.md) und Regeln für den [Code Stil](style-rules/index.md) .

| Schweregrad | Verhalten zur Buildzeit |
|-|-|
| `error` | Verstöße werden als *Buildfehler* angezeigt und bewirken, dass Builds fehlschlagen.|
| `warning` | Verstöße werden als *Buildwarnungen* angezeigt, bewirken jedoch nicht, dass Builds fehlschlagen (es sei denn, Sie haben eine Option zum Behandeln von Warnungen als Fehler festgelegt). |
| `suggestion` | Verstöße werden als *Buildmeldungen* und als Vorschläge in der Visual Studio-IDE angezeigt. |
| `silent` | Verstöße sind für den Benutzer nicht sichtbar. |
| `none` | Die Regel wird vollständig unterdrückt. |
| `default` | Der Standard Schweregrad der Regel wird verwendet. |

> [!TIP]
> Informationen zur Oberfläche für Regel Schweregrade in Visual Studio finden Sie unter [Schweregrade](/visualstudio/ide/editorconfig-language-conventions#severity-levels).

#### <a name="scope"></a>`Scope`

Verwenden Sie die folgende Syntax, um den Schweregrad der Regel für eine einzelne Regel festzulegen.

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

Verwenden Sie die folgende Syntax, um den Standard Schweregrad der Regel für eine Kategorie von Analyse Regeln festzulegen.

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

Verwenden Sie die folgende Syntax, um den Standard Schweregrad der Regel für alle Analyse Regeln festzulegen.

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a>Rangfolge

Wenn Sie über mehrere Konfigurationseinträge für den Schweregrad verfügen, die auf dieselbe Regel-ID angewendet werden können, wird die Rangfolge in der folgenden Reihenfolge ausgewählt:

- Ein Eintrag für eine einzelne Regel nach ID hat Vorrang vor einem Eintrag für eine Kategorie.
- Ein Eintrag für eine Kategorie hat Vorrang vor einem Eintrag für alle Analyzer-Regeln.

Sehen Sie sich das folgende Beispiel an, in dem [CA1822](/visualstudio/code-quality/ca1822) die Kategorie "Performance" hat:

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

Im vorherigen Beispiel sind alle drei Schweregrade auf CA1822 anwendbar. Bei Verwendung der angegebenen Rang folgen Regeln gewinnt der erste auf der Regel-ID basierende Eintrag jedoch mit den nächsten Einträgen. In diesem Beispiel hat CA1822 den effektiven Schweregrad `error` . Alle anderen Regeln in der Kategorie "Leistung" haben den Schweregrad `warning` .

Informationen zur Entscheidung, wie die Rangfolge der Datei Vorrang hat, finden Sie im Abschnitt "Rang folgen" im [Artikel "Konfigurationsdateien](configuration-files.md#precedence)".
