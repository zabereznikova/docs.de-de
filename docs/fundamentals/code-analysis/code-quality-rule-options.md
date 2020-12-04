---
title: Konfigurationsoptionen für die Code Qualitäts Regel
description: Erfahren Sie, wie Sie zusätzliche Konfigurationsoptionen für Code Qualitätsregeln angeben.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: af2984e73c554e8a1e1b32df9460933f86cc41be
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590737"
---
# <a name="code-quality-rule-configuration-options"></a>Konfigurationsoptionen für die Code Qualitäts Regel

Die *Code Qualitäts* Regeln verfügen über zusätzliche Konfigurationsoptionen, außer nur die [Konfiguration Ihres schwere](configuration-options.md#severity-level)Grads. Beispielsweise kann jeder Code Quality Analyzer so konfiguriert werden, dass er nur für bestimmte Teile Ihrer Codebasis gilt. Sie geben diese Optionen an, indem Sie Schlüssel-Wert-Paare zur gleichen Datei hinzufügen, [EditorConfig](https://editorconfig.org) in der Sie Regel Schweregrade und allgemeine Editor-Einstellungen angeben.

## <a name="option-scopes"></a>Options Bereiche

Jede Option zum verfeinern kann für alle Regeln, für eine Kategorie von Regeln (z. b. Sicherheit oder Entwurf) oder für eine bestimmte Regel konfiguriert werden.

### <a name="all-rules"></a>Alle Regeln

Die Syntax zum Konfigurieren einer Option für *alle* Regeln lautet wie folgt:

|Syntax|Beispiel|
|-|-|
| dotnet_code_quality. OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>Kategorie von Regeln

Die Syntax zum Konfigurieren einer Option für eine *Kategorie* von Regeln (z. b. Benennung, Entwurf oder Leistung) lautet wie folgt:

|Syntax|Beispiel|
|-|-|
| dotnet_code_quality. Rulecategory. optionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>Bestimmte Regel

Die Syntax zum Konfigurieren einer Option für eine *bestimmte* Regel lautet wie folgt:

|Syntax|Beispiel|
|-|-|
| dotnet_code_quality. RuleId. optionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="options"></a>Optionen

In diesem Abschnitt werden einige der verfügbaren Optionen aufgeführt. Die vollständige Liste der verfügbaren Optionen finden Sie unter [Analyse Konfiguration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md).

### <a name="api_surface"></a>api_surface

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Der zu analysierende Teil der API-Oberfläche | `public`<br/>`internal` oder `friend`<br/>`private`<br/>`all`<br/><br/>Trennen Sie mehrere Werte durch ein Komma (,). | `public` | [CA1000](quality-rules/ca1000.md) [CA1003](quality-rules/ca1003.md) [CA1008](quality-rules/ca1008.md) [CA1010](quality-rules/ca1010.md)<br/>[CA1012](quality-rules/ca1012.md) [CA1024](quality-rules/ca1024.md) [CA1027](quality-rules/ca1027.md) [CA1028](quality-rules/ca1028.md)<br/>[CA1030](quality-rules/ca1030.md) [CA1036](quality-rules/ca1036.md) [CA1040](quality-rules/ca1040.md) [CA1041](quality-rules/ca1041.md)<br/>[CA1043](quality-rules/ca1043.md) [CA1044](quality-rules/ca1044.md) [CA1051](quality-rules/ca1051.md) [CA1052](quality-rules/ca1052.md)<br/>[CA1054](quality-rules/ca1054.md) [CA1055](quality-rules/ca1055.md) [CA1056](quality-rules/ca1056.md) [CA1058](quality-rules/ca1058.md)<br/>[CA1063](quality-rules/ca1063.md) [CA1708](quality-rules/ca1708.md) [CA1710](quality-rules/ca1710.md) [CA1711](quality-rules/ca1711.md)<br/>[CA1714](quality-rules/ca1714.md) [CA1715](quality-rules/ca1715.md) [CA1716](quality-rules/ca1716.md) [CA1717](quality-rules/ca1717.md)<br/>[CA1720](quality-rules/ca1720.md) [CA1721](quality-rules/ca1721.md) [CA1725](quality-rules/ca1725.md) [CA1801](quality-rules/ca1801.md)<br/>[CA1802](quality-rules/ca1802.md) [CA1815](quality-rules/ca1815.md) [CA1819](quality-rules/ca1819.md) [CA2217](quality-rules/ca2217.md)<br/>[CA2225](quality-rules/ca2225.md) [CA2226](quality-rules/ca2226.md) [CA2231](quality-rules/ca2231.md) [CA2234](quality-rules/ca2234.md)<br/>|

### <a name="exclude_async_void_methods"></a>exclude_async_void_methods

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Gibt an, ob asynchrone Methoden ignoriert werden sollen, die keinen Wert zurückgeben. | `true`<br/>`false` | `false` | [CA2007](quality-rules/ca2007.md) |

> [!NOTE]
> Diese Option wurde `skip_async_void_methods` in einer früheren Version benannt.

### <a name="exclude_single_letter_type_parameters"></a>exclude_single_letter_type_parameters

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Ob [Typparameter](../../csharp/programming-guide/generics/generic-type-parameters.md) mit einem Zeichen aus der Regel ausgeschlossen werden sollen, z. b. `S` in `Collection<S>` | `true`<br/>`false` | `false` | [CA1715](quality-rules/ca1715.md) |

> [!NOTE]
> Diese Option wurde `allow_single_letter_type_parameters` in einer früheren Version benannt.

### <a name="output_kind"></a>output_kind

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Gibt an, dass Code in einem Projekt analysiert werden soll, das diesen Assemblytyp generiert. | Ein oder mehrere Felder der- <xref:Microsoft.CodeAnalysis.OutputKind> Enumeration.<br/><br/>Trennen Sie mehrere Werte durch ein Komma (,). | Alle Ausgabearten | [CA2007](quality-rules/ca2007.md) |

### <a name="required_modifiers"></a>required_modifiers

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Gibt die erforderlichen modifiziererer für APIs an, die analysiert werden sollen. | Mindestens ein Wert aus der unten angegebenen Tabelle mit den Modifiziererwerten<br/><br/>Trennen Sie mehrere Werte durch ein Komma (,). | Hängt von jeder Regel ab | [CA1802](quality-rules/ca1802.md) |

| Zulässiger Modifizierer | Zusammenfassung |
| --- | --- |
| `none` | Keine modifiziereranforderung |
| `static` oder `Shared` | Muss als `static` ( `Shared` in Visual Basic) deklariert werden. |
| `const` | Muss als deklariert werden `const` |
| `readonly` | Muss als deklariert werden `readonly` |
| `abstract` | Muss als deklariert werden `abstract` |
| `virtual` | Muss als deklariert werden `virtual` |
| `override` | Muss als deklariert werden `override` |
| `sealed` | Muss als deklariert werden `sealed` |
| `extern` | Muss als deklariert werden `extern` |
| `async` | Muss als deklariert werden `async` |

### <a name="exclude_extension_method_this_parameter"></a>exclude_extension_method_this_parameter

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Ob die Analyse für den `this` Parameter der Erweiterungs Methoden übersprungen werden soll. | `true`<br/>`false` | `false` | [CA1062](quality-rules/ca1062.md) |

### <a name="null_check_validation_methods"></a>null_check_validation_methods

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Namen von Validierungs Methoden mit NULL Überprüfung, die überprüfen, ob die an die Methode übergebenen Argumente nicht NULL sind | Zulässige Methodennamen Formate (durch Trennzeichen getrennt `|` ):<br/> -Nur Methodenname (schließt alle Methoden mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace)<br/> -Voll qualifizierte Namen im [Dokumentations-ID-Format](https://github.com/dotnet/csharplang/blob/master/spec/documentation-comments.md#id-string-format)des Symbols mit einem optionalen `M:` Präfix | Keine | [CA1062](quality-rules/ca1062.md) |

### <a name="additional_string_formatting_methods"></a>additional_string_formatting_methods

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Namen von zusätzlichen Zeichen folgen-Formatierungs Methoden | Zulässige Methodennamen Formate (durch Trennzeichen getrennt `|` ):<br/> -Nur Methodenname (schließt alle Methoden mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace)<br/> -Voll qualifizierte Namen im [Dokumentations-ID-Format](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)des Symbols mit einem optionalen `M:` Präfix | Keine | [CA2241](quality-rules/ca2241.md) |

### <a name="excluded_type_names_with_derived_types"></a>excluded_type_names_with_derived_types

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Namen von Typen, sodass der Typ und alle abgeleiteten Typen für die Analyse ausgeschlossen sind | Zulässige Symbolnamen Formate (durch Trennzeichen getrennt `|` ):<br/> -Nur Typname (schließt alle Typen mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace)<br/> -Voll qualifizierte Namen im [Dokumentations-ID-Format](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)des Symbols mit einem optionalen `T:` Präfix | Keine | [CA1303](quality-rules/ca1303.md) |

### <a name="excluded_symbol_names"></a>excluded_symbol_names

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Namen von Symbolen, die für die Analyse ausgeschlossen sind | Zulässige Symbolnamen Formate (durch Trennzeichen getrennt `|` ):<br/> -Nur Symbol Name (schließt alle Symbole mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace)<br/> -Voll qualifizierte Namen im [Dokumentations-ID-Format](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)des Symbols. Jeder Symbol Name erfordert ein Symbolart-Präfix, z `M:` . b. Präfix für Methoden, `T:` Präfix für Typen und `N:` Präfix für Namespaces.<br/> - `.ctor` für Konstruktoren und `.cctor` für statische Konstruktoren | Keine | [CA1062](quality-rules/ca1062.md) [CA1303](quality-rules/ca1303.md) [CA2000](quality-rules/ca2000.md) [CA2100](quality-rules/ca2100.md) [CA2301](quality-rules/ca2301.md) [CA2302](quality-rules/ca2302.md)<br/>[CA2311](quality-rules/ca2311.md) [CA2312](quality-rules/ca2312.md) [CA2321](quality-rules/ca2321.md) [CA2322](quality-rules/ca2322.md) [CA2327](quality-rules/ca2327.md) [CA2328](quality-rules/ca2328.md)<br/>[CA2329](quality-rules/ca2329.md) [CA2330](quality-rules/ca2330.md) [CA3001](quality-rules/ca3001.md) [CA3002](quality-rules/ca3002.md) [CA3003](quality-rules/ca3003.md) [CA3004](quality-rules/ca3004.md)<br/>[CA3005](quality-rules/ca3005.md) [CA3006](quality-rules/ca3006.md) [CA3007](quality-rules/ca3007.md) [CA3008](quality-rules/ca3008.md) [CA3009](quality-rules/ca3009.md) [CA3010](quality-rules/ca3010.md)<br/>[CA3011](quality-rules/ca3011.md) [CA3012](quality-rules/ca3012.md) [CA5361](quality-rules/ca5361.md) CA5376 CA5377 [CA5378](quality-rules/ca5378.md)<br/>[CA5380](quality-rules/ca5380.md) [CA5381](quality-rules/ca5381.md) CA5382 CA5383 CA5384 CA5387<br/>CA5388 [CA5389](quality-rules/ca5389.md) CA5390 |

### <a name="disallowed_symbol_names"></a>disallowed_symbol_names

| Beschreibung | Zulässige Werte | Standardwert | Konfigurierbare Regeln |
| - | - | - | - |
| Namen von Symbolen, die im Kontext der Analyse nicht zulässig sind | Zulässige Symbolnamen Formate (durch Trennzeichen getrennt `|` ):<br/> -Nur Symbol Name (schließt alle Symbole mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace)<br/> -Voll qualifizierte Namen im [Dokumentations-ID-Format](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)des Symbols. Jeder Symbol Name erfordert ein Symbolart-Präfix, z `M:` . b. Präfix für Methoden, `T:` Präfix für Typen und `N:` Präfix für Namespaces.<br/> - `.ctor` für Konstruktoren und `.cctor` für statische Konstruktoren | Keine | [CA1031](quality-rules/ca1031.md) |
