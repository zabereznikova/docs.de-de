---
title: Konfigurieren von Code Analyse Regeln
description: Erfahren Sie, wie Sie Code Analyse Regeln in einer Analyse Konfigurationsdatei konfigurieren.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: 4f7b392a2b066023fec75c5295bd94651654d645
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851789"
---
# <a name="configuration-options-for-code-analysis"></a><span data-ttu-id="f900b-103">Konfigurationsoptionen für die Code Analyse</span><span class="sxs-lookup"><span data-stu-id="f900b-103">Configuration options for code analysis</span></span>

<span data-ttu-id="f900b-104">Code Analyse Regeln verfügen über verschiedene Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="f900b-104">Code analysis rules have various configuration options.</span></span> <span data-ttu-id="f900b-105">Diese Optionen werden als Schlüssel-Wert-Paare in einer [Analyse Konfigurationsdatei](configuration-files.md) mithilfe der-Syntax angegeben `<option key> = <option value>` .</span><span class="sxs-lookup"><span data-stu-id="f900b-105">These options are specified as key-value pairs in an [analyzer configuration file](configuration-files.md) using the syntax `<option key> = <option value>`.</span></span>

<span data-ttu-id="f900b-106">Die am häufigsten konfigurierten Optionen sind der [Schweregrad einer Regel](#severity-level).</span><span class="sxs-lookup"><span data-stu-id="f900b-106">The most common option you'll configure is a [rule's severity](#severity-level).</span></span> <span data-ttu-id="f900b-107">Sie können den Schweregrad für alle Analyse Regeln konfigurieren, einschließlich [Code Qualitätsregeln](quality-rules/index.md) und Regeln für den [Code Stil](style-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="f900b-107">You can configure severity level for all analyzer rules, including [code quality rules](quality-rules/index.md) and [code style rules](style-rules/index.md).</span></span> <span data-ttu-id="f900b-108">Wenn Sie z. b. eine Regel als Warnung aktivieren möchten, können Sie das folgende Schlüssel-Wert-Paar zu einer Datei hinzufügen EditorConfig .</span><span class="sxs-lookup"><span data-stu-id="f900b-108">For example, to enable a rule as a warning, you can add the following key-value pair to an EditorConfig file.</span></span>

`dotnet_diagnostic.<rule ID>.severity = warning`

<span data-ttu-id="f900b-109">Sie können auch zusätzliche Optionen zum Anpassen des Regel Verhaltens konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f900b-109">You can also configure additional options to customize rule behavior:</span></span>

- <span data-ttu-id="f900b-110">Code Qualitätsregeln verfügen über [zusätzliche Optionen](code-quality-rule-options.md) zum Konfigurieren des Verhaltens, z. b. die Methodennamen, auf die eine Regel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f900b-110">Code quality rules have [additional options](code-quality-rule-options.md) to configure behavior, such as which method names a rule should apply to.</span></span>
- <span data-ttu-id="f900b-111">Code Formatregeln verfügen über [benutzerdefinierte Optionen für den Code Stil](code-style-rule-options.md).</span><span class="sxs-lookup"><span data-stu-id="f900b-111">Code style rules have [custom code style options](code-style-rule-options.md).</span></span>
- <span data-ttu-id="f900b-112">Analyse Regeln von Drittanbietern können eigene Konfigurationsoptionen mit benutzerdefinierten Schlüsselnamen und Wert Formaten definieren.</span><span class="sxs-lookup"><span data-stu-id="f900b-112">Third party analyzer rules can define their own configuration options, with custom key names and value formats.</span></span>

<span data-ttu-id="f900b-113">Die Syntax zum Konfigurieren des schwere Grads einer bestimmten Regel in einer [Analyse Konfigurationsdatei](configuration-files.md) lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f900b-113">The syntax for configuring a specific rule's severity in an [analyzer configuration file](configuration-files.md) is as follows:</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a><span data-ttu-id="f900b-114">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="f900b-114">General options</span></span>

<span data-ttu-id="f900b-115">Diese Optionen gelten für die Code Analyse als Ganzes.</span><span class="sxs-lookup"><span data-stu-id="f900b-115">These options apply to code analysis as a whole.</span></span> <span data-ttu-id="f900b-116">Sie können nicht nur auf eine einzelne Regel oder einen Satz von Regeln angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f900b-116">They cannot be applied only to a single rule or set of rules.</span></span>

### <a name="exclude-generated-code"></a><span data-ttu-id="f900b-117">Generierten Code ausschließen</span><span class="sxs-lookup"><span data-stu-id="f900b-117">Exclude generated code</span></span>

<span data-ttu-id="f900b-118">Sie können zusätzliche Dateien und Ordner so konfigurieren, dass Sie als generierten Code behandelt werden, indem Sie `generated_code = true | false` der [Konfigurationsdatei](configuration-files.md)einen Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f900b-118">You can configure additional files and folders to be treated as generated code by adding a `generated_code = true | false` entry to your [configuration file](configuration-files.md).</span></span> <span data-ttu-id="f900b-119">.NET Code Analyzer-Warnungen sind für generierte Code Dateien, z. b. vom Designer generierte Dateien, nicht nützlich, die Benutzer nicht bearbeiten können, um Verstöße zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f900b-119">.NET code analyzer warnings aren't useful on generated code files, such as designer-generated files, which users can't edit to fix any violations.</span></span> <span data-ttu-id="f900b-120">In den meisten Fällen überspringen Code Analysen generierte Code Dateien und melden keine Verstöße gegen diese Dateien.</span><span class="sxs-lookup"><span data-stu-id="f900b-120">In most cases, code analyzers skip generated code files and don't report violations on these files.</span></span>

<span data-ttu-id="f900b-121">Standardmäßig werden Dateien mit bestimmten Dateierweiterungen oder automatisch generierten Datei Headern als generierte Code Dateien behandelt.</span><span class="sxs-lookup"><span data-stu-id="f900b-121">By default, files with certain file extensions or auto-generated file headers are treated as generated code files.</span></span> <span data-ttu-id="f900b-122">Beispielsweise wird ein Dateiname, der mit oder endet, `.designer.cs` `.generated.cs` als generierter Code betrachtet.</span><span class="sxs-lookup"><span data-stu-id="f900b-122">For example, a file name ending with `.designer.cs` or `.generated.cs` is considered generated code.</span></span> <span data-ttu-id="f900b-123">Mit dieser Konfigurationsoption können Sie zusätzliche Benennungs Muster angeben.</span><span class="sxs-lookup"><span data-stu-id="f900b-123">This configuration option lets you specify additional naming patterns.</span></span>

<span data-ttu-id="f900b-124">Fügen Sie z. b. den folgenden Eintrag hinzu, um alle Dateien zu behandeln, deren Name mit `.MyGenerated.cs` dem generierten Code endet:</span><span class="sxs-lookup"><span data-stu-id="f900b-124">For example, to treat all files whose name ends with `.MyGenerated.cs` as generated code, add the following entry:</span></span>

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a><span data-ttu-id="f900b-125">Regel spezifische Optionen</span><span class="sxs-lookup"><span data-stu-id="f900b-125">Rule-specific options</span></span>

<span data-ttu-id="f900b-126">Regel spezifische Optionen können auf eine einzelne Regel, einen Regelsatz oder alle Regeln angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f900b-126">Rule-specific options can be applied to a single rule, a set of rules, or all rules.</span></span> <span data-ttu-id="f900b-127">Zu den Regel spezifischen Optionen gehören:</span><span class="sxs-lookup"><span data-stu-id="f900b-127">The rule-specific options include:</span></span>

- [<span data-ttu-id="f900b-128">Schweregrad der Regel</span><span class="sxs-lookup"><span data-stu-id="f900b-128">Rule severity level</span></span>](#severity-level)
- [<span data-ttu-id="f900b-129">Spezifische Optionen für *Code Qualitäts* Regeln</span><span class="sxs-lookup"><span data-stu-id="f900b-129">Options specific to *code-quality* rules</span></span>](code-quality-rule-options.md)

### <a name="severity-level"></a><span data-ttu-id="f900b-130">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="f900b-130">Severity level</span></span>

<span data-ttu-id="f900b-131">In der folgenden Tabelle werden die verschiedenen Regel Schweregrade angezeigt, die Sie für alle Analyse Regeln konfigurieren können, einschließlich [Codequalität](quality-rules/index.md) und Regeln für den [Code Stil](style-rules/index.md) .</span><span class="sxs-lookup"><span data-stu-id="f900b-131">The following table shows the different rule severities that you can configure for all analyzer rules, including [code quality](quality-rules/index.md) and [code style](style-rules/index.md) rules.</span></span>

| <span data-ttu-id="f900b-132">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="f900b-132">Severity</span></span> | <span data-ttu-id="f900b-133">Verhalten zur Buildzeit</span><span class="sxs-lookup"><span data-stu-id="f900b-133">Build-time behavior</span></span> |
|-|-|
| `error` | <span data-ttu-id="f900b-134">Verstöße werden als *Buildfehler* angezeigt und bewirken, dass Builds fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="f900b-134">Violations appear as build *errors* and cause builds to fail.</span></span>|
| `warning` | <span data-ttu-id="f900b-135">Verstöße werden als *Buildwarnungen* angezeigt, bewirken jedoch nicht, dass Builds fehlschlagen (es sei denn, Sie haben eine Option zum Behandeln von Warnungen als Fehler festgelegt).</span><span class="sxs-lookup"><span data-stu-id="f900b-135">Violations appear as build *warnings* but do not cause builds to fail (unless you have an option set to treat warnings as errors).</span></span> |
| `suggestion` | <span data-ttu-id="f900b-136">Verstöße werden als *Buildmeldungen* und als Vorschläge in der Visual Studio-IDE angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f900b-136">Violations appear as build *messages* and as suggestions in the Visual Studio IDE.</span></span> |
| `silent` | <span data-ttu-id="f900b-137">Verstöße sind für den Benutzer nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f900b-137">Violations aren't visible to the user.</span></span> |
| `none` | <span data-ttu-id="f900b-138">Die Regel wird vollständig unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="f900b-138">Rule is suppressed completely.</span></span> |
| `default` | <span data-ttu-id="f900b-139">Der Standard Schweregrad der Regel wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="f900b-139">The default severity of the rule is used.</span></span> |

> [!TIP]
> <span data-ttu-id="f900b-140">Informationen zur Oberfläche für Regel Schweregrade in Visual Studio finden Sie unter [Schweregrade](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span><span class="sxs-lookup"><span data-stu-id="f900b-140">For information about how rule severities surface in Visual Studio, see [Severity levels](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span></span>

#### <a name="scope"></a><span data-ttu-id="f900b-141">Bereich</span><span class="sxs-lookup"><span data-stu-id="f900b-141">Scope</span></span>

<span data-ttu-id="f900b-142">Verwenden Sie die folgende Syntax, um den Schweregrad der Regel für eine einzelne Regel festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f900b-142">To set the rule severity for a single rule, use the following syntax.</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

<span data-ttu-id="f900b-143">Verwenden Sie die folgende Syntax, um den Standard Schweregrad der Regel für eine Kategorie von Analyse Regeln festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f900b-143">To set the default rule severity for a category of analyzer rules, use the following syntax.</span></span>

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

<span data-ttu-id="f900b-144">Verwenden Sie die folgende Syntax, um den Standard Schweregrad der Regel für alle Analyse Regeln festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f900b-144">To set the default rule severity for all analyzer rules, use the following syntax.</span></span>

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a><span data-ttu-id="f900b-145">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f900b-145">Precedence</span></span>

<span data-ttu-id="f900b-146">Wenn Sie über mehrere Konfigurationseinträge für den Schweregrad verfügen, die auf dieselbe Regel-ID angewendet werden können, wird die Rangfolge in der folgenden Reihenfolge ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="f900b-146">If you have multiple severity configuration entries that can be applied to the same rule ID, precedence is chosen in the following order:</span></span>

- <span data-ttu-id="f900b-147">Ein Eintrag für eine einzelne Regel nach ID hat Vorrang vor einem Eintrag für eine Kategorie.</span><span class="sxs-lookup"><span data-stu-id="f900b-147">An entry for an individual rule by ID takes precedence over an entry for a category.</span></span>
- <span data-ttu-id="f900b-148">Ein Eintrag für eine Kategorie hat Vorrang vor einem Eintrag für alle Analyzer-Regeln.</span><span class="sxs-lookup"><span data-stu-id="f900b-148">An entry for a category takes precedence over an entry for all analyzer rules.</span></span>

<span data-ttu-id="f900b-149">Sehen Sie sich das folgende Beispiel an, in dem [CA1822](/visualstudio/code-quality/ca1822) die Kategorie "Performance" hat:</span><span class="sxs-lookup"><span data-stu-id="f900b-149">Consider the following example, where [CA1822](/visualstudio/code-quality/ca1822) has the category "Performance":</span></span>

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

<span data-ttu-id="f900b-150">Im vorherigen Beispiel sind alle drei Schweregrade auf CA1822 anwendbar.</span><span class="sxs-lookup"><span data-stu-id="f900b-150">In the preceding example, all three severity entries are applicable to CA1822.</span></span> <span data-ttu-id="f900b-151">Bei Verwendung der angegebenen Rang folgen Regeln gewinnt der erste auf der Regel-ID basierende Eintrag jedoch mit den nächsten Einträgen.</span><span class="sxs-lookup"><span data-stu-id="f900b-151">However, using the specified precedence rules, the first rule ID-based entry wins over the next entries.</span></span> <span data-ttu-id="f900b-152">In diesem Beispiel hat CA1822 den effektiven Schweregrad `error` .</span><span class="sxs-lookup"><span data-stu-id="f900b-152">In this example, CA1822 will have an effective severity of `error`.</span></span> <span data-ttu-id="f900b-153">Alle anderen Regeln in der Kategorie "Leistung" haben den Schweregrad `warning` .</span><span class="sxs-lookup"><span data-stu-id="f900b-153">All other rules within the "Performance" category will have a severity of `warning`.</span></span>

<span data-ttu-id="f900b-154">Informationen zur Entscheidung, wie die Rangfolge der Datei Vorrang hat, finden Sie im Abschnitt "Rang folgen" im [Artikel "Konfigurationsdateien](configuration-files.md#precedence)".</span><span class="sxs-lookup"><span data-stu-id="f900b-154">For information about how inter-file precedence is decided, see the [Precedence section of the Configuration files article](configuration-files.md#precedence).</span></span>
