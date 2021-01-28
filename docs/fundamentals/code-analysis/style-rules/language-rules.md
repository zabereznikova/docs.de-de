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
# <a name="language-rules"></a><span data-ttu-id="914ff-103">Sprachregeln</span><span class="sxs-lookup"><span data-stu-id="914ff-103">Language rules</span></span>

<span data-ttu-id="914ff-104">Regeln für das codeliterepository beeinflussen, wie verschiedene Konstrukte von .NET-Programmiersprachen, z. b. modifiziererer und Klammern, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="914ff-104">Code style language rules affect how various constructs of .NET programming languages, for example, modifiers and parentheses, are used.</span></span> <span data-ttu-id="914ff-105">Die Regeln fallen in die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="914ff-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="914ff-106">[.Net-Stilregeln](#net-style-rules): Regeln, die sowohl für c# als auch für Visual Basic gelten.</span><span class="sxs-lookup"><span data-stu-id="914ff-106">[.NET style rules](#net-style-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="914ff-107">Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `dotnet_style_` Präfix.</span><span class="sxs-lookup"><span data-stu-id="914ff-107">The EditorConfig option names for these rules start with `dotnet_style_` prefix.</span></span>
- <span data-ttu-id="914ff-108">[C#-Stilregeln](#c-style-rules): Regeln, die nur für die Sprache c# spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="914ff-108">[C# style rules](#c-style-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="914ff-109">Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `csharp_style_` Präfix.</span><span class="sxs-lookup"><span data-stu-id="914ff-109">The EditorConfig option names for these rules start with `csharp_style_` prefix.</span></span>
- <span data-ttu-id="914ff-110">[Visual Basic Stilregeln](#visual-basic-style-rules): Regeln, die nur für die Visual bsic-Sprache spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="914ff-110">[Visual Basic style rules](#visual-basic-style-rules): Rules that are specific to Visual Bsic language only.</span></span> <span data-ttu-id="914ff-111">Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `visual_basic_style_` Präfix.</span><span class="sxs-lookup"><span data-stu-id="914ff-111">The EditorConfig option names for these rules start with `visual_basic_style_` prefix.</span></span>

## <a name="option-format"></a><span data-ttu-id="914ff-112">Options Format</span><span class="sxs-lookup"><span data-stu-id="914ff-112">Option format</span></span>

<span data-ttu-id="914ff-113">Optionen für Sprachregeln können in einer Editor config-Datei mit folgendem Format angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="914ff-113">Options for language rules can be specified in an EditorConfig file with the following format:</span></span>

<span data-ttu-id="914ff-114">`option_name = value` (Visual Studio 2019, Version 16,9 Preview 2 und höher)</span><span class="sxs-lookup"><span data-stu-id="914ff-114">`option_name = value` (Visual Studio 2019 version 16.9 Preview 2 and later)</span></span>

<span data-ttu-id="914ff-115">oder</span><span class="sxs-lookup"><span data-stu-id="914ff-115">or</span></span>

`option_name = value:severity`

- <span data-ttu-id="914ff-116">**Wert**</span><span class="sxs-lookup"><span data-stu-id="914ff-116">**Value**</span></span>

  <span data-ttu-id="914ff-117">Für jede Sprachregel geben Sie einen Wert an, der festlegt, ob oder wann der Stil bevorzugt werden soll.</span><span class="sxs-lookup"><span data-stu-id="914ff-117">For each language rule, you specify a value that defines if or when to prefer the style.</span></span> <span data-ttu-id="914ff-118">Viele Regeln akzeptieren den Wert `true` (dieses Format bevorzugen) oder `false` (dieses Format nicht bevorzugen).</span><span class="sxs-lookup"><span data-stu-id="914ff-118">Many rules accept a value of `true` (prefer this style) or `false` (do not prefer this style).</span></span> <span data-ttu-id="914ff-119">Andere Regeln akzeptieren Werte wie `when_on_single_line` oder `never`.</span><span class="sxs-lookup"><span data-stu-id="914ff-119">Other rules accept values such as `when_on_single_line` or `never`.</span></span>

- <span data-ttu-id="914ff-120">**Schweregrad** (optional in Visual Studio 2019, Version 16,9 Preview 2 und höhere Versionen)</span><span class="sxs-lookup"><span data-stu-id="914ff-120">**Severity** (optional in Visual Studio 2019 version 16.9 Preview 2 and later versions)</span></span>

  <span data-ttu-id="914ff-121">Der zweite Teil der Regel gibt den [Schweregrad](../configuration-options.md#severity-level) für die Regel an.</span><span class="sxs-lookup"><span data-stu-id="914ff-121">The second part of the rule specifies the [severity level](../configuration-options.md#severity-level) for the rule.</span></span> <span data-ttu-id="914ff-122">Wenn die Einstellung auf diese Weise festgelegt wird, wird die Einstellung für den Schweregrad nur in Entwicklungs-IDES wie Visual Studio berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="914ff-122">When specified in this way, the severity setting is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="914ff-123">Sie wird während des Builds *nicht* beachtet.</span><span class="sxs-lookup"><span data-stu-id="914ff-123">It is *not* respected during build.</span></span>

  <span data-ttu-id="914ff-124">Legen Sie den Schweregrad mithilfe der Regel-ID-basierten Schweregrad Konfigurationssyntax für Analysen fest, um Code Formatregeln zum Zeitpunkt der Erstellung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="914ff-124">To enforce code style rules at build time, set the severity by using the rule ID-based severity configuration syntax for analyzers instead.</span></span> <span data-ttu-id="914ff-125">Die Syntax sieht wie folgt aus: `dotnet_diagnostic.<rule ID>.severity = <severity>`. Beispiel: `dotnet_diagnostic.IDE0040.severity = silent`.</span><span class="sxs-lookup"><span data-stu-id="914ff-125">The syntax takes the form `dotnet_diagnostic.<rule ID>.severity = <severity>`, for example, `dotnet_diagnostic.IDE0040.severity = silent`.</span></span> <span data-ttu-id="914ff-126">Weitere Informationen finden Sie unter [Schweregrad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="914ff-126">For more information, see [severity level](../configuration-options.md#severity-level).</span></span>

> [!TIP]
>
> <span data-ttu-id="914ff-127">Ab Version 16.3 von Visual Studio 2019 können Sie Regeln für Codeformate über das Fehlerbehebungsmenü [Schnellaktionen](/visualstudio/ide/quick-actions) konfigurieren, wenn ein Formatverstoß auftritt.</span><span class="sxs-lookup"><span data-stu-id="914ff-127">Starting in Visual Studio 2019 version 16.3, you can configure code style rules from the [Quick Actions](/visualstudio/ide/quick-actions) light bulb menu after a style violation occurs.</span></span> <span data-ttu-id="914ff-128">Weitere Informationen finden Sie unter [Automatisches Konfigurieren von Code Stilen in Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="914ff-128">For more information, see [Automatically configure code styles in Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).</span></span>

## <a name="net-style-rules"></a><span data-ttu-id="914ff-129">.Net-Stilregeln</span><span class="sxs-lookup"><span data-stu-id="914ff-129">.NET style rules</span></span>

<span data-ttu-id="914ff-130">Die Formatregeln in diesem Abschnitt gelten für C# und für Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="914ff-130">The style rules in this section are applicable to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="914ff-131">"this." und "Me."-Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="914ff-131">'this.' and 'Me.' qualifiers</span></span>](ide0003-ide0009.md)
  - [<span data-ttu-id="914ff-132">dotnet_style_qualification_for_field</span><span class="sxs-lookup"><span data-stu-id="914ff-132">dotnet_style_qualification_for_field</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [<span data-ttu-id="914ff-133">dotnet_style_qualification_for_property</span><span class="sxs-lookup"><span data-stu-id="914ff-133">dotnet_style_qualification_for_property</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [<span data-ttu-id="914ff-134">dotnet_style_qualification_for_method</span><span class="sxs-lookup"><span data-stu-id="914ff-134">dotnet_style_qualification_for_method</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [<span data-ttu-id="914ff-135">dotnet_style_qualification_for_event</span><span class="sxs-lookup"><span data-stu-id="914ff-135">dotnet_style_qualification_for_event</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [<span data-ttu-id="914ff-136">Sprachschlüsselwörter anstelle von Framework-Typnamen für Typverweise</span><span class="sxs-lookup"><span data-stu-id="914ff-136">Language keywords instead of framework type names for type references</span></span>](ide0049.md)
  - [<span data-ttu-id="914ff-137">dotnet_style_predefined_type_for_locals_parameters_members</span><span class="sxs-lookup"><span data-stu-id="914ff-137">dotnet_style_predefined_type_for_locals_parameters_members</span></span>](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [<span data-ttu-id="914ff-138">dotnet_style_predefined_type_for_member_access</span><span class="sxs-lookup"><span data-stu-id="914ff-138">dotnet_style_predefined_type_for_member_access</span></span>](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [<span data-ttu-id="914ff-139">Einstellungen von Modifizierern</span><span class="sxs-lookup"><span data-stu-id="914ff-139">Modifier preferences</span></span>](modifier-preferences.md#net-modifier-preferences)
  - [<span data-ttu-id="914ff-140">dotnet_style_require_accessibility_modifiers</span><span class="sxs-lookup"><span data-stu-id="914ff-140">dotnet_style_require_accessibility_modifiers</span></span>](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [<span data-ttu-id="914ff-141">csharp_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="914ff-141">csharp_preferred_modifier_order</span></span>](ide0036.md#csharp_preferred_modifier_order)
  - [<span data-ttu-id="914ff-142">visual_basic_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="914ff-142">visual_basic_preferred_modifier_order</span></span>](ide0036.md#visual_basic_preferred_modifier_order)
  - [<span data-ttu-id="914ff-143">dotnet_style_readonly_field</span><span class="sxs-lookup"><span data-stu-id="914ff-143">dotnet_style_readonly_field</span></span>](ide0044.md#dotnet_style_readonly_field)
- [<span data-ttu-id="914ff-144">Einstellungen für Klammern</span><span class="sxs-lookup"><span data-stu-id="914ff-144">Parentheses preferences</span></span>](ide0047-ide0048.md)
  - [<span data-ttu-id="914ff-145">dotnet_style_parentheses_in_arithmetic_binary_operators</span><span class="sxs-lookup"><span data-stu-id="914ff-145">dotnet_style_parentheses_in_arithmetic_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [<span data-ttu-id="914ff-146">dotnet_style_parentheses_in_relational_binary_operators</span><span class="sxs-lookup"><span data-stu-id="914ff-146">dotnet_style_parentheses_in_relational_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [<span data-ttu-id="914ff-147">dotnet_style_parentheses_in_other_binary_operators</span><span class="sxs-lookup"><span data-stu-id="914ff-147">dotnet_style_parentheses_in_other_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [<span data-ttu-id="914ff-148">dotnet_style_parentheses_in_other_operators</span><span class="sxs-lookup"><span data-stu-id="914ff-148">dotnet_style_parentheses_in_other_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [<span data-ttu-id="914ff-149">Einstellungen auf Ausdrucksebene</span><span class="sxs-lookup"><span data-stu-id="914ff-149">Expression-level preferences</span></span>](expression-level-preferences.md#net-expression-level-preferences)
  - [<span data-ttu-id="914ff-150">dotnet_style_object_initializer</span><span class="sxs-lookup"><span data-stu-id="914ff-150">dotnet_style_object_initializer</span></span>](ide0017.md#dotnet_style_object_initializer)
  - [<span data-ttu-id="914ff-151">dotnet_style_collection_initializer</span><span class="sxs-lookup"><span data-stu-id="914ff-151">dotnet_style_collection_initializer</span></span>](ide0028.md#dotnet_style_collection_initializer)
  - [<span data-ttu-id="914ff-152">dotnet_style_explicit_tuple_names</span><span class="sxs-lookup"><span data-stu-id="914ff-152">dotnet_style_explicit_tuple_names</span></span>](ide0033.md#dotnet_style_explicit_tuple_names)
  - [<span data-ttu-id="914ff-153">dotnet_style_prefer_inferred_tuple_names</span><span class="sxs-lookup"><span data-stu-id="914ff-153">dotnet_style_prefer_inferred_tuple_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [<span data-ttu-id="914ff-154">dotnet_style_prefer_inferred_anonymous_type_member_names</span><span class="sxs-lookup"><span data-stu-id="914ff-154">dotnet_style_prefer_inferred_anonymous_type_member_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [<span data-ttu-id="914ff-155">dotnet_style_prefer_auto_properties</span><span class="sxs-lookup"><span data-stu-id="914ff-155">dotnet_style_prefer_auto_properties</span></span>](ide0032.md#dotnet_style_prefer_auto_properties)
  - [<span data-ttu-id="914ff-156">dotnet_style_prefer_conditional_expression_over_assignment</span><span class="sxs-lookup"><span data-stu-id="914ff-156">dotnet_style_prefer_conditional_expression_over_assignment</span></span>](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [<span data-ttu-id="914ff-157">dotnet_style_prefer_conditional_expression_over_return</span><span class="sxs-lookup"><span data-stu-id="914ff-157">dotnet_style_prefer_conditional_expression_over_return</span></span>](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [<span data-ttu-id="914ff-158">dotnet_style_prefer_compound_assignment</span><span class="sxs-lookup"><span data-stu-id="914ff-158">dotnet_style_prefer_compound_assignment</span></span>](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [<span data-ttu-id="914ff-159">dotnet_style_prefer_simplified_interpolation</span><span class="sxs-lookup"><span data-stu-id="914ff-159">dotnet_style_prefer_simplified_interpolation</span></span>](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [<span data-ttu-id="914ff-160">dotnet_style_prefer_simplified_boolean_expressions</span><span class="sxs-lookup"><span data-stu-id="914ff-160">dotnet_style_prefer_simplified_boolean_expressions</span></span>](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - <span data-ttu-id="914ff-161">[Fehlende Fälle zu Switch-Anweisung hinzufügen](ide0010.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-161">[Add missing cases to switch statement](ide0010.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="914ff-162">[Anonymen Typ in Tupel konvertieren](ide0050.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-162">[Convert anonymous type to tuple](ide0050.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="914ff-163">["System. Hashcode. Combine" verwenden](ide0070.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-163">[Use 'System.HashCode.Combine'](ide0070.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="914ff-164">["Typeof" in "nameof" konvertieren](ide0082.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-164">[Convert 'typeof' to 'nameof'](ide0082.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="914ff-165">Einstellungen für die NULL-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="914ff-165">Null-checking preferences</span></span>](null-checking-preferences.md#net-null-checking-preferences)
  - [<span data-ttu-id="914ff-166">dotnet_style_coalesce_expression</span><span class="sxs-lookup"><span data-stu-id="914ff-166">dotnet_style_coalesce_expression</span></span>](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [<span data-ttu-id="914ff-167">dotnet_style_null_propagation</span><span class="sxs-lookup"><span data-stu-id="914ff-167">dotnet_style_null_propagation</span></span>](ide0031.md#dotnet_style_null_propagation)
  - [<span data-ttu-id="914ff-168">dotnet_style_prefer_is_null_check_over_reference_equality_method</span><span class="sxs-lookup"><span data-stu-id="914ff-168">dotnet_style_prefer_is_null_check_over_reference_equality_method</span></span>](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [<span data-ttu-id="914ff-169">Dateiheadereinstellungen</span><span class="sxs-lookup"><span data-stu-id="914ff-169">File header preferences</span></span>](ide0073.md)
  - [<span data-ttu-id="914ff-170">file_header_template</span><span class="sxs-lookup"><span data-stu-id="914ff-170">file_header_template</span></span>](ide0073.md#file_header_template)

## <a name="c-style-rules"></a><span data-ttu-id="914ff-171">C#-Stilregeln</span><span class="sxs-lookup"><span data-stu-id="914ff-171">C# style rules</span></span>

<span data-ttu-id="914ff-172">Die Stilregeln in diesem Abschnitt gelten nur für die Sprache c#.</span><span class="sxs-lookup"><span data-stu-id="914ff-172">The style rules in this section are applicable to C# language only.</span></span>

- [<span data-ttu-id="914ff-173">"var"-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="914ff-173">'var' preferences</span></span>](ide0007-ide0008.md)
  - [<span data-ttu-id="914ff-174">csharp_style_var_for_built_in_types</span><span class="sxs-lookup"><span data-stu-id="914ff-174">csharp_style_var_for_built_in_types</span></span>](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [<span data-ttu-id="914ff-175">csharp_style_var_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="914ff-175">csharp_style_var_when_type_is_apparent</span></span>](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [<span data-ttu-id="914ff-176">csharp_style_var_elsewhere</span><span class="sxs-lookup"><span data-stu-id="914ff-176">csharp_style_var_elsewhere</span></span>](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [<span data-ttu-id="914ff-177">Ausdruckskörpermember</span><span class="sxs-lookup"><span data-stu-id="914ff-177">Expression-bodied members</span></span>](expression-bodied-members.md)
  - [<span data-ttu-id="914ff-178">csharp_style_expression_bodied_methods</span><span class="sxs-lookup"><span data-stu-id="914ff-178">csharp_style_expression_bodied_methods</span></span>](ide0022.md#csharp_style_expression_bodied_methods)
  - [<span data-ttu-id="914ff-179">csharp_style_expression_bodied_constructors</span><span class="sxs-lookup"><span data-stu-id="914ff-179">csharp_style_expression_bodied_constructors</span></span>](ide0021.md#csharp_style_expression_bodied_constructors)
  - [<span data-ttu-id="914ff-180">csharp_style_expression_bodied_operators</span><span class="sxs-lookup"><span data-stu-id="914ff-180">csharp_style_expression_bodied_operators</span></span>](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [<span data-ttu-id="914ff-181">csharp_style_expression_bodied_properties</span><span class="sxs-lookup"><span data-stu-id="914ff-181">csharp_style_expression_bodied_properties</span></span>](ide0025.md#csharp_style_expression_bodied_properties)
  - [<span data-ttu-id="914ff-182">csharp_style_expression_bodied_indexers</span><span class="sxs-lookup"><span data-stu-id="914ff-182">csharp_style_expression_bodied_indexers</span></span>](ide0026.md#csharp_style_expression_bodied_indexers)
  - [<span data-ttu-id="914ff-183">csharp_style_expression_bodied_accessors</span><span class="sxs-lookup"><span data-stu-id="914ff-183">csharp_style_expression_bodied_accessors</span></span>](ide0027.md#csharp_style_expression_bodied_accessors)
  - [<span data-ttu-id="914ff-184">csharp_style_expression_bodied_lambdas</span><span class="sxs-lookup"><span data-stu-id="914ff-184">csharp_style_expression_bodied_lambdas</span></span>](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [<span data-ttu-id="914ff-185">csharp_style_expression_bodied_local_functions</span><span class="sxs-lookup"><span data-stu-id="914ff-185">csharp_style_expression_bodied_local_functions</span></span>](ide0061.md#csharp_style_expression_bodied_local_functions)
- [<span data-ttu-id="914ff-186">Einstellungen für den Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="914ff-186">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="914ff-187">csharp_style_pattern_matching_over_is_with_cast_check</span><span class="sxs-lookup"><span data-stu-id="914ff-187">csharp_style_pattern_matching_over_is_with_cast_check</span></span>](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [<span data-ttu-id="914ff-188">csharp_style_pattern_matching_over_as_with_null_check</span><span class="sxs-lookup"><span data-stu-id="914ff-188">csharp_style_pattern_matching_over_as_with_null_check</span></span>](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [<span data-ttu-id="914ff-189">csharp_style_prefer_switch_expression</span><span class="sxs-lookup"><span data-stu-id="914ff-189">csharp_style_prefer_switch_expression</span></span>](ide0066.md#csharp_style_prefer_switch_expression)
  - [<span data-ttu-id="914ff-190">csharp_style_prefer_pattern_matching</span><span class="sxs-lookup"><span data-stu-id="914ff-190">csharp_style_prefer_pattern_matching</span></span>](ide0078.md#csharp_style_prefer_pattern_matching)
  - [<span data-ttu-id="914ff-191">csharp_style_prefer_not_pattern</span><span class="sxs-lookup"><span data-stu-id="914ff-191">csharp_style_prefer_not_pattern</span></span>](ide0083.md#csharp_style_prefer_not_pattern)
- [<span data-ttu-id="914ff-192">Einstellungen auf Ausdrucksebene</span><span class="sxs-lookup"><span data-stu-id="914ff-192">Expression-level preferences</span></span>](expression-level-preferences.md#c-expression-level-preferences)
  - [<span data-ttu-id="914ff-193">csharp_style_inlined_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="914ff-193">csharp_style_inlined_variable_declaration</span></span>](ide0018.md#csharp_style_inlined_variable_declaration)
  - [<span data-ttu-id="914ff-194">csharp_prefer_simple_default_expression</span><span class="sxs-lookup"><span data-stu-id="914ff-194">csharp_prefer_simple_default_expression</span></span>](ide0034.md#csharp_prefer_simple_default_expression)
  - [<span data-ttu-id="914ff-195">csharp_style_pattern_local_over_anonymous_function</span><span class="sxs-lookup"><span data-stu-id="914ff-195">csharp_style_pattern_local_over_anonymous_function</span></span>](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [<span data-ttu-id="914ff-196">csharp_style_deconstructed_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="914ff-196">csharp_style_deconstructed_variable_declaration</span></span>](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [<span data-ttu-id="914ff-197">csharp_style_prefer_index_operator</span><span class="sxs-lookup"><span data-stu-id="914ff-197">csharp_style_prefer_index_operator</span></span>](ide0056.md#csharp_style_prefer_index_operator)
  - [<span data-ttu-id="914ff-198">csharp_style_prefer_range_operator</span><span class="sxs-lookup"><span data-stu-id="914ff-198">csharp_style_prefer_range_operator</span></span>](ide0057.md#csharp_style_prefer_range_operator)
  - [<span data-ttu-id="914ff-199">csharp_style_implicit_object_creation_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="914ff-199">csharp_style_implicit_object_creation_when_type_is_apparent</span></span>](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - <span data-ttu-id="914ff-200">[Dem Switch-Ausdruck fehlende Fälle hinzufügen](ide0072.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-200">[Add missing cases to switch expression](ide0072.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="914ff-201">Einstellungen für die NULL-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="914ff-201">"Null" checking preferences</span></span>](null-checking-preferences.md#c-null-checking-preferences)
  - [<span data-ttu-id="914ff-202">csharp_style_throw_expression</span><span class="sxs-lookup"><span data-stu-id="914ff-202">csharp_style_throw_expression</span></span>](ide0016.md#csharp_style_throw_expression)
  - [<span data-ttu-id="914ff-203">csharp_style_conditional_delegate_call</span><span class="sxs-lookup"><span data-stu-id="914ff-203">csharp_style_conditional_delegate_call</span></span>](ide1005.md#csharp_style_conditional_delegate_call)
- [<span data-ttu-id="914ff-204">Codeblockeinstellungen</span><span class="sxs-lookup"><span data-stu-id="914ff-204">Code block preferences</span></span>](code-block-preferences.md)
  - [<span data-ttu-id="914ff-205">csharp_prefer_braces</span><span class="sxs-lookup"><span data-stu-id="914ff-205">csharp_prefer_braces</span></span>](ide0011.md#csharp_prefer_braces)
  - [<span data-ttu-id="914ff-206">csharp_prefer_simple_using_statement</span><span class="sxs-lookup"><span data-stu-id="914ff-206">csharp_prefer_simple_using_statement</span></span>](ide0063.md#csharp_prefer_simple_using_statement)
- [<span data-ttu-id="914ff-207">using-direktiveneinstellungen</span><span class="sxs-lookup"><span data-stu-id="914ff-207">'using' directive preferences</span></span>](ide0065.md)
  - [<span data-ttu-id="914ff-208">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="914ff-208">csharp_using_directive_placement</span></span>](ide0065.md#csharp_using_directive_placement)
- [<span data-ttu-id="914ff-209">Einstellungen von Modifizierern</span><span class="sxs-lookup"><span data-stu-id="914ff-209">Modifier preferences</span></span>](modifier-preferences.md#c-modifier-preferences)
  - [<span data-ttu-id="914ff-210">csharp_prefer_static_local_function</span><span class="sxs-lookup"><span data-stu-id="914ff-210">csharp_prefer_static_local_function</span></span>](ide0062.md#csharp_prefer_static_local_function)
  - <span data-ttu-id="914ff-211">[Beschreibbare Struktur Felder erstellen](ide0064.md) : Diese Regel weist keine Codestil-Option auf.</span><span class="sxs-lookup"><span data-stu-id="914ff-211">[Make struct fields writable](ide0064.md) - This rule has no code style option.</span></span>

## <a name="visual-basic-style-rules"></a><span data-ttu-id="914ff-212">Regeln für Visual Basic Stil</span><span class="sxs-lookup"><span data-stu-id="914ff-212">Visual Basic style rules</span></span>

<span data-ttu-id="914ff-213">Die Stilregeln in diesem Abschnitt gelten nur für Visual Basic Sprache.</span><span class="sxs-lookup"><span data-stu-id="914ff-213">The style rules in this section are applicable to Visual Basic language only.</span></span>

- [<span data-ttu-id="914ff-214">Einstellungen für den Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="914ff-214">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="914ff-215">visual_basic_style_prefer_isnot_expression</span><span class="sxs-lookup"><span data-stu-id="914ff-215">visual_basic_style_prefer_isnot_expression</span></span>](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a><span data-ttu-id="914ff-216">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="914ff-216">See also</span></span>

- [<span data-ttu-id="914ff-217">Nicht benötigte Coderegeln</span><span class="sxs-lookup"><span data-stu-id="914ff-217">Unnecessary code rules</span></span>](unnecessary-code-rules.md)
- [<span data-ttu-id="914ff-218">Formatierungsregeln</span><span class="sxs-lookup"><span data-stu-id="914ff-218">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="914ff-219">Benennungsregeln</span><span class="sxs-lookup"><span data-stu-id="914ff-219">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="914ff-220">.Net-Codestil-Regel Referenz</span><span class="sxs-lookup"><span data-stu-id="914ff-220">.NET code style rules reference</span></span>](index.md)
