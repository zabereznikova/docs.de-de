---
title: Was ist neu in c# 7.1
description: "Eine Übersicht über neue Funktionen in c# 7.1."
keywords: C#-Sprachentwurf, 7.1, Visual Studio-2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="8f025-104">Was ist neu in c# 7.1</span><span class="sxs-lookup"><span data-stu-id="8f025-104">What's new in C# 7.1</span></span>

<span data-ttu-id="8f025-105">C#-7.1 ist der erste Punkt Version der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="8f025-105">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="8f025-106">Eine erhöhte-versionsrhythmus für die Sprache werden markiert.</span><span class="sxs-lookup"><span data-stu-id="8f025-106">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="8f025-107">Sie können die neuen Funktionen früher, im Idealfall verwenden, wenn jeder neuen Funktion bereit ist.</span><span class="sxs-lookup"><span data-stu-id="8f025-107">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="8f025-108">C#-7.1 fügt die Möglichkeit, den Compiler entsprechend eine angegebene Version der Sprache zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8f025-108">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="8f025-109">Mit der Sie die Entscheidung zum Aktualisieren von Tools von der Entscheidung für eine Aktualisierung von Sprachversionen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="8f025-109">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="8f025-110">C#-7.1 fügt die [Version Sprachauswahl](#language-version-selection) Konfigurationselement, drei neue Sprachfunktionen zu nutzen und neue Compilerverhalten.</span><span class="sxs-lookup"><span data-stu-id="8f025-110">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="8f025-111">Die neuen Sprachfeatures in diesem Release umfassen:</span><span class="sxs-lookup"><span data-stu-id="8f025-111">The new language features in this release are:</span></span>

* [<span data-ttu-id="8f025-112">`async``Main` Methode</span><span class="sxs-lookup"><span data-stu-id="8f025-112">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="8f025-113">Der `async` -Modifizierer kann am Einstiegspunkt einer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f025-113">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="8f025-114">`default`Literale Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8f025-114">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="8f025-115">Sie können Literale Standardausdrücken in Default-Wert-Ausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f025-115">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="8f025-116">Abgeleitete Tupel Elementnamen</span><span class="sxs-lookup"><span data-stu-id="8f025-116">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="8f025-117">Tupel Initialisierung in vielen Fällen können die Namen der Tupelelemente abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8f025-117">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="8f025-118">Schließlich der Compiler verfügt über zwei Optionen `/refout` und `/refonly` das entsprechende Steuerelement [Generieren der Assembly verweisen](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="8f025-118">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="8f025-119">Sprachauswahl-version</span><span class="sxs-lookup"><span data-stu-id="8f025-119">Language version selection</span></span>

<span data-ttu-id="8f025-120">Der C#-Compiler unterstützt c# 7.1 beginnend mit Visual Studio 2017 Version 15.3 oder .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="8f025-120">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="8f025-121">Allerdings sind die 7.1 Funktionen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f025-121">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="8f025-122">Um die 7.1-Funktionen zu aktivieren, müssen Sie die Spracheinstellung für die Version für das Projekt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8f025-122">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="8f025-123">Klicken Sie in Visual Studio mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8f025-123">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="8f025-124">Wählen Sie die **erstellen** Registerkarte, und wählen Sie die **erweitert** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="8f025-124">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="8f025-125">Wählen Sie in der Dropdownliste **c# neueste Nebenversion (aktuellste Version)**, oder eine bestimmte Version **c# 7.1** wie im folgenden Bild gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f025-125">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="8f025-126">Die `latest` Wert bedeutet, dass Sie die aktuelle Nebenversion auf dem aktuellen Computer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8f025-126">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="8f025-127">Die `C# 7.1` bedeutet, dass die gewünschten c# 7.1 verwenden, auch nachdem die neuere Nebenversionen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f025-127">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Die Sprachversion festlegen](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="8f025-129">Sie können alternativ bearbeiten Sie die Datei "Csproj" und hinzufügen oder ändern die folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="8f025-129">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="8f025-130">Wenn Sie Visual Studio-IDE verwenden, um die Csproj-Dateien aktualisiert werden, erstellt die IDE separate Knoten für jede Buildkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8f025-130">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="8f025-131">In der Regel legen Sie dem Wert der gleiche in alle Buildkonfigurationen, jedoch müssen Sie explizit für jede Buildkonfiguration festgelegt, oder wählen Sie "Alle Konfigurationen" aus, wenn Sie diese Einstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8f025-131">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="8f025-132">Im folgenden sehen Sie in der Csproj-Datei:</span><span class="sxs-lookup"><span data-stu-id="8f025-132">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="8f025-133">Gültige Einstellungen für die `LangVersion` -Element sind:</span><span class="sxs-lookup"><span data-stu-id="8f025-133">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="8f025-134">Die speziellen Zeichenfolgen `default` und `latest` auf die neueste Haupt- und Nebenversionsnummern Sprachversionen auf dem Buildcomputer installiert wurde, bzw. beheben.</span><span class="sxs-lookup"><span data-stu-id="8f025-134">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="8f025-135">Diese Einstellung entkoppelt, installieren neue Versionen des SDK und Tools in der Entwicklungsumgebung von auswählen, um neue Sprachfeatures in einem Projekt einzubinden.</span><span class="sxs-lookup"><span data-stu-id="8f025-135">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="8f025-136">Sie können das neueste SDK und Tools auf dem Buildcomputer installieren.</span><span class="sxs-lookup"><span data-stu-id="8f025-136">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="8f025-137">Jedes Projekt kann konfiguriert werden, um eine bestimmte Version der Sprache für ihre Build verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f025-137">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="8f025-138">Async-Hauptfenster</span><span class="sxs-lookup"><span data-stu-id="8f025-138">Async main</span></span>

<span data-ttu-id="8f025-139">Ein *Async main* Methode ermöglicht Ihnen die Verwendung `await` in Ihrer `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="8f025-139">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="8f025-140">Bisher mussten Sie zum Schreiben:</span><span class="sxs-lookup"><span data-stu-id="8f025-140">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="8f025-141">Sie können jetzt Folgendes schreiben:</span><span class="sxs-lookup"><span data-stu-id="8f025-141">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="8f025-142">Wenn das Programm einen Exitcode zurückgegeben wird, können Sie deklarieren eine `Main` Methode, die zurückgibt eine <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="8f025-142">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="8f025-143">Erfahren Sie mehr über die Details in der [Async main](../programming-guide/main-and-command-args/index.md) Thema des Handbuchs Programmierung.</span><span class="sxs-lookup"><span data-stu-id="8f025-143">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="8f025-144">Literale Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="8f025-144">Default literal expressions</span></span>

<span data-ttu-id="8f025-145">Standard-Literale Ausdrücke sind eine Erweiterung Default-Wert-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="8f025-145">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="8f025-146">Diese Ausdrücke initialisiert werden, eine Variable auf den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="8f025-146">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="8f025-147">Sie würden, in dem zuvor schreiben:</span><span class="sxs-lookup"><span data-stu-id="8f025-147">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="8f025-148">Sie können jetzt den Typ auf der rechten Seite der Initialisierung weglassen:</span><span class="sxs-lookup"><span data-stu-id="8f025-148">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="8f025-149">Sie können erfahren Sie mehr über diese Erweiterung in der C#-Programmierhandbuch Thema auf [Standard Wertausdrücke](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8f025-149">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="8f025-150">Diese Erweiterung ändert sich auch einige der Regeln für die Analyse der [default-Schlüsselwort](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="8f025-150">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="8f025-151">Abgeleitete Tupel Elementnamen</span><span class="sxs-lookup"><span data-stu-id="8f025-151">Inferred tuple element names</span></span>

<span data-ttu-id="8f025-152">Diese Funktion ist eine kleine Erweiterung der Tupel-Funktion in c# 7.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f025-152">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="8f025-153">Oft bei der Initialisierung eines Tupels sind Variablen, die für die rechte Seite der Zuweisung verwendet identisch mit den Namen, die Sie für die Tupelelemente würde wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8f025-153">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="8f025-154">Die Variablen verwendet, um das Tupel in c# 7.1 initialisieren können die Namen der Tupelelemente abgeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="8f025-154">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="8f025-155">Weitere Informationen finden Sie Informationen zu dieser Funktion in der [Tupel](../tuples.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="8f025-155">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="8f025-156">Generieren der Assembly Verweis</span><span class="sxs-lookup"><span data-stu-id="8f025-156">Reference assembly generation</span></span>

<span data-ttu-id="8f025-157">Es gibt zwei neue Compileroptionen, die generieren *Verweis reine Assemblys*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) und [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8f025-157">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="8f025-158">In den verknüpften Themen werden diese Optionen und die Verweisassemblys ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="8f025-158">The linked topics explain these options and reference assemblies in more detail.</span></span>
