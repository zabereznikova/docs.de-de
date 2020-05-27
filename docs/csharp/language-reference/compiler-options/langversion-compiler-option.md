---
title: -langversion (C#-Compileroptionen)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802957"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="5c29c-102">-langversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="5c29c-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="5c29c-103">Führt dazu, dass der Compiler nur Syntax akzeptiert, die in der ausgewählten C#-Sprachspezifikation enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5c29c-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c29c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c29c-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="5c29c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5c29c-105">Arguments</span></span>

`option`

<span data-ttu-id="5c29c-106">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="5c29c-106">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="5c29c-107">Die Standardsprachversion ist vom Zielframework für Ihre Anwendung und der installierten Version des SDK oder von Visual Studio abhängig.</span><span class="sxs-lookup"><span data-stu-id="5c29c-107">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="5c29c-108">Diese Regeln werden im Artikel zum [Konfigurieren der Sprachversion](../configure-language-version.md#defaults) definiert.</span><span class="sxs-lookup"><span data-stu-id="5c29c-108">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c29c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c29c-109">Remarks</span></span>

<span data-ttu-id="5c29c-110">Metadaten, auf die von Ihrer C#-Anwendung verwiesen wird, unterliegen nicht der Compileroption **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="5c29c-110">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="5c29c-111">Da jede Version des C#-Compilers Erweiterungen der Sprachspezifikation enthält, bietet **-langversion** Ihnen nicht die gleiche Funktionalität wie die einer früheren Compilerversion.</span><span class="sxs-lookup"><span data-stu-id="5c29c-111">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="5c29c-112">Darüber hinaus sind die neue Syntax und die neuen Features nicht unbedingt an die spezifische Version des Frameworks gebunden, während C#-Versionsupdates für gewöhnlich mit den Releases von .NET Framework einhergehen.</span><span class="sxs-lookup"><span data-stu-id="5c29c-112">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="5c29c-113">Während die neuen Features ein Compilerupdate erfordern, das mit der C#-Revision veröffentlicht wird, hat jedes Feature seine eigene mindestens erforderliche .NET-API- oder CLR-Anforderungen, durch die es auf abwärtskompatiblen Frameworks ausgeführt werden kann, indem NuGet-Pakete oder andere Bibliotheken einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5c29c-113">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="5c29c-114">Unabhängig von der verwendeten **-langversion**-Einstellung verwenden Sie die aktuelle Version der CLR, um Ihre EXE- oder DLL-Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c29c-114">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="5c29c-115">Davon ausgenommen sind Friend-Assemblys und [-moduleassemblyname (C#-Compileroption)](./moduleassemblyname-compiler-option.md), die unter **-langversion:ISO-1** laufen.</span><span class="sxs-lookup"><span data-stu-id="5c29c-115">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="5c29c-116">Weitere Möglichkeiten zum Angeben der C#-Sprachversion finden Sie im Artikel zum [Auswählen der C#-Sprachversion](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="5c29c-116">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="5c29c-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c29c-117">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5c29c-118">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5c29c-118">C# language specification</span></span>

| <span data-ttu-id="5c29c-119">Version</span><span class="sxs-lookup"><span data-stu-id="5c29c-119">Version</span></span>          | <span data-ttu-id="5c29c-120">Link</span><span class="sxs-lookup"><span data-stu-id="5c29c-120">Link</span></span>                       | <span data-ttu-id="5c29c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c29c-121">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="5c29c-122">C# 7.0 und höher</span><span class="sxs-lookup"><span data-stu-id="5c29c-122">C# 7.0 and later</span></span> |                            | <span data-ttu-id="5c29c-123">Derzeit nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="5c29c-123">Not currently available</span></span>                                                 |
| <span data-ttu-id="5c29c-124">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-124">C# 6.0</span></span>           | <span data-ttu-id="5c29c-125">[Link][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="5c29c-125">[Link][csharp-6]</span></span>           | <span data-ttu-id="5c29c-126">C#-Spezifikation Version 6, inoffizieller Entwurf: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="5c29c-126">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="5c29c-127">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-127">C# 5.0</span></span>           | <span data-ttu-id="5c29c-128">[PDF herunterladen][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="5c29c-128">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="5c29c-129">Standard ECMA-334, 5. Edition</span><span class="sxs-lookup"><span data-stu-id="5c29c-129">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="5c29c-130">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-130">C# 3.0</span></span>           | <span data-ttu-id="5c29c-131">[DOC herunterladen][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="5c29c-131">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="5c29c-132">C#-Programmiersprachenspezifikation Version 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5c29c-132">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="5c29c-133">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-133">C# 2.0</span></span>           | <span data-ttu-id="5c29c-134">[PDF herunterladen][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="5c29c-134">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="5c29c-135">Standard ECMA-334, 4. Edition</span><span class="sxs-lookup"><span data-stu-id="5c29c-135">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="5c29c-136">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="5c29c-136">C# 1.2</span></span>           | <span data-ttu-id="5c29c-137">[DOC herunterladen][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="5c29c-137">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="5c29c-138">C#-Programmiersprachenspezifikation Version 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5c29c-138">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="5c29c-139">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-139">C# 1.0</span></span>           | <span data-ttu-id="5c29c-140">[DOC herunterladen][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="5c29c-140">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="5c29c-141">C#-Programmiersprachenspezifikation Version 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5c29c-141">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="5c29c-142">Mindestens erforderliche SDK-Version, die erforderlich ist, um alle Sprachfeatures zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="5c29c-142">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="5c29c-143">In der folgenden Tabelle sind die Mindestversionen des SDK mit dem C#-Compiler aufgeführt, der die entsprechende Sprachversion unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5c29c-143">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="5c29c-144">C#-Version</span><span class="sxs-lookup"><span data-stu-id="5c29c-144">C# version</span></span> | <span data-ttu-id="5c29c-145">Mindestversion des SDK</span><span class="sxs-lookup"><span data-stu-id="5c29c-145">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="5c29c-146">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-146">C# 8.0</span></span>     | <span data-ttu-id="5c29c-147">Microsoft Visual Studio/Build Tools 2019, Version 16.3, oder .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="5c29c-147">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="5c29c-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="5c29c-148">C# 7.3</span></span>     | <span data-ttu-id="5c29c-149">Microsoft Visual Studio/Build Tools 2017, Version 15.7</span><span class="sxs-lookup"><span data-stu-id="5c29c-149">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="5c29c-150">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="5c29c-150">C# 7.2</span></span>     | <span data-ttu-id="5c29c-151">Microsoft Visual Studio/Build Tools 2017, Version 15.5</span><span class="sxs-lookup"><span data-stu-id="5c29c-151">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="5c29c-152">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="5c29c-152">C# 7.1</span></span>     | <span data-ttu-id="5c29c-153">Microsoft Visual Studio/Build Tools 2017, Version 15.3</span><span class="sxs-lookup"><span data-stu-id="5c29c-153">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="5c29c-154">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="5c29c-154">C# 7.0</span></span>     | <span data-ttu-id="5c29c-155">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="5c29c-155">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="5c29c-156">C# 6</span><span class="sxs-lookup"><span data-stu-id="5c29c-156">C# 6</span></span>       | <span data-ttu-id="5c29c-157">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="5c29c-157">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="5c29c-158">C# 5</span><span class="sxs-lookup"><span data-stu-id="5c29c-158">C# 5</span></span>       | <span data-ttu-id="5c29c-159">Microsoft Visual Studio/Build Tools 2012 oder gebündelter .NET Framework 4.5-Compiler</span><span class="sxs-lookup"><span data-stu-id="5c29c-159">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="5c29c-160">C# 4</span><span class="sxs-lookup"><span data-stu-id="5c29c-160">C# 4</span></span>       | <span data-ttu-id="5c29c-161">Microsoft Visual Studio/Build Tools 2010 oder gebündelter .NET Framework 4.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="5c29c-161">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="5c29c-162">C# 3</span><span class="sxs-lookup"><span data-stu-id="5c29c-162">C# 3</span></span>       | <span data-ttu-id="5c29c-163">Microsoft Visual Studio/Build Tools 2008 oder gebündelter .NET Framework 3.5-Compiler</span><span class="sxs-lookup"><span data-stu-id="5c29c-163">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="5c29c-164">C# 2</span><span class="sxs-lookup"><span data-stu-id="5c29c-164">C# 2</span></span>       | <span data-ttu-id="5c29c-165">Microsoft Visual Studio/Build Tools 2005 oder gebündelter .NET Framework 2.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="5c29c-165">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="5c29c-166">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="5c29c-166">C# 1.0/1.2</span></span> | <span data-ttu-id="5c29c-167">Microsoft Visual Studio/Build Tools .NET 2002 oder gebündelter .NET Framework 1.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="5c29c-167">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="5c29c-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c29c-168">See also</span></span>

- [<span data-ttu-id="5c29c-169">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="5c29c-169">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="5c29c-170">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="5c29c-170">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
