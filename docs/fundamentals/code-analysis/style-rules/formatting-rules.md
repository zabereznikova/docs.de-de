---
title: Formatierungs Regeln für den Code Stil
description: Erfahren Sie mehr über die Code Stilregeln für das Formatieren von Einzüge, Leerzeichen und neuen Zeilen.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE0055
- formatting rules
helpviewer_keywords:
- IDE0055
- formatting code style rules [EditorConfig]
- formatting rules
- EditorConfig formatting conventions
ms.openlocfilehash: 61e6f6a6afdc6aaf9710eef3143af8ae700ef612
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "96591726"
---
# <a name="formatting-rules"></a><span data-ttu-id="11a08-103">Formatierungsregeln</span><span class="sxs-lookup"><span data-stu-id="11a08-103">Formatting rules</span></span>

<span data-ttu-id="11a08-104">Formatierungs Regeln beeinflussen, wie Einzug, Leerräume und neue Zeilen um .net-Programmier Sprachkonstrukte abgestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="11a08-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="11a08-105">Die Regeln fallen in die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="11a08-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="11a08-106">[.Net-Formatierungs Regeln](#net-formatting-rules): Regeln, die sowohl für c# als auch für Visual Basic gelten.</span><span class="sxs-lookup"><span data-stu-id="11a08-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="11a08-107">Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `dotnet_` Präfix.</span><span class="sxs-lookup"><span data-stu-id="11a08-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="11a08-108">[C#-Formatierungs Regeln](#c-formatting-rules): Regeln, die nur für die Sprache c# spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="11a08-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="11a08-109">Die Editor config-Optionsnamen für diese Regeln beginnen mit dem `csharp_` Präfix.</span><span class="sxs-lookup"><span data-stu-id="11a08-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="11a08-110">Regel-ID: "IDE0055" (Formatierung reparieren)</span><span class="sxs-lookup"><span data-stu-id="11a08-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="11a08-111">Alle Formatierungsoptionen verfügen über Regel `IDE0055` -ID und Titel `Fix formatting` .</span><span class="sxs-lookup"><span data-stu-id="11a08-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="11a08-112">Legen Sie den Schweregrad einer Formatierungs Verletzung in einer editorconfig-Datei mithilfe der folgenden Konfigurationszeile fest.</span><span class="sxs-lookup"><span data-stu-id="11a08-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="11a08-113">Der Schweregrad muss `warning` oder sein `error` , um [beim Build erzwungen](../overview.md#code-style-analysis)zu werden.</span><span class="sxs-lookup"><span data-stu-id="11a08-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="11a08-114">Alle möglichen Schweregrad Werte finden Sie unter [Schweregrad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="11a08-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="11a08-115">Options Format</span><span class="sxs-lookup"><span data-stu-id="11a08-115">Option format</span></span>

<span data-ttu-id="11a08-116">Optionen für Formatierungs Regeln können in einer Editor config-Datei mit folgendem Format angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="11a08-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="11a08-117">Bei vielen Regeln geben Sie entweder `true` (dieses Format bevorzugen) oder `false` (dieses Format nicht bevorzugen) als `value` an.</span><span class="sxs-lookup"><span data-stu-id="11a08-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="11a08-118">Bei anderen Regeln geben Sie einen Wert wie `flush_left` oder `before_and_after` an, um zu beschreiben, wann und wo die Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11a08-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="11a08-119">Sie geben keinen Schweregrad an.</span><span class="sxs-lookup"><span data-stu-id="11a08-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="11a08-120">.Net-Formatierungs Regeln</span><span class="sxs-lookup"><span data-stu-id="11a08-120">.NET formatting rules</span></span>

<span data-ttu-id="11a08-121">Die Formatierungs Regeln in diesem Abschnitt gelten für c# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="11a08-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="11a08-122">Organisieren von Using-Direktiven</span><span class="sxs-lookup"><span data-stu-id="11a08-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="11a08-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="11a08-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="11a08-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="11a08-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="11a08-125">Organisieren von using-Direktiven</span><span class="sxs-lookup"><span data-stu-id="11a08-125">Organize using directives</span></span>

<span data-ttu-id="11a08-126">Diese Formatierungsregeln betreffen die Sortierung und Anzeige von `using`-Direktiven und `Imports`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="11a08-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="11a08-127">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="11a08-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="11a08-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="11a08-129">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-129">Property</span></span>|<span data-ttu-id="11a08-130">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-130">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-131">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-131">**Option name**</span></span> | <span data-ttu-id="11a08-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="11a08-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="11a08-133">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-133">**Applicable languages**</span></span> | <span data-ttu-id="11a08-134">C# und Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11a08-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="11a08-135">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-135">**Introduced version**</span></span> | <span data-ttu-id="11a08-136">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-137">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-137">**Option values**</span></span> | <span data-ttu-id="11a08-138">`true` -Sortieren `System.*` `using` Sie-Direktiven alphabetisch, und platzieren Sie Sie vor anderen using-Direktiven.</span><span class="sxs-lookup"><span data-stu-id="11a08-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="11a08-139">`false` - `System.*` `using` Direktiven nicht vor anderen- `using` Direktiven platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="11a08-140">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-140">Code examples:</span></span>

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="11a08-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="11a08-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="11a08-142">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-142">Property</span></span>|<span data-ttu-id="11a08-143">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-143">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-144">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-144">**Option name**</span></span> | <span data-ttu-id="11a08-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="11a08-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="11a08-146">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-146">**Applicable languages**</span></span> | <span data-ttu-id="11a08-147">C# und Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11a08-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="11a08-148">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-148">**Introduced version**</span></span> | <span data-ttu-id="11a08-149">Visual Studio 2017 Version 15.5</span><span class="sxs-lookup"><span data-stu-id="11a08-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="11a08-150">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-150">**Option values**</span></span> | <span data-ttu-id="11a08-151">`true` – Leerzeile zwischen `using`-Direktivengruppen platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="11a08-152">`false` – keine Leerzeile zwischen `using`-Direktivengruppen platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="11a08-153">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-153">Code examples:</span></span>

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

## <a name="c-formatting-rules"></a><span data-ttu-id="11a08-154">C#-Formatierungs Regeln</span><span class="sxs-lookup"><span data-stu-id="11a08-154">C# formatting rules</span></span>

<span data-ttu-id="11a08-155">Die Formatierungsregeln in diesem Abschnitt gelten nur für C#-Code.</span><span class="sxs-lookup"><span data-stu-id="11a08-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="11a08-156">Newline-Optionen</span><span class="sxs-lookup"><span data-stu-id="11a08-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="11a08-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="11a08-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="11a08-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="11a08-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="11a08-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="11a08-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="11a08-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="11a08-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="11a08-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="11a08-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="11a08-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="11a08-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="11a08-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="11a08-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="11a08-164">Einzugsoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="11a08-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="11a08-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="11a08-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="11a08-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="11a08-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="11a08-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="11a08-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="11a08-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="11a08-171">Abstandsoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="11a08-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="11a08-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="11a08-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="11a08-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="11a08-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="11a08-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="11a08-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="11a08-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="11a08-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="11a08-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="11a08-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="11a08-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="11a08-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="11a08-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="11a08-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="11a08-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="11a08-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="11a08-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="11a08-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="11a08-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="11a08-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="11a08-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="11a08-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="11a08-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="11a08-194">Umbruchoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="11a08-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="11a08-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="11a08-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="11a08-197">Optionen für using-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="11a08-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="11a08-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="11a08-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="11a08-199">Optionen für „Neue Zeile“</span><span class="sxs-lookup"><span data-stu-id="11a08-199">New-line options</span></span>

<span data-ttu-id="11a08-200">Diese Formatierungsregeln beziehen sich auf die Verwendung neuer Zeilen zur Codeformatierung.</span><span class="sxs-lookup"><span data-stu-id="11a08-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="11a08-201">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-201">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="11a08-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="11a08-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="11a08-203">Diese Regel bezieht sich auf die Frage, ob eine öffnende geschweifte Klammer `{` in derselben Zeile wie der vorangehende Code oder in einer neuen Zeile platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="11a08-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="11a08-204">Für diese Regel geben Sie **Alle**, **Keine** oder mindestens ein Codeelement an, wie z.B. **Methoden** oder **Eigenschaften**, um festzulegen, wann diese Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11a08-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="11a08-205">Um mehrere Codeelemente anzugeben, trennen Sie diese durch Komma (,).</span><span class="sxs-lookup"><span data-stu-id="11a08-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="11a08-206">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-206">Property</span></span>|<span data-ttu-id="11a08-207">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-207">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-208">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-208">**Option name**</span></span> | <span data-ttu-id="11a08-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="11a08-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="11a08-210">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-210">**Applicable languages**</span></span> | <span data-ttu-id="11a08-211">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-211">C#</span></span> |
| <span data-ttu-id="11a08-212">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-212">**Introduced version**</span></span> | <span data-ttu-id="11a08-213">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-214">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-214">**Option values**</span></span> | <span data-ttu-id="11a08-215">`all` – geschweifte Klammern müssen für alle Ausdrücke in einer neuen Zeile stehen (Allman-Format).</span><span class="sxs-lookup"><span data-stu-id="11a08-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="11a08-216">`none` – geschweifte Klammern müssen für alle Ausdrücke in der gleichen Zeile stehen („K&R“).</span><span class="sxs-lookup"><span data-stu-id="11a08-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="11a08-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` – geschweifte Klammern müssen für das angegebene Codeelement in einer neuen Zeile stehen (Allman-Format).</span><span class="sxs-lookup"><span data-stu-id="11a08-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="11a08-218">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-218">Code examples:</span></span>

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="11a08-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="11a08-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="11a08-220">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-220">Property</span></span>|<span data-ttu-id="11a08-221">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-221">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-222">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-222">**Option name**</span></span> | <span data-ttu-id="11a08-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="11a08-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="11a08-224">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-224">**Applicable languages**</span></span> | <span data-ttu-id="11a08-225">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-225">C#</span></span> |
| <span data-ttu-id="11a08-226">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-226">**Introduced version**</span></span> | <span data-ttu-id="11a08-227">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-228">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-228">**Option values**</span></span> | <span data-ttu-id="11a08-229">`true` – `else`-Anweisungen in einer neuen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="11a08-230">`false` – `else`-Anweisungen in der gleichen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="11a08-231">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-231">Code examples:</span></span>

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="11a08-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="11a08-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="11a08-233">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-233">Property</span></span>|<span data-ttu-id="11a08-234">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-234">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-235">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-235">**Option name**</span></span> | <span data-ttu-id="11a08-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="11a08-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="11a08-237">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-237">**Applicable languages**</span></span> | <span data-ttu-id="11a08-238">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-238">C#</span></span> |
| <span data-ttu-id="11a08-239">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-239">**Introduced version**</span></span> | <span data-ttu-id="11a08-240">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-241">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-241">**Option values**</span></span> | <span data-ttu-id="11a08-242">`true` – `catch`-Anweisungen in einer neuen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="11a08-243">`false` – `catch`-Anweisungen in der gleichen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="11a08-244">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-244">Code examples:</span></span>

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="11a08-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="11a08-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="11a08-246">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-246">Property</span></span>|<span data-ttu-id="11a08-247">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-247">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-248">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-248">**Option name**</span></span> | <span data-ttu-id="11a08-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="11a08-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="11a08-250">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-250">**Applicable languages**</span></span> | <span data-ttu-id="11a08-251">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-251">C#</span></span> |
| <span data-ttu-id="11a08-252">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-252">**Introduced version**</span></span> | <span data-ttu-id="11a08-253">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-254">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-254">**Option values**</span></span> | <span data-ttu-id="11a08-255">`true` – `finally`-Anweisungen müssen nach der schließenden geschweiften Klammer in einer neuen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="11a08-256">`false` – `finally`-Anweisungen müssen nach der schließenden geschweiften Klammer in der gleichen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="11a08-257">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-257">Code examples:</span></span>

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="11a08-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="11a08-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="11a08-259">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-259">Property</span></span>|<span data-ttu-id="11a08-260">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-260">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-261">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-261">**Option name**</span></span> | <span data-ttu-id="11a08-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="11a08-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="11a08-263">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-263">**Applicable languages**</span></span> | <span data-ttu-id="11a08-264">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-264">C#</span></span> |
| <span data-ttu-id="11a08-265">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-265">**Introduced version**</span></span> | <span data-ttu-id="11a08-266">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-267">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-267">**Option values**</span></span> | <span data-ttu-id="11a08-268">`true` – Member von Objektinitialisierern müssen in separaten Zeilen stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="11a08-269">`false` – Member von Objektinitialisierern müssen in der gleichen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="11a08-270">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-270">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="11a08-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="11a08-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="11a08-272">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-272">Property</span></span>|<span data-ttu-id="11a08-273">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-273">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-274">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-274">**Option name**</span></span> | <span data-ttu-id="11a08-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="11a08-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="11a08-276">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-276">**Applicable languages**</span></span> | <span data-ttu-id="11a08-277">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-277">C#</span></span> |
| <span data-ttu-id="11a08-278">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-278">**Introduced version**</span></span> | <span data-ttu-id="11a08-279">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-280">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-280">**Option values**</span></span> | <span data-ttu-id="11a08-281">`true` – Member von anonymen Typen müssen in separaten Zeilen stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="11a08-282">`false` – Member von anonymen Typen müssen in der gleichen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="11a08-283">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-283">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="11a08-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="11a08-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="11a08-285">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-285">Property</span></span>|<span data-ttu-id="11a08-286">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-286">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-287">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-287">**Option name**</span></span> | <span data-ttu-id="11a08-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="11a08-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="11a08-289">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-289">**Applicable languages**</span></span> | <span data-ttu-id="11a08-290">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-290">C#</span></span> |
| <span data-ttu-id="11a08-291">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-291">**Introduced version**</span></span> | <span data-ttu-id="11a08-292">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-293">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-293">**Option values**</span></span> | <span data-ttu-id="11a08-294">`true` – Elemente von Abfrageausdrucksklauseln müssen in separaten Zeilen stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="11a08-295">`false` – Elemente von Abfrageausdrucksklauseln müssen in der gleichen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="11a08-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="11a08-296">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="11a08-297">Einzugsoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-297">Indentation options</span></span>

<span data-ttu-id="11a08-298">Diese Formatierungsregeln beziehen sich auf die Verwendung von Einzügen zur Codeformatierung.</span><span class="sxs-lookup"><span data-stu-id="11a08-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="11a08-299">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-299">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents_when_block = true
```

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="11a08-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="11a08-301">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-301">Property</span></span>|<span data-ttu-id="11a08-302">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-302">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-303">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-303">**Option name**</span></span> | <span data-ttu-id="11a08-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="11a08-305">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-305">**Applicable languages**</span></span> | <span data-ttu-id="11a08-306">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-306">C#</span></span> |
| <span data-ttu-id="11a08-307">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-307">**Introduced version**</span></span> | <span data-ttu-id="11a08-308">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-309">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-309">**Option values**</span></span> | <span data-ttu-id="11a08-310">`true` – „`switch` case“-Inhalte einrücken.</span><span class="sxs-lookup"><span data-stu-id="11a08-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="11a08-311">`false` – „`switch` case“-Inhalte nicht einrücken.</span><span class="sxs-lookup"><span data-stu-id="11a08-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="11a08-312">Wenn diese Regel auf **TRUE** festgelegt ist: i.</span><span class="sxs-lookup"><span data-stu-id="11a08-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="11a08-313">Wenn diese Regel auf **FALSE** festgelegt ist: d.</span><span class="sxs-lookup"><span data-stu-id="11a08-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="11a08-314">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-314">Code examples:</span></span>

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="11a08-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="11a08-316">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-316">Property</span></span>|<span data-ttu-id="11a08-317">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-317">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-318">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-318">**Option name**</span></span> | <span data-ttu-id="11a08-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="11a08-320">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-320">**Applicable languages**</span></span> | <span data-ttu-id="11a08-321">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-321">C#</span></span> |
| <span data-ttu-id="11a08-322">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-322">**Introduced version**</span></span> | <span data-ttu-id="11a08-323">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-324">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-324">**Option values**</span></span> | <span data-ttu-id="11a08-325">`true` – `switch`-Bezeichnungen einrücken.</span><span class="sxs-lookup"><span data-stu-id="11a08-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="11a08-326">`false` – `switch`-Bezeichner nicht einrücken.</span><span class="sxs-lookup"><span data-stu-id="11a08-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="11a08-327">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-327">Code examples:</span></span>

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_labels"></a><span data-ttu-id="11a08-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="11a08-329">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-329">Property</span></span>|<span data-ttu-id="11a08-330">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-330">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-331">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-331">**Option name**</span></span> | <span data-ttu-id="11a08-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="11a08-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="11a08-333">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-333">**Applicable languages**</span></span> | <span data-ttu-id="11a08-334">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-334">C#</span></span> |
| <span data-ttu-id="11a08-335">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-335">**Introduced version**</span></span> | <span data-ttu-id="11a08-336">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-337">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-337">**Option values**</span></span> | <span data-ttu-id="11a08-338">`flush_left` – Bezeichnungen werden in der Spalte ganz links angeordnet.</span><span class="sxs-lookup"><span data-stu-id="11a08-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="11a08-339">`one_less_than_current` – Bezeichnungen werden mit einem um eine Einheit geringerem Einzug platziert als der aktuelle Kontext.</span><span class="sxs-lookup"><span data-stu-id="11a08-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="11a08-340">`no_change` – Bezeichnungen werden mit dem gleichen Einzug platziert wie der aktuelle Kontext.</span><span class="sxs-lookup"><span data-stu-id="11a08-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="11a08-341">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-341">Code examples:</span></span>

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="11a08-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="11a08-343">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-343">Property</span></span>|<span data-ttu-id="11a08-344">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-344">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-345">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-345">**Option name**</span></span> | <span data-ttu-id="11a08-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="11a08-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="11a08-347">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-347">**Applicable languages**</span></span> | <span data-ttu-id="11a08-348">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-348">C#</span></span> |
| <span data-ttu-id="11a08-349">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="11a08-350">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-350">Code examples:</span></span>

```csharp
// csharp_indent_block_contents = true
static void Hello()
{
    Console.WriteLine("Hello");
}

// csharp_indent_block_contents = false
static void Hello()
{
Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_braces"></a><span data-ttu-id="11a08-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="11a08-351">csharp_indent_braces</span></span>

|<span data-ttu-id="11a08-352">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-352">Property</span></span>|<span data-ttu-id="11a08-353">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-353">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-354">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-354">**Option name**</span></span> | <span data-ttu-id="11a08-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="11a08-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="11a08-356">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-356">**Applicable languages**</span></span> | <span data-ttu-id="11a08-357">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-357">C#</span></span> |
| <span data-ttu-id="11a08-358">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="11a08-359">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-359">Code examples:</span></span>

```csharp
// csharp_indent_braces = true
static void Hello()
    {
    Console.WriteLine("Hello");
    }

// csharp_indent_braces = false
static void Hello()
{
    Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="11a08-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="11a08-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="11a08-361">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-361">Property</span></span>|<span data-ttu-id="11a08-362">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-362">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-363">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-363">**Option name**</span></span> | <span data-ttu-id="11a08-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="11a08-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="11a08-365">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-365">**Applicable languages**</span></span> | <span data-ttu-id="11a08-366">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-366">C#</span></span> |
| <span data-ttu-id="11a08-367">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="11a08-368">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-368">Code examples:</span></span>

```csharp
// csharp_indent_case_contents_when_block = true
case 0:
    {
        Console.WriteLine("Hello");
        break;
    }

// csharp_indent_case_contents_when_block = false
case 0:
{
    Console.WriteLine("Hello");
    break;
}
```

### <a name="spacing-options"></a><span data-ttu-id="11a08-369">Abstandsoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-369">Spacing options</span></span>

<span data-ttu-id="11a08-370">Diese Formatierungsregeln beziehen sich auf die Verwendung von Leerzeichen zur Codeformatierung.</span><span class="sxs-lookup"><span data-stu-id="11a08-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="11a08-371">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-371">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_after_comma = true
csharp_space_before_comma = false
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_before_semicolon_in_for_statement = false
csharp_space_around_declaration_statements = false
csharp_space_before_open_square_brackets = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_square_brackets = false
```

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="11a08-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="11a08-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="11a08-373">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-373">Property</span></span>|<span data-ttu-id="11a08-374">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-374">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-375">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-375">**Option name**</span></span> | <span data-ttu-id="11a08-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="11a08-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="11a08-377">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-377">**Applicable languages**</span></span> | <span data-ttu-id="11a08-378">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-378">C#</span></span> |
| <span data-ttu-id="11a08-379">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-379">**Introduced version**</span></span> | <span data-ttu-id="11a08-380">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-381">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-381">**Option values**</span></span> | <span data-ttu-id="11a08-382">`true` – Leerzeichen zwischen einer Umwandlung und dem Wert platzieren</span><span class="sxs-lookup"><span data-stu-id="11a08-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="11a08-383">`false` – Leerzeichen zwischen einer Umwandlung und dem Wert entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="11a08-384">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="11a08-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="11a08-386">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-386">Property</span></span>|<span data-ttu-id="11a08-387">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-387">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-388">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-388">**Option name**</span></span> | <span data-ttu-id="11a08-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="11a08-390">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-390">**Applicable languages**</span></span> | <span data-ttu-id="11a08-391">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-391">C#</span></span> |
| <span data-ttu-id="11a08-392">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-392">**Introduced version**</span></span> | <span data-ttu-id="11a08-393">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-394">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-394">**Option values**</span></span> | <span data-ttu-id="11a08-395">`true` – Leerzeichen nach einem Schlüsselwort in einer Ablaufsteuerungsanweisung wie einer `for`-Schleife platzieren</span><span class="sxs-lookup"><span data-stu-id="11a08-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="11a08-396">`false` – Leerzeichen nach einem Schlüsselwort in einer Ablaufsteuerungsanweisung wie einer `for`-Schleife entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="11a08-397">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="11a08-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="11a08-399">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-399">Property</span></span>|<span data-ttu-id="11a08-400">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-400">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-401">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-401">**Option name**</span></span> | <span data-ttu-id="11a08-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="11a08-403">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-403">**Applicable languages**</span></span> | <span data-ttu-id="11a08-404">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-404">C#</span></span> |
| <span data-ttu-id="11a08-405">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-405">**Introduced version**</span></span> | <span data-ttu-id="11a08-406">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-407">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-407">**Option values**</span></span> | <span data-ttu-id="11a08-408">`control_flow_statements` – Leerzeichen zwischen Klammern von Ablaufsteuerungsanweisungen einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="11a08-409">`expressions` – Leerzeichen zwischen Klammern von Ausdrücken einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="11a08-410">`type_casts` – Leerzeichen zwischen Klammern in Typumwandlungen einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="11a08-411">Wenn Sie diese Regel auslassen oder einen anderen Wert als `control_flow_statements`, `expressions` oder `type_casts` verwenden, wird die Einstellung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="11a08-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="11a08-412">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="11a08-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="11a08-414">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-414">Property</span></span>|<span data-ttu-id="11a08-415">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-415">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-416">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-416">**Option name**</span></span> | <span data-ttu-id="11a08-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="11a08-418">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-418">**Applicable languages**</span></span> | <span data-ttu-id="11a08-419">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-419">C#</span></span> |
| <span data-ttu-id="11a08-420">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-420">**Introduced version**</span></span> | <span data-ttu-id="11a08-421">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-422">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-422">**Option values**</span></span> | <span data-ttu-id="11a08-423">`true` – Leerzeichen vor dem Doppelpunkt für Basen oder Schnittstellen in einer Typdeklaration platzieren</span><span class="sxs-lookup"><span data-stu-id="11a08-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="11a08-424">`false` – Leerzeichen vor dem Doppelpunkt für Basen oder Schnittstellen in einer Typdeklaration entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="11a08-425">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-425">Code examples:</span></span>

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="11a08-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="11a08-427">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-427">Property</span></span>|<span data-ttu-id="11a08-428">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-428">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-429">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-429">**Option name**</span></span> | <span data-ttu-id="11a08-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="11a08-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="11a08-431">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-431">**Applicable languages**</span></span> | <span data-ttu-id="11a08-432">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-432">C#</span></span> |
| <span data-ttu-id="11a08-433">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-433">**Introduced version**</span></span> | <span data-ttu-id="11a08-434">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-435">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-435">**Option values**</span></span> | <span data-ttu-id="11a08-436">`true` – Leerzeichen nach dem Doppelpunkt für Basen oder Schnittstellen in einer Typdeklaration platzieren</span><span class="sxs-lookup"><span data-stu-id="11a08-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="11a08-437">`false` – Leerzeichen nach dem Doppelpunkt für Basen oder Schnittstellen in einer Typdeklaration entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="11a08-438">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-438">Code examples:</span></span>

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="11a08-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="11a08-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="11a08-440">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-440">Property</span></span>|<span data-ttu-id="11a08-441">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-441">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-442">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-442">**Option name**</span></span> | <span data-ttu-id="11a08-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="11a08-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="11a08-444">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-444">**Applicable languages**</span></span> | <span data-ttu-id="11a08-445">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-445">C#</span></span> |
| <span data-ttu-id="11a08-446">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-446">**Introduced version**</span></span> | <span data-ttu-id="11a08-447">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-448">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-448">**Option values**</span></span> | <span data-ttu-id="11a08-449">`before_and_after` – Leerzeichen vor und nach dem binären Operator einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="11a08-450">`none` – Leerzeichen vor und nach dem binären Operator entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="11a08-451">`ignore` – Leerzeichen um binäre Operatoren ignorieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="11a08-452">Wenn Sie diese Regel auslassen oder einen anderen Wert als `before_and_after`, `none` oder `ignore` verwenden, wird die Einstellung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="11a08-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="11a08-453">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="11a08-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="11a08-455">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-455">Property</span></span>|<span data-ttu-id="11a08-456">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-456">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-457">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-457">**Option name**</span></span> | <span data-ttu-id="11a08-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="11a08-459">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-459">**Applicable languages**</span></span> | <span data-ttu-id="11a08-460">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-460">C#</span></span> |
| <span data-ttu-id="11a08-461">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-461">**Introduced version**</span></span> | <span data-ttu-id="11a08-462">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-463">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-463">**Option values**</span></span> | <span data-ttu-id="11a08-464">`true` – hinter der öffnenden Klammer und vor der schließenden Klammer einer Parameterliste der Methodendeklaration ein Leerzeichen platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="11a08-465">`false` – Leerzeichen nach der öffnenden Klammer und vor der schließenden Klammer einer Parameterliste der Methodendeklaration entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="11a08-466">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="11a08-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="11a08-468">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-468">Property</span></span>|<span data-ttu-id="11a08-469">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-469">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-470">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-470">**Option name**</span></span> | <span data-ttu-id="11a08-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="11a08-472">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-472">**Applicable languages**</span></span> | <span data-ttu-id="11a08-473">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-473">C#</span></span> |
| <span data-ttu-id="11a08-474">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-474">**Introduced version**</span></span> | <span data-ttu-id="11a08-475">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-476">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-476">**Option values**</span></span> | <span data-ttu-id="11a08-477">`true` – bei einer Methodendeklaration innerhalb der Klammern für eine leere Parameterliste ein Leerzeichen einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="11a08-478">`false` – bei einer Methodendeklaration das Leerzeichen innerhalb der Klammern für eine leere Parameterliste entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="11a08-479">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-479">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="11a08-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="11a08-481">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-481">Property</span></span>|<span data-ttu-id="11a08-482">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-482">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-483">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-483">**Option name**</span></span> | <span data-ttu-id="11a08-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="11a08-485">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-485">**Applicable languages**</span></span> | <span data-ttu-id="11a08-486">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-486">C#</span></span> |
| <span data-ttu-id="11a08-487">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-487">**Option values**</span></span> | <span data-ttu-id="11a08-488">`true` – Leerzeichen zwischen dem Methodennamen und der öffnenden Klammer in der Methodendeklaration platzieren</span><span class="sxs-lookup"><span data-stu-id="11a08-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="11a08-489">`false` – Leerzeichen zwischen dem Methodennamen und der öffnenden Klammer in der Methodendeklaration entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="11a08-490">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="11a08-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="11a08-492">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-492">Property</span></span>|<span data-ttu-id="11a08-493">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-493">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-494">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-494">**Option name**</span></span> | <span data-ttu-id="11a08-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="11a08-496">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-496">**Applicable languages**</span></span> | <span data-ttu-id="11a08-497">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-497">C#</span></span> |
| <span data-ttu-id="11a08-498">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-498">**Introduced version**</span></span> | <span data-ttu-id="11a08-499">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-500">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-500">**Option values**</span></span> | <span data-ttu-id="11a08-501">`true` – hinter der öffnenden Klammer und vor der schließenden Klammer eines Methodenaufrufs ein Leerzeichen platzieren.</span><span class="sxs-lookup"><span data-stu-id="11a08-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="11a08-502">`false` – Leerzeichen nach der öffnenden Klammer und vor der schließenden Klammer eines Methodenaufrufs entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="11a08-503">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="11a08-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="11a08-505">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-505">Property</span></span>|<span data-ttu-id="11a08-506">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-506">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-507">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-507">**Option name**</span></span> | <span data-ttu-id="11a08-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="11a08-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="11a08-509">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-509">**Applicable languages**</span></span> | <span data-ttu-id="11a08-510">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-510">C#</span></span> |
| <span data-ttu-id="11a08-511">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-511">**Introduced version**</span></span> | <span data-ttu-id="11a08-512">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-513">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-513">**Option values**</span></span> | <span data-ttu-id="11a08-514">`true` – Leerzeichen zwischen Klammern um leere Argumentliste einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="11a08-515">`false` – Leerzeichen zwischen Klammern um leere Argumentliste entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="11a08-516">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-516">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="11a08-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="11a08-518">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-518">Property</span></span>|<span data-ttu-id="11a08-519">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-519">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-520">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-520">**Option name**</span></span> | <span data-ttu-id="11a08-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="11a08-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="11a08-522">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-522">**Applicable languages**</span></span> | <span data-ttu-id="11a08-523">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-523">C#</span></span> |
| <span data-ttu-id="11a08-524">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-524">**Introduced version**</span></span> | <span data-ttu-id="11a08-525">Visual Studio 2017-Version 15.7</span><span class="sxs-lookup"><span data-stu-id="11a08-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="11a08-526">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-526">**Option values**</span></span> | <span data-ttu-id="11a08-527">`true` – zwischen dem Namen des Methodenaufrufs und der öffnenden Klammer ein Leerzeichen einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="11a08-528">`false` – das Leerzeichen zwischen dem Namen des Methodenaufrufs und der öffnenden Klammer entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="11a08-529">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-529">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="11a08-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="11a08-531">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-531">Property</span></span>|<span data-ttu-id="11a08-532">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-532">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-533">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-533">**Option name**</span></span> | <span data-ttu-id="11a08-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="11a08-535">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-535">**Applicable languages**</span></span> | <span data-ttu-id="11a08-536">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-536">C#</span></span> |
| <span data-ttu-id="11a08-537">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-537">**Option values**</span></span> | <span data-ttu-id="11a08-538">`true` – Leerzeichen nach einem Komma einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="11a08-539">`false` – Leerzeichen nach einem Komma entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="11a08-540">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="11a08-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="11a08-542">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-542">Property</span></span>|<span data-ttu-id="11a08-543">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-543">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-544">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-544">**Option name**</span></span> | <span data-ttu-id="11a08-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="11a08-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="11a08-546">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-546">**Applicable languages**</span></span> | <span data-ttu-id="11a08-547">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-547">C#</span></span> |
| <span data-ttu-id="11a08-548">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-548">**Option values**</span></span> | <span data-ttu-id="11a08-549">`true` – Leerzeichen vor einem Komma einfügen</span><span class="sxs-lookup"><span data-stu-id="11a08-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="11a08-550">`false` – Leerzeichen vor einem Komma entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="11a08-551">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="11a08-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="11a08-553">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-553">Property</span></span>|<span data-ttu-id="11a08-554">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-554">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-555">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-555">**Option name**</span></span> | <span data-ttu-id="11a08-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="11a08-557">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-557">**Applicable languages**</span></span> | <span data-ttu-id="11a08-558">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-558">C#</span></span> |
| <span data-ttu-id="11a08-559">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-559">**Option values**</span></span> | <span data-ttu-id="11a08-560">`true` – Leerzeichen nach einem Punkt einfügen.</span><span class="sxs-lookup"><span data-stu-id="11a08-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="11a08-561">`false` – Leerzeichen nach einem Punkt entfernen.</span><span class="sxs-lookup"><span data-stu-id="11a08-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="11a08-562">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="11a08-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="11a08-564">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-564">Property</span></span>|<span data-ttu-id="11a08-565">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-565">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-566">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-566">**Option name**</span></span> | <span data-ttu-id="11a08-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="11a08-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="11a08-568">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-568">**Applicable languages**</span></span> | <span data-ttu-id="11a08-569">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-569">C#</span></span> |
| <span data-ttu-id="11a08-570">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-570">**Option values**</span></span> | <span data-ttu-id="11a08-571">`true` – Leerzeichen vor einem Punkt einfügen</span><span class="sxs-lookup"><span data-stu-id="11a08-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="11a08-572">`false` – Leerzeichen vor einem Punkt entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="11a08-573">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="11a08-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="11a08-575">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-575">Property</span></span>|<span data-ttu-id="11a08-576">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-576">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-577">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-577">**Option name**</span></span> | <span data-ttu-id="11a08-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="11a08-579">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-579">**Applicable languages**</span></span> | <span data-ttu-id="11a08-580">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-580">C#</span></span> |
| <span data-ttu-id="11a08-581">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-581">**Option values**</span></span> | <span data-ttu-id="11a08-582">`true` – Leerzeichen nach jedem Semikolon in einer `for`-Anweisung einfügen</span><span class="sxs-lookup"><span data-stu-id="11a08-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="11a08-583">`false` – Leerzeichen nach jedem Semikolon in einer `for`-Anweisung entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="11a08-584">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

##### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="11a08-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="11a08-586">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-586">Property</span></span>|<span data-ttu-id="11a08-587">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-587">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-588">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-588">**Option name**</span></span> | <span data-ttu-id="11a08-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="11a08-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="11a08-590">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-590">**Applicable languages**</span></span> | <span data-ttu-id="11a08-591">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-591">C#</span></span> |
| <span data-ttu-id="11a08-592">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-592">**Option values**</span></span> | <span data-ttu-id="11a08-593">`true` – Leerzeichen vor jedem Semikolon in einer `for`-Anweisung einfügen</span><span class="sxs-lookup"><span data-stu-id="11a08-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="11a08-594">`false` – Leerzeichen vor jedem Semikolon in einer `for`-Anweisung entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="11a08-595">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="11a08-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="11a08-597">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-597">Property</span></span>|<span data-ttu-id="11a08-598">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-598">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-599">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-599">**Option name**</span></span> | <span data-ttu-id="11a08-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="11a08-601">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-601">**Applicable languages**</span></span> | <span data-ttu-id="11a08-602">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-602">C#</span></span> |
| <span data-ttu-id="11a08-603">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-603">**Option values**</span></span> | <span data-ttu-id="11a08-604">`ignore` – Keine zusätzlichen Leerzeichen in Deklarationsanweisungen entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="11a08-605">`false` – Zusätzliche Leerzeichen in Deklarationsanweisungen entfernen</span><span class="sxs-lookup"><span data-stu-id="11a08-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="11a08-606">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="11a08-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="11a08-608">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-608">Property</span></span>|<span data-ttu-id="11a08-609">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-609">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-610">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-610">**Option name**</span></span> | <span data-ttu-id="11a08-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="11a08-612">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-612">**Applicable languages**</span></span> | <span data-ttu-id="11a08-613">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-613">C#</span></span> |
| <span data-ttu-id="11a08-614">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-614">**Option values**</span></span> | <span data-ttu-id="11a08-615">`true` – Leerzeichen vor öffnenden eckigen Klammern einfügen `[`</span><span class="sxs-lookup"><span data-stu-id="11a08-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="11a08-616">`false` – Leerzeichen vor öffnenden eckigen Klammern entfernen `[`</span><span class="sxs-lookup"><span data-stu-id="11a08-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="11a08-617">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="11a08-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="11a08-619">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-619">Property</span></span>|<span data-ttu-id="11a08-620">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-620">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-621">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-621">**Option name**</span></span> | <span data-ttu-id="11a08-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="11a08-623">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-623">**Applicable languages**</span></span> | <span data-ttu-id="11a08-624">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-624">C#</span></span> |
| <span data-ttu-id="11a08-625">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-625">**Option values**</span></span> | <span data-ttu-id="11a08-626">`true` – Leerzeichen zwischen leeren eckigen Klammern einfügen `[ ]`</span><span class="sxs-lookup"><span data-stu-id="11a08-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="11a08-627">`false` – Leerzeichen zwischen leeren eckigen Klammern entfernen `[]`</span><span class="sxs-lookup"><span data-stu-id="11a08-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="11a08-628">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="11a08-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="11a08-630">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-630">Property</span></span>|<span data-ttu-id="11a08-631">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-631">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-632">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-632">**Option name**</span></span> | <span data-ttu-id="11a08-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="11a08-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="11a08-634">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-634">**Applicable languages**</span></span> | <span data-ttu-id="11a08-635">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-635">C#</span></span> |
| <span data-ttu-id="11a08-636">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-636">**Option values**</span></span> | <span data-ttu-id="11a08-637">`true` – Leerzeichen in nicht leeren eckigen Klammern einfügen `[ 0 ]`</span><span class="sxs-lookup"><span data-stu-id="11a08-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="11a08-638">`false` – Leerzeichen aus nicht leeren eckigen Klammern entfernen `[0]`</span><span class="sxs-lookup"><span data-stu-id="11a08-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="11a08-639">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="11a08-640">Umbruchoptionen</span><span class="sxs-lookup"><span data-stu-id="11a08-640">Wrap options</span></span>

<span data-ttu-id="11a08-641">Diese Formatierungsregeln beziehen sich auf die Verwendung von einzelnen Zeilen im Vergleich zu separaten Zeilen bei Anweisungen und Codeblöcken.</span><span class="sxs-lookup"><span data-stu-id="11a08-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="11a08-642">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="11a08-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="11a08-644">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-644">Property</span></span>|<span data-ttu-id="11a08-645">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-645">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-646">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-646">**Option name**</span></span> | <span data-ttu-id="11a08-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="11a08-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="11a08-648">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-648">**Applicable languages**</span></span> | <span data-ttu-id="11a08-649">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-649">C#</span></span> |
| <span data-ttu-id="11a08-650">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-650">**Introduced version**</span></span> | <span data-ttu-id="11a08-651">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-652">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-652">**Option values**</span></span> | <span data-ttu-id="11a08-653">`true` – Anweisungen und Memberdeklarationen in der gleichen Zeile belassen.</span><span class="sxs-lookup"><span data-stu-id="11a08-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="11a08-654">`false` – Anweisungen und Memberdeklarationen in verschiedenen Zeilen belassen.</span><span class="sxs-lookup"><span data-stu-id="11a08-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="11a08-655">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="11a08-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="11a08-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="11a08-657">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-657">Property</span></span>|<span data-ttu-id="11a08-658">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-658">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-659">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-659">**Option name**</span></span> | <span data-ttu-id="11a08-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="11a08-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="11a08-661">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-661">**Applicable languages**</span></span> | <span data-ttu-id="11a08-662">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-662">C#</span></span> |
| <span data-ttu-id="11a08-663">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-663">**Introduced version**</span></span> | <span data-ttu-id="11a08-664">Visual Studio 2017 Version 15.3</span><span class="sxs-lookup"><span data-stu-id="11a08-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="11a08-665">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-665">**Option values**</span></span> | <span data-ttu-id="11a08-666">`true` – Codeblock in einzelner Zeile belassen.</span><span class="sxs-lookup"><span data-stu-id="11a08-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="11a08-667">`false` – Codeblock in separaten Zeilen belassen.</span><span class="sxs-lookup"><span data-stu-id="11a08-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="11a08-668">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="11a08-669">Optionen für using-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="11a08-669">Using directive options</span></span>

<span data-ttu-id="11a08-670">Diese Formatierungsregel bezieht sich auf die Verwendung von using-Anweisungen, die innerhalb oder außerhalb eines Namespaces platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="11a08-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="11a08-671">*EDITORCONFIG-Beispieldatei:*</span><span class="sxs-lookup"><span data-stu-id="11a08-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="11a08-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="11a08-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="11a08-673">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="11a08-673">Property</span></span>|<span data-ttu-id="11a08-674">Wert</span><span class="sxs-lookup"><span data-stu-id="11a08-674">Value</span></span>|
|-|-|
| <span data-ttu-id="11a08-675">**Options Name**</span><span class="sxs-lookup"><span data-stu-id="11a08-675">**Option name**</span></span> | <span data-ttu-id="11a08-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="11a08-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="11a08-677">**Gültige Sprachen**</span><span class="sxs-lookup"><span data-stu-id="11a08-677">**Applicable languages**</span></span> | <span data-ttu-id="11a08-678">C#</span><span class="sxs-lookup"><span data-stu-id="11a08-678">C#</span></span> |
| <span data-ttu-id="11a08-679">**Eingeführt in Version**</span><span class="sxs-lookup"><span data-stu-id="11a08-679">**Introduced version**</span></span> | <span data-ttu-id="11a08-680">Visual Studio 2019 Version 16.1</span><span class="sxs-lookup"><span data-stu-id="11a08-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="11a08-681">**Optionswerte**</span><span class="sxs-lookup"><span data-stu-id="11a08-681">**Option values**</span></span> | <span data-ttu-id="11a08-682">`outside_namespace`: Platzieren Sie using-Anweisungen bei diesem Wert außerhalb des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="11a08-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="11a08-683">`inside_namespace`: Platzieren Sie using-Anweisungen bei diesem Wert innerhalb des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="11a08-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="11a08-684">Codebeispiele:</span><span class="sxs-lookup"><span data-stu-id="11a08-684">Code examples:</span></span>

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{

}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
}
```

## <a name="see-also"></a><span data-ttu-id="11a08-685">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11a08-685">See also</span></span>

- [<span data-ttu-id="11a08-686">Sprachregeln</span><span class="sxs-lookup"><span data-stu-id="11a08-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="11a08-687">Benennungsregeln</span><span class="sxs-lookup"><span data-stu-id="11a08-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="11a08-688">.Net-Codestil-Regel Referenz</span><span class="sxs-lookup"><span data-stu-id="11a08-688">.NET code style rules reference</span></span>](index.md)
