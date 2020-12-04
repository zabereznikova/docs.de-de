---
title: Benennungs Regeln für den Code Stil
description: Erfahren Sie mehr über die .NET-Code Stilregeln für das Benennen von Code Elementen.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: 8ce209e64ee7f9f9028c221daedef8fc6a993ef7
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592120"
---
# <a name="naming-rules"></a>Benennungsregeln

Benennungs Regeln beziehen sich auf die Benennung von Code Elementen der .NET-Programmiersprache, wie z. b. Klassen, Eigenschaften und Methoden. Sie können beispielsweise angeben, dass öffentliche Mitglieder großgeschrieben werden oder dass private Felder mit `_` beginnen müssen.

Eine Benennungs Regel besteht aus drei Teilen:

* Die Gruppe der Symbole, auf die Sie angewendet wird.
* Der Benennungs Stil, der der Regel zugeordnet werden soll.
* Der Schweregrad für die Erzwingung der Konvention.

Benennungs Regeln definieren Sie in einer Editor config-Datei.

## <a name="general-syntax"></a>Allgemeine Syntax

Legen Sie zum Definieren einer Benennungs Regel, einer Symbolgruppe oder eines Benennungs Stils eine oder mehrere Eigenschaften mit der folgenden Syntax fest:

```ini
<prefix>.<title>.<propertyName> = <propertyValue>
```

Jede Eigenschaft sollte nur einmal festgelegt werden, aber einige Einstellungen lassen mehrere durch Trennzeichen getrennte Werte zu.

Die Reihenfolge der Eigenschaften ist ohne Bedeutung.

### \<prefix>

**\<prefix>** Gibt an, welche Art von Element &mdash; namens Regel, Symbolgruppe oder Benennungs Stil definiert wird, &mdash; und muss eine der folgenden sein:

| So legen Sie eine Eigenschaft fest | Verwenden des Präfixes | Beispiel |
| --- | --- | -- |
| Benennungs Regel | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| Symbol Gruppe | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| Benennungs Stil | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

Jeder Typ von Definitions &mdash; [Benennungs Regel](#naming-rule-properties), [Symbolgruppe](#symbol-group-properties)oder [Benennungs Stil](#naming-style-properties) &mdash; hat seine eigenen unterstützten Eigenschaften, wie in den folgenden Abschnitten beschrieben.

### \<title>

**\<title>** ein beschreibender Name, den Sie auswählen, der mehrere Eigenschafts Einstellungen einer einzelnen Definition zuordnet. Die folgenden Eigenschaften ergeben z. b. zwei Symbolgruppen Definitionen, `interface` und `types` , von denen jeweils zwei Eigenschaften festgelegt sind.

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a>Eigenschaften von Benennungs Regeln

Alle Eigenschaften der Benennungs Regel sind erforderlich, damit eine Regel wirksam wird.

| Eigenschaft | BESCHREIBUNG |
| -- | -- |
| `symbols` | Der Titel der Symbolgruppe, die die Symbole definiert, auf die diese Regel angewendet werden soll. |
| `style` | Der Titel des Namens Stils, der dieser Regel zugeordnet werden soll. |
| `severity` |  Legt den Schweregrad fest, mit dem die Benennungs Regel erzwungen werden soll. Legen Sie den zugeordneten Wert auf einen der verfügbaren [Schweregrade](https://docs.microsoft.com/dotnet/fundamentals/code-analysis/configuration-options#severity-level)fest. <sup>1</sup> |

**Hinweise:**

1. Die Schweregrad Spezifikation innerhalb einer Benennungs Regel wird nur innerhalb der Entwicklungs-IDES, z. b. Visual Studio, berücksichtigt. Diese Einstellung wird von den c#-oder VB-Compilern nicht verstanden und daher während des Builds nicht beachtet. Stattdessen sollten Sie den Schweregrad mithilfe der Regel-ID-basierten Schweregrad Konfiguration wie in [diesem Abschnitt](#rule-id-ide1006-naming-rule-violation)erläutert festlegen, um Benennungs Stilregeln für den Build zu erzwingen. Weitere Informationen finden Sie in diesem [GitHub-Problem](https://github.com/dotnet/roslyn/issues/44201).

## <a name="rule-order"></a>Regelreihenfolge

Die Reihenfolge, in der Benennungs Regeln in einer Editor config-Datei definiert sind, spielt keine Rolle. Die Benennungs Regeln werden automatisch nach der Definition der Regeln selbst geordnet. Die Erweiterung [EditorConfig Language Service](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) kann eine EditorConfig-Datei analysieren und Fälle melden, in denen sich die Regelreihenfolge in der Datei von der Reihenfolge unterscheidet, die vom Compiler zur Laufzeit verwendet wird.

> [!NOTE]
>
> Wenn Sie eine frühere Version von Visual Studio als Visual Studio 2019 Version 16,2 verwenden, sollten Benennungs Regeln von der spezifischsten zu den spezifischsten in der Editor config-Datei angeordnet werden. Die erste Regel, die angewendet werden kann, ist die einzige Regel, die angewendet wird. Wenn es jedoch mehrere *Regeleigenschaften* mit dem gleichen Namen gibt, hat die zuletzt gefundene Eigenschaft mit diesem Namen Vorrang. Weitere Informationen finden Sie unter [Dateihierarchie und Rangfolge](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).

## <a name="symbol-group-properties"></a>Symbol Gruppen Eigenschaften

Sie können die folgenden Eigenschaften für Symbolgruppen festlegen, um einzuschränken, welche Symbole in der Gruppe enthalten sind. Wenn Sie mehrere Werte in einer einzelnen Eigenschafts Einstellung angeben möchten, trennen Sie diese durch ein Komma.

| Eigenschaft | BESCHREIBUNG | Zulässige Werte | Erforderlich |
| -- | -- | -- | -- |
| `applicable_kinds` | Arten von Symbolen in Gruppe <sup>1</sup> | `*` (verwenden Sie diesen Wert, um alle Symbole anzugeben)<br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | Ja |
| `applicable_accessibilities` | Barrierefreiheits Stufen der Symbole in der Gruppe | `*` (verwenden Sie diesen Wert, um alle Zugriffsebenen anzugeben)<br/>`public`<br/>`internal` oder `friend`<br/>`private`<br/>`protected`<br/>`protected_internal` oder `protected_friend`<br/>`private_protected`<br/>`local` (für Symbole, die in einer Methode definiert sind) | Ja |
| `required_modifiers` | Symbole nur mit _allen_ angegebenen modifiziererzeichen <sup>2</sup> vergleichen | `abstract` oder `must_inherit`<br/>`async`<br/>`const`<br/>`readonly`<br/>`static` oder `shared` <sup>3</sup> | Nein  |

**Hinweise:**

1. Tupelmember werden in derzeit nicht unterstützt `applicable_kinds` .
2. Die Symbolgruppe gleicht _alle_ modifiziererer in der `required_modifiers` Eigenschaft ab.  Wenn Sie diese Eigenschaft weglassen, sind keine spezifischen modifiziererer für eine Entsprechung erforderlich. Das bedeutet, dass die Modifizierer eines Symbols keine Auswirkungen darauf haben, ob die Regel angewendet wird oder nicht.
3. Wenn die Gruppe `static` oder `shared` in der- `required_modifiers` Eigenschaft aufweist, enthält die Gruppe auch `const` Symbole, da Sie implizit sind `static` / `Shared` . Wenn Sie jedoch nicht möchten, dass die `static` Benennungs Regel auf `const` Symbole angewendet wird, können Sie eine neue Benennungs Regel mit einer Symbolgruppe von erstellen `const` .

## <a name="naming-style-properties"></a>Benennungs Stileigenschaften

Ein Benennungs Stil definiert die Konventionen, die Sie mit der Regel erzwingen möchten. Zum Beispiel:

* Großbuchstaben mit `PascalCase`
* Beginnt mit `m_`
* Endet mit `_g`
* Getrennte Wörter mit `__`

Sie können die folgenden Eigenschaften für einen Benennungs Stil festlegen:

| Eigenschaft | BESCHREIBUNG | Zulässige Werte | Erforderlich |
| -- | -- | -- | -- |
| `capitalization` | Groß-/Kleinschreibung für Wörter innerhalb des Symbols | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | Ja<sup>1</sup> |
| `required_prefix` | Muss mit diesen Zeichen beginnen | | Nein  |
| `required_suffix` | Muss mit diesen Zeichen enden | | Nein  |
| `word_separator` | Wörter innerhalb des Symbols müssen durch dieses Zeichen getrennt werden. | | Nein  |

**Hinweise:**

1. Sie müssen im Rahmen Ihres Benennungsstils einen Stil für die Groß-/Kleinschreibung angeben. Andernfalls wird Ihr Benennungsstil möglicherweise ignoriert.

## <a name="default-naming-styles"></a>Standardbenennungsstile

Wenn Sie keine benutzerdefinierten Benennungs Regeln angeben, werden die folgenden Standard Stile verwendet:

- Bei Klassen, Strukturen, Enumerationen, Eigenschaften und Ereignissen mit `public`-, `private`-, `internal`-, `protected`- oder `protected_internal`-Zugriff, ist der standardmäßige Benennungsstil die Pascal-Schreibweise.

- Bei Schnittstellen mit `public`-, `private`-, `internal`-, `protected`- oder `protected_internal`-Zugriff ist der standardmäßige Benennungsstil die Pascal-Schreibweise mit dem erforderlichen Präfix **I**.

## <a name="example"></a>Beispiel

Die folgende *EDITORCONFIG-Datei* enthält eine Namenskonvention, die angibt, dass öffentliche Eigenschaften, Methoden, Felder, Ereignisse und Delegaten großgeschrieben werden müssen. Beachten Sie, dass diese Namenskonvention mehrere Arten von Symbolen angibt, für die die Regel gelten soll, wobei die Werte durch ein Komma getrennt werden.

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a>Regel-ID: "IDE1006" (Verstoß gegen Benennungs Regel)

Alle Benennungs Optionen verfügen über Regel `IDE1006` -ID und Titel `Naming rule violation` . Sie können den Schweregrad von Benennungs Verstößen Global in einer editorconfig-Datei mit der folgenden Syntax konfigurieren:

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

Der Schweregrad muss `warning` oder sein `error` , um [beim Build erzwungen](../overview.md#code-style-analysis)zu werden. Alle möglichen Schweregrad Werte finden Sie unter [Schweregrad](../configuration-options.md#severity-level).

## <a name="see-also"></a>Siehe auch

- [Sprachregeln](language-rules.md)
- [Formatierungsregeln](formatting-rules.md)
- [Roslyn-Benennungs Regeln](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [.Net-Codestil-Regel Referenz](index.md)
