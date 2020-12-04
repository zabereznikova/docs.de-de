---
title: Vordefinierte Konfigurationsdateien (Code Analyse)
description: Erfahren Sie, wie Sie vordefinierte Editor config-und Regel Satz Dateien verwenden können, um bestimmte Arten der Code Analyse zu verwenden.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "96591665"
---
# <a name="predefined-configuration-files"></a><span data-ttu-id="79e3e-103">Vordefinierte Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="79e3e-103">Predefined configuration files</span></span>

<span data-ttu-id="79e3e-104">Vordefinierte Editor config-und [Regel Satz](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) Dateien sind verfügbar, die es Ihnen ermöglichen, eine Kategorie von Code Qualitätsregeln, wie z. b. Sicherheits-oder Entwurfs Regeln, schnell und einfach zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="79e3e-104">Predefined EditorConfig and [rule set](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) files are available that make it quick and easy to enable a category of code quality rules, such as security or design rules.</span></span> <span data-ttu-id="79e3e-105">Indem Sie eine bestimmte Kategorie von Regeln aktivieren, können Sie gezielte Probleme und bestimmte Bedingungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="79e3e-105">By enabling a specific category of rules, you can identify targeted issues and specific conditions.</span></span> <span data-ttu-id="79e3e-106">Um auf diese vordefinierten Dateien zuzugreifen, installieren Sie das nuget Analyzer-Paket [Microsoft. Code Analysis. netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) .</span><span class="sxs-lookup"><span data-stu-id="79e3e-106">To access these predefined files, install the [Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer package.</span></span>

<span data-ttu-id="79e3e-107">[Microsoft. Code Analysis. netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) enthält vordefinierte Editor config-Dateien und Regelsätze für die folgenden Regel Kategorien:</span><span class="sxs-lookup"><span data-stu-id="79e3e-107">[Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) includes predefined EditorConfig files and rule sets for the following rule categories:</span></span>

- <span data-ttu-id="79e3e-108">Alle Regeln</span><span class="sxs-lookup"><span data-stu-id="79e3e-108">All rules</span></span>
- <span data-ttu-id="79e3e-109">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="79e3e-109">Dataflow</span></span>
- <span data-ttu-id="79e3e-110">Entwurf</span><span class="sxs-lookup"><span data-stu-id="79e3e-110">Design</span></span>
- <span data-ttu-id="79e3e-111">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="79e3e-111">Documentation</span></span>
- <span data-ttu-id="79e3e-112">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="79e3e-112">Globalization</span></span>
- <span data-ttu-id="79e3e-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="79e3e-113">Interoperability</span></span>
- <span data-ttu-id="79e3e-114">Wartbarkeit</span><span class="sxs-lookup"><span data-stu-id="79e3e-114">Maintainability</span></span>
- <span data-ttu-id="79e3e-115">Benennung</span><span class="sxs-lookup"><span data-stu-id="79e3e-115">Naming</span></span>
- <span data-ttu-id="79e3e-116">Leistung</span><span class="sxs-lookup"><span data-stu-id="79e3e-116">Performance</span></span>
- <span data-ttu-id="79e3e-117">Portiert von FxCop</span><span class="sxs-lookup"><span data-stu-id="79e3e-117">Ported from FxCop</span></span>
- <span data-ttu-id="79e3e-118">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="79e3e-118">Reliability</span></span>
- <span data-ttu-id="79e3e-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="79e3e-119">Security</span></span>
- <span data-ttu-id="79e3e-120">Verbrauch</span><span class="sxs-lookup"><span data-stu-id="79e3e-120">Usage</span></span>

<span data-ttu-id="79e3e-121">Jede dieser Kategorien von Regeln verfügt über eine Editor config-oder Regel Satz Datei für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79e3e-121">Each of those categories of rules has an EditorConfig or rule set file to:</span></span>

- <span data-ttu-id="79e3e-122">Alle Regeln in der Kategorie aktivieren (und alle anderen Regeln deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="79e3e-122">Enable all the rules in the category (and disable all other rules)</span></span>
- <span data-ttu-id="79e3e-123">Standard Schweregrad der Regel verwenden und standardmäßig aktiviert (und alle anderen Regeln deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="79e3e-123">Use each rule's default severity and enabled by default setting (and disable all other rules)</span></span>

> [!TIP]
> <span data-ttu-id="79e3e-124">Die Kategorie "alle Regeln" verfügt über eine zusätzliche Editor config-oder Regel Satz Datei, um alle Regeln zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="79e3e-124">The "all rules" category has an additional EditorConfig or rule set file to disable all rules.</span></span> <span data-ttu-id="79e3e-125">Verwenden Sie diese Datei, um alle Analyse Warnungen oder-Fehler in einem Projekt schnell zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="79e3e-125">Use this file to quickly get rid of any analyzer warnings or errors in a project.</span></span>

## <a name="predefined-editorconfig-files"></a><span data-ttu-id="79e3e-126">Vordefinierte Editor config-Dateien</span><span class="sxs-lookup"><span data-stu-id="79e3e-126">Predefined EditorConfig files</span></span>

<span data-ttu-id="79e3e-127">Die vordefinierten Editor config-Dateien für das Microsoft. Code Analysis. netanalyzers Analyzer-Paket befinden sich im Unterverzeichnis " *Editor config* ", in dem das nuget-Paket installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="79e3e-127">The predefined EditorConfig files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *editorconfig* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="79e3e-128">Beispielsweise befindet sich die Editor config-Datei, um alle Sicherheitsregeln zu aktivieren, unter *Editor config/securityrulesenabled/. Editor config*.</span><span class="sxs-lookup"><span data-stu-id="79e3e-128">For example, the EditorConfig file to enable all security rules is located at *editorconfig/SecurityRulesEnabled/.editorconfig*.</span></span>

<span data-ttu-id="79e3e-129">Kopieren Sie die ausgewählte *Editor config* -Datei in das Stammverzeichnis Ihres Projekts.</span><span class="sxs-lookup"><span data-stu-id="79e3e-129">Copy the chosen *.editorconfig* file to your project's root directory.</span></span>

## <a name="predefined-rule-sets"></a><span data-ttu-id="79e3e-130">Vordefinierter Regelsatz</span><span class="sxs-lookup"><span data-stu-id="79e3e-130">Predefined rule sets</span></span>

<span data-ttu-id="79e3e-131">Die vordefinierten Regel Satz Dateien für das Microsoft. Code Analysis. netanalyzers Analyzer-Paket befinden sich im Unterverzeichnis *RuleSets* von, in dem das nuget-Paket installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="79e3e-131">The predefined rule set files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *rulesets* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="79e3e-132">Beispielsweise befindet sich die Regel Satz Datei, um alle Sicherheitsregeln zu aktivieren, unter *RuleSets/securityrulesenabled. RuleSet*.</span><span class="sxs-lookup"><span data-stu-id="79e3e-132">For example, the rule set file to enable all security rules is located at *rulesets/SecurityRulesEnabled.ruleset*.</span></span> <span data-ttu-id="79e3e-133">Kopieren Sie mindestens einen Regelsatz, und fügen Sie ihn in das Verzeichnis ein, in dem sich das Projekt befindet.</span><span class="sxs-lookup"><span data-stu-id="79e3e-133">Copy one or more of the rule sets and paste them in the directory that contains your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="79e3e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e3e-134">See also</span></span>

- [<span data-ttu-id="79e3e-135">Analysetoolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="79e3e-135">Analyzer configuration</span></span>](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [<span data-ttu-id="79e3e-136">Optionen für die .net-Codestil-Regel für Editor config</span><span class="sxs-lookup"><span data-stu-id="79e3e-136">.NET code style rule options for EditorConfig</span></span>](code-style-rule-options.md)
