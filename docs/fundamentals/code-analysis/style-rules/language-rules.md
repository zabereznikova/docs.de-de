---
title: Regeln für Code Stilsprache
description: Erfahren Sie mehr über die verschiedenen Code Stilregeln für die Verwendung von c#-und Visual Basic-Sprachkonstrukten.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
- language rules
- EditorConfig language conventions
ms.openlocfilehash: 2aa2261534363f1da6a2109f092e08d210ebd915
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957974"
---
# <a name="language-rules"></a>Sprachregeln

Regeln für das codeliterepository beeinflussen, wie verschiedene Konstrukte von .NET-Programmiersprachen, z. b. modifiziererer und Klammern, verwendet werden. Die Regeln fallen in die folgenden Kategorien:

- [.Net-Stilregeln](#net-style-rules): Regeln, die sowohl für c# als auch für Visual Basic gelten. Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `dotnet_style_` Präfix.
- [C#-Stilregeln](#c-style-rules): Regeln, die nur für die Sprache c# spezifisch sind. Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `csharp_style_` Präfix.
- [Visual Basic Stilregeln](#visual-basic-style-rules): Regeln, die nur für die Visual bsic-Sprache spezifisch sind. Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `visual_basic_style_` Präfix.

## <a name="option-format"></a>Options Format

Optionen für Sprachregeln können in einer Editor config-Datei mit folgendem Format angegeben werden:

`option_name = value` (Visual Studio 2019, Version 16,9 Preview 2 und höher)

oder

`option_name = value:severity`

- **Wert**

  Für jede Sprachregel geben Sie einen Wert an, der festlegt, ob oder wann der Stil bevorzugt werden soll. Viele Regeln akzeptieren den Wert `true` (dieses Format bevorzugen) oder `false` (dieses Format nicht bevorzugen). Andere Regeln akzeptieren Werte wie `when_on_single_line` oder `never`.

- **Schweregrad** (optional in Visual Studio 2019, Version 16,9 Preview 2 und höhere Versionen)

  Der zweite Teil der Regel gibt den [Schweregrad](../configuration-options.md#severity-level) für die Regel an. Wenn die Einstellung auf diese Weise festgelegt wird, wird die Einstellung für den Schweregrad nur in Entwicklungs-IDES wie Visual Studio berücksichtigt. Sie wird während des Builds *nicht* beachtet.

  Legen Sie den Schweregrad mithilfe der Regel-ID-basierten Schweregrad Konfigurationssyntax für Analysen fest, um Code Formatregeln zum Zeitpunkt der Erstellung zu erzwingen. Die Syntax sieht wie folgt aus: `dotnet_diagnostic.<rule ID>.severity = <severity>`. Beispiel: `dotnet_diagnostic.IDE0040.severity = silent`. Weitere Informationen finden Sie unter [Schweregrad](../configuration-options.md#severity-level).

> [!TIP]
>
> Ab Version 16.3 von Visual Studio 2019 können Sie Regeln für Codeformate über das Fehlerbehebungsmenü [Schnellaktionen](/visualstudio/ide/quick-actions) konfigurieren, wenn ein Formatverstoß auftritt. Weitere Informationen finden Sie unter [Automatisches Konfigurieren von Code Stilen in Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).

## <a name="net-style-rules"></a>.Net-Stilregeln

Die Formatregeln in diesem Abschnitt gelten für C# und für Visual Basic.

- ["this." und "Me."-Qualifizierer](ide0003-ide0009.md)
  - [dotnet_style_qualification_for_field](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [dotnet_style_qualification_for_property](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [dotnet_style_qualification_for_method](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [dotnet_style_qualification_for_event](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [Sprachschlüsselwörter anstelle von Framework-Typnamen für Typverweise](ide0049.md)
  - [dotnet_style_predefined_type_for_locals_parameters_members](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [dotnet_style_predefined_type_for_member_access](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [Einstellungen von Modifizierern](modifier-preferences.md#net-modifier-preferences)
  - [dotnet_style_require_accessibility_modifiers](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [csharp_preferred_modifier_order](ide0036.md#csharp_preferred_modifier_order)
  - [visual_basic_preferred_modifier_order](ide0036.md#visual_basic_preferred_modifier_order)
  - [dotnet_style_readonly_field](ide0044.md#dotnet_style_readonly_field)
- [Einstellungen für Klammern](ide0047-ide0048.md)
  - [dotnet_style_parentheses_in_arithmetic_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [dotnet_style_parentheses_in_relational_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [dotnet_style_parentheses_in_other_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [dotnet_style_parentheses_in_other_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [Einstellungen auf Ausdrucksebene](expression-level-preferences.md#net-expression-level-preferences)
  - [dotnet_style_object_initializer](ide0017.md#dotnet_style_object_initializer)
  - [dotnet_style_collection_initializer](ide0028.md#dotnet_style_collection_initializer)
  - [dotnet_style_explicit_tuple_names](ide0033.md#dotnet_style_explicit_tuple_names)
  - [dotnet_style_prefer_inferred_tuple_names](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [dotnet_style_prefer_inferred_anonymous_type_member_names](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [dotnet_style_prefer_auto_properties](ide0032.md#dotnet_style_prefer_auto_properties)
  - [dotnet_style_prefer_conditional_expression_over_assignment](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [dotnet_style_prefer_conditional_expression_over_return](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [dotnet_style_prefer_compound_assignment](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [dotnet_style_prefer_simplified_interpolation](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [dotnet_style_prefer_simplified_boolean_expressions](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - [Fehlende Fälle zu Switch-Anweisung hinzufügen](ide0010.md) : Diese Regel weist keine Codestil-Option auf.
  - [Anonymen Typ in Tupel konvertieren](ide0050.md) : Diese Regel weist keine Codestil-Option auf.
  - ["System. Hashcode. Combine" verwenden](ide0070.md) : Diese Regel weist keine Codestil-Option auf.
  - ["Typeof" in "nameof" konvertieren](ide0082.md) : Diese Regel weist keine Codestil-Option auf.
- [Einstellungen für die NULL-Überprüfung](null-checking-preferences.md#net-null-checking-preferences)
  - [dotnet_style_coalesce_expression](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [dotnet_style_null_propagation](ide0031.md#dotnet_style_null_propagation)
  - [dotnet_style_prefer_is_null_check_over_reference_equality_method](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [Dateiheadereinstellungen](ide0073.md)
  - [file_header_template](ide0073.md#file_header_template)

## <a name="c-style-rules"></a>C#-Stilregeln

Die Stilregeln in diesem Abschnitt gelten nur für die Sprache c#.

- ["var"-Einstellungen](ide0007-ide0008.md)
  - [csharp_style_var_for_built_in_types](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [csharp_style_var_when_type_is_apparent](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [csharp_style_var_elsewhere](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [Ausdruckskörpermember](expression-bodied-members.md)
  - [csharp_style_expression_bodied_methods](ide0022.md#csharp_style_expression_bodied_methods)
  - [csharp_style_expression_bodied_constructors](ide0021.md#csharp_style_expression_bodied_constructors)
  - [csharp_style_expression_bodied_operators](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [csharp_style_expression_bodied_properties](ide0025.md#csharp_style_expression_bodied_properties)
  - [csharp_style_expression_bodied_indexers](ide0026.md#csharp_style_expression_bodied_indexers)
  - [csharp_style_expression_bodied_accessors](ide0027.md#csharp_style_expression_bodied_accessors)
  - [csharp_style_expression_bodied_lambdas](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [csharp_style_expression_bodied_local_functions](ide0061.md#csharp_style_expression_bodied_local_functions)
- [Einstellungen für den Musterabgleich](pattern-matching-preferences.md)
  - [csharp_style_pattern_matching_over_is_with_cast_check](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [csharp_style_pattern_matching_over_as_with_null_check](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [csharp_style_prefer_switch_expression](ide0066.md#csharp_style_prefer_switch_expression)
  - [csharp_style_prefer_pattern_matching](ide0078.md#csharp_style_prefer_pattern_matching)
  - [csharp_style_prefer_not_pattern](ide0083.md#csharp_style_prefer_not_pattern)
- [Einstellungen auf Ausdrucksebene](expression-level-preferences.md#c-expression-level-preferences)
  - [csharp_style_inlined_variable_declaration](ide0018.md#csharp_style_inlined_variable_declaration)
  - [csharp_prefer_simple_default_expression](ide0034.md#csharp_prefer_simple_default_expression)
  - [csharp_style_pattern_local_over_anonymous_function](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [csharp_style_deconstructed_variable_declaration](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [csharp_style_prefer_index_operator](ide0056.md#csharp_style_prefer_index_operator)
  - [csharp_style_prefer_range_operator](ide0057.md#csharp_style_prefer_range_operator)
  - [csharp_style_implicit_object_creation_when_type_is_apparent](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - [Dem Switch-Ausdruck fehlende Fälle hinzufügen](ide0072.md) : Diese Regel weist keine Codestil-Option auf.
- [Einstellungen für die NULL-Überprüfung](null-checking-preferences.md#c-null-checking-preferences)
  - [csharp_style_throw_expression](ide0016.md#csharp_style_throw_expression)
  - [csharp_style_conditional_delegate_call](ide1005.md#csharp_style_conditional_delegate_call)
- [Codeblockeinstellungen](code-block-preferences.md)
  - [csharp_prefer_braces](ide0011.md#csharp_prefer_braces)
  - [csharp_prefer_simple_using_statement](ide0063.md#csharp_prefer_simple_using_statement)
- [using-direktiveneinstellungen](ide0065.md)
  - [csharp_using_directive_placement](ide0065.md#csharp_using_directive_placement)
- [Einstellungen von Modifizierern](modifier-preferences.md#c-modifier-preferences)
  - [csharp_prefer_static_local_function](ide0062.md#csharp_prefer_static_local_function)
  - [Beschreibbare Struktur Felder erstellen](ide0064.md) : Diese Regel weist keine Codestil-Option auf.

## <a name="visual-basic-style-rules"></a>Regeln für Visual Basic Stil

Die Stilregeln in diesem Abschnitt gelten nur für Visual Basic Sprache.

- [Einstellungen für den Musterabgleich](pattern-matching-preferences.md)
  - [visual_basic_style_prefer_isnot_expression](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a>Siehe auch

- [Nicht benötigte Coderegeln](unnecessary-code-rules.md)
- [Formatierungsregeln](formatting-rules.md)
- [Benennungsregeln](naming-rules.md)
- [.Net-Codestil-Regel Referenz](index.md)
