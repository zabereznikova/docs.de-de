---
title: Neues in C# 7.1
description: Eine Übersicht der neuen Features in C# 7.1
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="cec2f-103">Neues in C# 7.1</span><span class="sxs-lookup"><span data-stu-id="cec2f-103">What's new in C# 7.1</span></span>

<span data-ttu-id="cec2f-104">C# 7.1 ist die erste Punktversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="cec2f-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="cec2f-105">Das bedeutet schnellere Releaserhythmen für die Sprache.</span><span class="sxs-lookup"><span data-stu-id="cec2f-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="cec2f-106">Sie können die neuen Features früher benutzen, im Idealfall sobald ein neues Feature bereit ist.</span><span class="sxs-lookup"><span data-stu-id="cec2f-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="cec2f-107">Mit C# 7.1 wird die Fähigkeit hinzugefügt, den Compiler so zu konfigurieren, dass er einer bestimmten Version der Sprache entspricht.</span><span class="sxs-lookup"><span data-stu-id="cec2f-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="cec2f-108">Damit können Sie die Entscheidung, Tools upzugraden, von der Entscheidung unterscheiden, Upgrades für Sprachversionen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cec2f-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="cec2f-109">Mit C# 7.1 wird ein Konfigurationselement zum [Auswählen der Sprachversion](#language-version-selection), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cec2f-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="cec2f-110">Die neuen Sprachfeatures in diesem Release umfassen:</span><span class="sxs-lookup"><span data-stu-id="cec2f-110">The new language features in this release are:</span></span>

* <span data-ttu-id="cec2f-111">Die [`async``Main`-Methode](#async-main)</span><span class="sxs-lookup"><span data-stu-id="cec2f-111">[`async` `Main` method](#async-main)</span></span>
  - <span data-ttu-id="cec2f-112">Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.</span><span class="sxs-lookup"><span data-stu-id="cec2f-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="cec2f-113">`default`Literale Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="cec2f-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="cec2f-114">Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cec2f-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="cec2f-115">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="cec2f-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="cec2f-116">Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cec2f-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="cec2f-117">Außerdem verfügt der Compiler über die zwei Optionen `/refout` und `/refonly`, mit denen die [Generierung der Referenzassembly](#reference-assembly-generation) gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="cec2f-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="cec2f-118">Auswählen der Sprachversion</span><span class="sxs-lookup"><span data-stu-id="cec2f-118">Language version selection</span></span>

<span data-ttu-id="cec2f-119">Der C#-Compiler unterstützt C# 7.1 ab Visual Studio 2017 Version 15.3 bzw. .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="cec2f-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="cec2f-120">Allerdings sind die Features von C# 7.1 standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cec2f-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="cec2f-121">Sie müssen die Einstellung der Sprachversion Ihres Projekts ändern, um diese Features zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cec2f-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="cec2f-122">Klicken Sie in Visual Studio mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cec2f-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="cec2f-123">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="cec2f-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="cec2f-124">Wählen Sie, wie in der folgenden Abbildung gezeigt wird, in der Dropdownliste **C# latest minor version (latest)** (Neueste C#-Nebenversion (latest)) oder die bestimmte Version **C# 7.1** aus.</span><span class="sxs-lookup"><span data-stu-id="cec2f-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="cec2f-125">Der Wert `latest` bedeutet, dass Sie die neueste Nebenversion auf dem aktuellen Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="cec2f-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="cec2f-126">`C# 7.1` bedeutet, dass Sie C# 7.1 verwenden, auch nachdem neuere Nebenversionen veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="cec2f-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Festlegen der Sprachversion](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="cec2f-128">Alternativ können Sie die CSPROJ-Datei bearbeiten und die folgenden Zeilen hinzufügen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cec2f-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="cec2f-129">Wenn Sie die Visual Studio-IDE verwenden, um Ihre CSPROJ-Dateien zu aktualisieren, werden separate Knoten für jede Buildkonfiguration von der IDE erstellt.</span><span class="sxs-lookup"><span data-stu-id="cec2f-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="cec2f-130">In der Regel legen Sie den gleichen Wert in allen Buildkonfigurationen fest, dennoch müssen Sie ihn für jede Buildkonfiguration explizit festlegen oder beim Ändern dieser Einstellung „Alle Konfigurationen“ auswählen.</span><span class="sxs-lookup"><span data-stu-id="cec2f-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="cec2f-131">Folgendes wird dann in Ihrer CSPROJ-Datei angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cec2f-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="cec2f-132">Folgende Einstellungen sind für das `LangVersion`-Element gültig:</span><span class="sxs-lookup"><span data-stu-id="cec2f-132">Valid settings for the `LangVersion` element are:</span></span>

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

<span data-ttu-id="cec2f-133">Die Auflösung der speziellen Zeichenfolgen `default` und `latest` sind die Haupt- und Nebensprachversionen, die jeweils auf dem Buildcomputer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="cec2f-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="cec2f-134">Mit dieser Einstellung wird das Installieren neuer Versionen des SDK und der Tools in Ihrer Entwicklungsumgebung vom Auswählen neuer Sprachfeatures für ein Projekt entkoppelt.</span><span class="sxs-lookup"><span data-stu-id="cec2f-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="cec2f-135">Sie können das neueste SDK und die neuesten Tools auf Ihrem Buildcomputer installieren.</span><span class="sxs-lookup"><span data-stu-id="cec2f-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="cec2f-136">Jedes Projekt kann dazu konfiguriert werden, eine spezifische Version der Sprache für das Build zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cec2f-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="cec2f-137">Async Main</span><span class="sxs-lookup"><span data-stu-id="cec2f-137">Async main</span></span>

<span data-ttu-id="cec2f-138">Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="cec2f-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="cec2f-139">Vorher hätten Sie das Folgende schreiben müssen:</span><span class="sxs-lookup"><span data-stu-id="cec2f-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="cec2f-140">Nun können Sie das Folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="cec2f-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="cec2f-141">Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="cec2f-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="cec2f-142">Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="cec2f-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="cec2f-143">Literale Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="cec2f-143">Default literal expressions</span></span>

<span data-ttu-id="cec2f-144">Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cec2f-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="cec2f-145">Diese Ausdrücke initialisieren eine Variable auf dem Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cec2f-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="cec2f-146">Dort, wo Sie vorher das Folgende geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="cec2f-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="cec2f-147">Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.</span><span class="sxs-lookup"><span data-stu-id="cec2f-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="cec2f-148">Weitere Informationen zu dieser Erweiterung finden Sie unter [default value expressions (Standardwertausdrücke)](../programming-guide/statements-expressions-operators/default-value-expressions.md) im C#-Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="cec2f-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="cec2f-149">Diese Erweiterung ändert auch einige Regeln der Analyse für das [Schlüsselwort „default“](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="cec2f-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="cec2f-150">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="cec2f-150">Inferred tuple element names</span></span>

<span data-ttu-id="cec2f-151">Dieses Feature ist eine kleine Erweiterung des Tupelfeatures, das in C# 7.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cec2f-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="cec2f-152">Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten.</span><span class="sxs-lookup"><span data-stu-id="cec2f-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="cec2f-153">Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel in C# 7.1 verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cec2f-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="cec2f-154">Weitere Informationen über dieses Feature finden Sie im Artikel [Tupel](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="cec2f-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="cec2f-155">Generierung der Referenzassembly</span><span class="sxs-lookup"><span data-stu-id="cec2f-155">Reference assembly generation</span></span>

<span data-ttu-id="cec2f-156">Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [/refout](../language-reference/compiler-options/refout-compiler-option.md) und [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="cec2f-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="cec2f-157">In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cec2f-157">The linked topics explain these options and reference assemblies in more detail.</span></span>
