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
ms.openlocfilehash: 0eea5e89ac5055a45d9ead14363cc2f2fc574401
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191078"
---
# <a name="naming-rules"></a><span data-ttu-id="90000-103">Benennungsregeln</span><span class="sxs-lookup"><span data-stu-id="90000-103">Naming rules</span></span>

<span data-ttu-id="90000-104">Benennungs Regeln beziehen sich auf die Benennung von Code Elementen der .NET-Programmiersprache, wie z. b. Klassen, Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="90000-104">Naming rules concern the naming of .NET programming language code elements, such as classes, properties, and methods.</span></span> <span data-ttu-id="90000-105">Sie können beispielsweise angeben, dass öffentliche Mitglieder großgeschrieben werden oder dass private Felder mit `_` beginnen müssen.</span><span class="sxs-lookup"><span data-stu-id="90000-105">For example, you can specify that public members must be capitalized or that private fields must begin with `_`.</span></span>

<span data-ttu-id="90000-106">Eine Benennungs Regel besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="90000-106">A naming rule has three parts:</span></span>

* <span data-ttu-id="90000-107">Die Gruppe der Symbole, auf die Sie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="90000-107">The group of symbols it applies to.</span></span>
* <span data-ttu-id="90000-108">Der Benennungs Stil, der der Regel zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90000-108">The naming style to associate with the rule.</span></span>
* <span data-ttu-id="90000-109">Der Schweregrad für die Erzwingung der Konvention.</span><span class="sxs-lookup"><span data-stu-id="90000-109">The severity for enforcing the convention.</span></span>

<span data-ttu-id="90000-110">Benennungs Regeln definieren Sie in einer Editor config-Datei.</span><span class="sxs-lookup"><span data-stu-id="90000-110">You define naming rules in an EditorConfig file.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="90000-111">Allgemeine Syntax</span><span class="sxs-lookup"><span data-stu-id="90000-111">General syntax</span></span>

<span data-ttu-id="90000-112">Legen Sie zum Definieren einer Benennungs Regel, einer Symbolgruppe oder eines Benennungs Stils eine oder mehrere Eigenschaften mit der folgenden Syntax fest:</span><span class="sxs-lookup"><span data-stu-id="90000-112">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<prefix>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="90000-113">Jede Eigenschaft sollte nur einmal festgelegt werden, aber einige Einstellungen lassen mehrere durch Trennzeichen getrennte Werte zu.</span><span class="sxs-lookup"><span data-stu-id="90000-113">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="90000-114">Die Reihenfolge der Eigenschaften ist ohne Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="90000-114">The order of the properties is not important.</span></span>

### \<prefix>

<span data-ttu-id="90000-115">**\<prefix>** Gibt an, welche Art von Element &mdash; namens Regel, Symbolgruppe oder Benennungs Stil definiert wird, &mdash; und muss eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="90000-115">**\<prefix>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="90000-116">So legen Sie eine Eigenschaft fest</span><span class="sxs-lookup"><span data-stu-id="90000-116">To set a property for</span></span> | <span data-ttu-id="90000-117">Verwenden des Präfixes</span><span class="sxs-lookup"><span data-stu-id="90000-117">Use the prefix</span></span> | <span data-ttu-id="90000-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90000-118">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="90000-119">Benennungs Regel</span><span class="sxs-lookup"><span data-stu-id="90000-119">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="90000-120">Symbol Gruppe</span><span class="sxs-lookup"><span data-stu-id="90000-120">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="90000-121">Benennungs Stil</span><span class="sxs-lookup"><span data-stu-id="90000-121">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="90000-122">Jeder Typ von Definitions &mdash; [Benennungs Regel](#naming-rule-properties), [Symbolgruppe](#symbol-group-properties)oder [Benennungs Stil](#naming-style-properties) &mdash; hat seine eigenen unterstützten Eigenschaften, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90000-122">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="90000-123">**\<title>** ein beschreibender Name, den Sie auswählen, der mehrere Eigenschafts Einstellungen einer einzelnen Definition zuordnet.</span><span class="sxs-lookup"><span data-stu-id="90000-123">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="90000-124">Die folgenden Eigenschaften ergeben z. b. zwei Symbolgruppen Definitionen, `interface` und `types` , von denen jeweils zwei Eigenschaften festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="90000-124">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="90000-125">Eigenschaften von Benennungs Regeln</span><span class="sxs-lookup"><span data-stu-id="90000-125">Naming rule properties</span></span>

<span data-ttu-id="90000-126">Alle Eigenschaften der Benennungs Regel sind erforderlich, damit eine Regel wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="90000-126">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="90000-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="90000-127">Property</span></span> | <span data-ttu-id="90000-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90000-128">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="90000-129">Der Titel der Symbolgruppe, die die Symbole definiert, auf die diese Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90000-129">The title of the symbol group, defining the symbols to which this rule should be applied</span></span> |
| `style` | <span data-ttu-id="90000-130">Der Titel des Namens Stils, der dieser Regel zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90000-130">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="90000-131">Legt den Schweregrad fest, mit dem die Benennungs Regel erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="90000-131">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="90000-132">Legen Sie den zugeordneten Wert auf einen der verfügbaren [Schweregrade](../configuration-options.md#severity-level)fest. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90000-132">Set the associated value to one of the available [severity levels](../configuration-options.md#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="90000-133">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="90000-133">**Notes:**</span></span>

1. <span data-ttu-id="90000-134">Die Schweregrad Spezifikation innerhalb einer Benennungs Regel wird nur innerhalb der Entwicklungs-IDES, z. b. Visual Studio, berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="90000-134">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="90000-135">Diese Einstellung wird von den c#-oder VB-Compilern nicht verstanden und daher während des Builds nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="90000-135">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="90000-136">Stattdessen sollten Sie den Schweregrad mithilfe der Regel-ID-basierten Schweregrad Konfiguration wie in [diesem Abschnitt](#rule-id-ide1006-naming-rule-violation)erläutert festlegen, um Benennungs Stilregeln für den Build zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="90000-136">Instead, to enforce naming style rules on build, you should set the severity by using the rule ID-based severity configuration as explained in [this section](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="90000-137">Weitere Informationen finden Sie in diesem [GitHub-Problem](https://github.com/dotnet/roslyn/issues/44201).</span><span class="sxs-lookup"><span data-stu-id="90000-137">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="rule-order"></a><span data-ttu-id="90000-138">Regelreihenfolge</span><span class="sxs-lookup"><span data-stu-id="90000-138">Rule order</span></span>

<span data-ttu-id="90000-139">Die Reihenfolge, in der Benennungs Regeln in einer Editor config-Datei definiert sind, spielt keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="90000-139">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="90000-140">Die Benennungs Regeln werden automatisch nach der Definition der Regeln selbst geordnet.</span><span class="sxs-lookup"><span data-stu-id="90000-140">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="90000-141">Die Erweiterung [EditorConfig Language Service](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) kann eine EditorConfig-Datei analysieren und Fälle melden, in denen sich die Regelreihenfolge in der Datei von der Reihenfolge unterscheidet, die vom Compiler zur Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90000-141">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="90000-142">Wenn Sie eine frühere Version von Visual Studio als Visual Studio 2019 Version 16,2 verwenden, sollten Benennungs Regeln von der spezifischsten zu den spezifischsten in der Editor config-Datei angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="90000-142">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="90000-143">Die erste Regel, die angewendet werden kann, ist die einzige Regel, die angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="90000-143">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="90000-144">Wenn es jedoch mehrere *Regeleigenschaften* mit dem gleichen Namen gibt, hat die zuletzt gefundene Eigenschaft mit diesem Namen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="90000-144">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="90000-145">Weitere Informationen finden Sie unter [Dateihierarchie und Rangfolge](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span><span class="sxs-lookup"><span data-stu-id="90000-145">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="90000-146">Symbol Gruppen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="90000-146">Symbol group properties</span></span>

<span data-ttu-id="90000-147">Sie können die folgenden Eigenschaften für Symbolgruppen festlegen, um einzuschränken, welche Symbole in der Gruppe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="90000-147">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="90000-148">Wenn Sie mehrere Werte in einer einzelnen Eigenschafts Einstellung angeben möchten, trennen Sie diese durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="90000-148">To specify multiple values in a single property setting, separate them with a comma.</span></span>

| <span data-ttu-id="90000-149">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="90000-149">Property</span></span> | <span data-ttu-id="90000-150">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90000-150">Description</span></span> | <span data-ttu-id="90000-151">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="90000-151">Allowed values</span></span> | <span data-ttu-id="90000-152">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="90000-152">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="90000-153">Arten von Symbolen in Gruppe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90000-153">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="90000-154">`*` (verwenden Sie diesen Wert, um alle Symbole anzugeben)</span><span class="sxs-lookup"><span data-stu-id="90000-154">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="90000-155">Ja</span><span class="sxs-lookup"><span data-stu-id="90000-155">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="90000-156">Barrierefreiheits Stufen der Symbole in der Gruppe</span><span class="sxs-lookup"><span data-stu-id="90000-156">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="90000-157">`*` (verwenden Sie diesen Wert, um alle Zugriffsebenen anzugeben)</span><span class="sxs-lookup"><span data-stu-id="90000-157">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="90000-158">`internal` oder `friend`</span><span class="sxs-lookup"><span data-stu-id="90000-158">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="90000-159">`protected_internal` oder `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="90000-159">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="90000-160">`local` (für Symbole, die in einer Methode definiert sind)</span><span class="sxs-lookup"><span data-stu-id="90000-160">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="90000-161">Ja</span><span class="sxs-lookup"><span data-stu-id="90000-161">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="90000-162">Symbole nur mit _allen_ angegebenen modifiziererzeichen <sup>2</sup> vergleichen</span><span class="sxs-lookup"><span data-stu-id="90000-162">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="90000-163">`abstract` oder `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="90000-163">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="90000-164">`static` oder `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="90000-164">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="90000-165">Nein</span><span class="sxs-lookup"><span data-stu-id="90000-165">No</span></span> |

<span data-ttu-id="90000-166">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="90000-166">**Notes:**</span></span>

1. <span data-ttu-id="90000-167">Tupelmember werden in derzeit nicht unterstützt `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="90000-167">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="90000-168">Die Symbolgruppe gleicht _alle_ modifiziererer in der `required_modifiers` Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="90000-168">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="90000-169">Wenn Sie diese Eigenschaft weglassen, sind keine spezifischen modifiziererer für eine Entsprechung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90000-169">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="90000-170">Das bedeutet, dass die Modifizierer eines Symbols keine Auswirkungen darauf haben, ob die Regel angewendet wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="90000-170">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="90000-171">Wenn die Gruppe `static` oder `shared` in der- `required_modifiers` Eigenschaft aufweist, enthält die Gruppe auch `const` Symbole, da Sie implizit sind `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="90000-171">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="90000-172">Wenn Sie jedoch nicht möchten, dass die `static` Benennungs Regel auf `const` Symbole angewendet wird, können Sie eine neue Benennungs Regel mit einer Symbolgruppe von erstellen `const` .</span><span class="sxs-lookup"><span data-stu-id="90000-172">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="90000-173">Benennungs Stileigenschaften</span><span class="sxs-lookup"><span data-stu-id="90000-173">Naming style properties</span></span>

<span data-ttu-id="90000-174">Ein Benennungs Stil definiert die Konventionen, die Sie mit der Regel erzwingen möchten.</span><span class="sxs-lookup"><span data-stu-id="90000-174">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="90000-175">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="90000-175">For example:</span></span>

* <span data-ttu-id="90000-176">Großbuchstaben mit `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="90000-176">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="90000-177">Beginnt mit `m_`</span><span class="sxs-lookup"><span data-stu-id="90000-177">Starts with `m_`</span></span>
* <span data-ttu-id="90000-178">Endet mit `_g`</span><span class="sxs-lookup"><span data-stu-id="90000-178">Ends with `_g`</span></span>
* <span data-ttu-id="90000-179">Getrennte Wörter mit `__`</span><span class="sxs-lookup"><span data-stu-id="90000-179">Separate words with `__`</span></span>

<span data-ttu-id="90000-180">Sie können die folgenden Eigenschaften für einen Benennungs Stil festlegen:</span><span class="sxs-lookup"><span data-stu-id="90000-180">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="90000-181">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="90000-181">Property</span></span> | <span data-ttu-id="90000-182">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90000-182">Description</span></span> | <span data-ttu-id="90000-183">Zulässige Werte</span><span class="sxs-lookup"><span data-stu-id="90000-183">Allowed values</span></span> | <span data-ttu-id="90000-184">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="90000-184">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="90000-185">Groß-/Kleinschreibung für Wörter innerhalb des Symbols</span><span class="sxs-lookup"><span data-stu-id="90000-185">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="90000-186">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90000-186">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="90000-187">Muss mit diesen Zeichen beginnen</span><span class="sxs-lookup"><span data-stu-id="90000-187">Must begin with these characters</span></span> | | <span data-ttu-id="90000-188">Nein</span><span class="sxs-lookup"><span data-stu-id="90000-188">No</span></span> |
| `required_suffix` | <span data-ttu-id="90000-189">Muss mit diesen Zeichen enden</span><span class="sxs-lookup"><span data-stu-id="90000-189">Must end with these characters</span></span> | | <span data-ttu-id="90000-190">Nein</span><span class="sxs-lookup"><span data-stu-id="90000-190">No</span></span> |
| `word_separator` | <span data-ttu-id="90000-191">Wörter innerhalb des Symbols müssen durch dieses Zeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="90000-191">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="90000-192">Nein</span><span class="sxs-lookup"><span data-stu-id="90000-192">No</span></span> |

<span data-ttu-id="90000-193">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="90000-193">**Notes:**</span></span>

1. <span data-ttu-id="90000-194">Sie müssen im Rahmen Ihres Benennungsstils einen Stil für die Groß-/Kleinschreibung angeben. Andernfalls wird Ihr Benennungsstil möglicherweise ignoriert.</span><span class="sxs-lookup"><span data-stu-id="90000-194">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="90000-195">Standardbenennungsstile</span><span class="sxs-lookup"><span data-stu-id="90000-195">Default naming styles</span></span>

<span data-ttu-id="90000-196">Wenn Sie keine benutzerdefinierten Benennungs Regeln angeben, werden die folgenden Standard Stile verwendet:</span><span class="sxs-lookup"><span data-stu-id="90000-196">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="90000-197">Bei Klassen, Strukturen, Enumerationen, Eigenschaften und Ereignissen mit `public`-, `private`-, `internal`-, `protected`- oder `protected_internal`-Zugriff, ist der standardmäßige Benennungsstil die Pascal-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="90000-197">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="90000-198">Bei Schnittstellen mit `public`-, `private`-, `internal`-, `protected`- oder `protected_internal`-Zugriff ist der standardmäßige Benennungsstil die Pascal-Schreibweise mit dem erforderlichen Präfix **I**.</span><span class="sxs-lookup"><span data-stu-id="90000-198">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="example"></a><span data-ttu-id="90000-199">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90000-199">Example</span></span>

<span data-ttu-id="90000-200">Die folgende *EDITORCONFIG-Datei* enthält eine Namenskonvention, die angibt, dass öffentliche Eigenschaften, Methoden, Felder, Ereignisse und Delegaten großgeschrieben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="90000-200">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="90000-201">Beachten Sie, dass diese Namenskonvention mehrere Arten von Symbolen angibt, für die die Regel gelten soll, wobei die Werte durch ein Komma getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="90000-201">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

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

## <a name="rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="90000-202">Regel-ID: "IDE1006" (Verstoß gegen Benennungs Regel)</span><span class="sxs-lookup"><span data-stu-id="90000-202">Rule ID: "IDE1006" (Naming rule violation)</span></span>

<span data-ttu-id="90000-203">Alle Benennungs Optionen verfügen über Regel `IDE1006` -ID und Titel `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="90000-203">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="90000-204">Sie können den Schweregrad von Benennungs Verstößen Global in einer editorconfig-Datei mit der folgenden Syntax konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="90000-204">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="90000-205">Der Schweregrad muss `warning` oder sein `error` , um [beim Build erzwungen](../overview.md#code-style-analysis)zu werden.</span><span class="sxs-lookup"><span data-stu-id="90000-205">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="90000-206">Alle möglichen Schweregrad Werte finden Sie unter [Schweregrad](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="90000-206">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="see-also"></a><span data-ttu-id="90000-207">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90000-207">See also</span></span>

- [<span data-ttu-id="90000-208">Sprachregeln</span><span class="sxs-lookup"><span data-stu-id="90000-208">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="90000-209">Formatierungsregeln</span><span class="sxs-lookup"><span data-stu-id="90000-209">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="90000-210">Roslyn-Benennungs Regeln</span><span class="sxs-lookup"><span data-stu-id="90000-210">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="90000-211">.Net-Codestil-Regel Referenz</span><span class="sxs-lookup"><span data-stu-id="90000-211">.NET code style rules reference</span></span>](index.md)
