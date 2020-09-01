---
description: -langversion (C#-Compileroptionen)
title: -langversion (C#-Compileroptionen)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: b0e966bcc87303c0a7c2199fbfac743b22481424
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125474"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="77869-103">-langversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="77869-103">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="77869-104">Führt dazu, dass der Compiler nur Syntax akzeptiert, die in der ausgewählten C#-Sprachspezifikation enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="77869-104">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="77869-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="77869-105">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="77869-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="77869-106">Arguments</span></span>

`option`

<span data-ttu-id="77869-107">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="77869-107">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="77869-108">Die Standardsprachversion ist vom Zielframework für Ihre Anwendung und der installierten Version des SDK oder von Visual Studio abhängig.</span><span class="sxs-lookup"><span data-stu-id="77869-108">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="77869-109">Diese Regeln werden im Artikel zum [Konfigurieren der Sprachversion](../configure-language-version.md#defaults) definiert.</span><span class="sxs-lookup"><span data-stu-id="77869-109">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="77869-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77869-110">Remarks</span></span>

<span data-ttu-id="77869-111">Metadaten, auf die von Ihrer C#-Anwendung verwiesen wird, unterliegen nicht der Compileroption **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="77869-111">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="77869-112">Da jede Version des C#-Compilers Erweiterungen der Sprachspezifikation enthält, bietet **-langversion** Ihnen nicht die gleiche Funktionalität wie die einer früheren Compilerversion.</span><span class="sxs-lookup"><span data-stu-id="77869-112">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="77869-113">Darüber hinaus sind die neue Syntax und die neuen Features nicht unbedingt an die spezifische Version des Frameworks gebunden, während C#-Versionsupdates für gewöhnlich mit den Releases von .NET Framework einhergehen.</span><span class="sxs-lookup"><span data-stu-id="77869-113">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="77869-114">Während die neuen Features ein Compilerupdate erfordern, das mit der C#-Revision veröffentlicht wird, hat jedes Feature seine eigene mindestens erforderliche .NET-API- oder CLR-Anforderungen, durch die es auf abwärtskompatiblen Frameworks ausgeführt werden kann, indem NuGet-Pakete oder andere Bibliotheken einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="77869-114">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="77869-115">Unabhängig von der verwendeten **-langversion**-Einstellung verwenden Sie die aktuelle Version der CLR, um Ihre EXE- oder DLL-Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77869-115">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="77869-116">Davon ausgenommen sind Friend-Assemblys und [-moduleassemblyname (C#-Compileroption)](./moduleassemblyname-compiler-option.md), die unter **-langversion:ISO-1** laufen.</span><span class="sxs-lookup"><span data-stu-id="77869-116">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="77869-117">Weitere Möglichkeiten zum Angeben der C#-Sprachversion finden Sie im Artikel zum [Auswählen der C#-Sprachversion](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="77869-117">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="77869-118">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="77869-118">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="77869-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="77869-119">C# language specification</span></span>

| <span data-ttu-id="77869-120">Version</span><span class="sxs-lookup"><span data-stu-id="77869-120">Version</span></span>          | <span data-ttu-id="77869-121">Link</span><span class="sxs-lookup"><span data-stu-id="77869-121">Link</span></span>                       | <span data-ttu-id="77869-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77869-122">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="77869-123">C# 7.0 und höher</span><span class="sxs-lookup"><span data-stu-id="77869-123">C# 7.0 and later</span></span> |                            | <span data-ttu-id="77869-124">Derzeit nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="77869-124">Not currently available</span></span>                                                 |
| <span data-ttu-id="77869-125">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="77869-125">C# 6.0</span></span>           | <span data-ttu-id="77869-126">[Link][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="77869-126">[Link][csharp-6]</span></span>           | <span data-ttu-id="77869-127">C#-Spezifikation Version 6, inoffizieller Entwurf: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="77869-127">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="77869-128">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="77869-128">C# 5.0</span></span>           | <span data-ttu-id="77869-129">[PDF herunterladen][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="77869-129">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="77869-130">Standard ECMA-334, 5. Edition</span><span class="sxs-lookup"><span data-stu-id="77869-130">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="77869-131">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="77869-131">C# 3.0</span></span>           | <span data-ttu-id="77869-132">[DOC herunterladen][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="77869-132">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="77869-133">C#-Programmiersprachenspezifikation Version 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="77869-133">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="77869-134">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="77869-134">C# 2.0</span></span>           | <span data-ttu-id="77869-135">[PDF herunterladen][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="77869-135">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="77869-136">Standard ECMA-334, 4. Edition</span><span class="sxs-lookup"><span data-stu-id="77869-136">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="77869-137">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="77869-137">C# 1.2</span></span>           | <span data-ttu-id="77869-138">[DOC herunterladen][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="77869-138">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="77869-139">C#-Programmiersprachenspezifikation Version 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="77869-139">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="77869-140">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="77869-140">C# 1.0</span></span>           | <span data-ttu-id="77869-141">[DOC herunterladen][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="77869-141">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="77869-142">C#-Programmiersprachenspezifikation Version 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="77869-142">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="77869-143">Mindestens erforderliche SDK-Version, die erforderlich ist, um alle Sprachfeatures zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="77869-143">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="77869-144">In der folgenden Tabelle sind die Mindestversionen des SDK mit dem C#-Compiler aufgeführt, der die entsprechende Sprachversion unterstützt:</span><span class="sxs-lookup"><span data-stu-id="77869-144">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="77869-145">C#-Version</span><span class="sxs-lookup"><span data-stu-id="77869-145">C# version</span></span> | <span data-ttu-id="77869-146">Mindestversion des SDK</span><span class="sxs-lookup"><span data-stu-id="77869-146">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="77869-147">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="77869-147">C# 8.0</span></span>     | <span data-ttu-id="77869-148">Microsoft Visual Studio/Build Tools 2019, Version 16.3, oder .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="77869-148">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="77869-149">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="77869-149">C# 7.3</span></span>     | <span data-ttu-id="77869-150">Microsoft Visual Studio/Build Tools 2017, Version 15.7</span><span class="sxs-lookup"><span data-stu-id="77869-150">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="77869-151">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="77869-151">C# 7.2</span></span>     | <span data-ttu-id="77869-152">Microsoft Visual Studio/Build Tools 2017, Version 15.5</span><span class="sxs-lookup"><span data-stu-id="77869-152">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="77869-153">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="77869-153">C# 7.1</span></span>     | <span data-ttu-id="77869-154">Microsoft Visual Studio/Build Tools 2017, Version 15.3</span><span class="sxs-lookup"><span data-stu-id="77869-154">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="77869-155">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="77869-155">C# 7.0</span></span>     | <span data-ttu-id="77869-156">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="77869-156">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="77869-157">C# 6</span><span class="sxs-lookup"><span data-stu-id="77869-157">C# 6</span></span>       | <span data-ttu-id="77869-158">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="77869-158">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="77869-159">C# 5</span><span class="sxs-lookup"><span data-stu-id="77869-159">C# 5</span></span>       | <span data-ttu-id="77869-160">Microsoft Visual Studio/Build Tools 2012 oder gebündelter .NET Framework 4.5-Compiler</span><span class="sxs-lookup"><span data-stu-id="77869-160">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="77869-161">C# 4</span><span class="sxs-lookup"><span data-stu-id="77869-161">C# 4</span></span>       | <span data-ttu-id="77869-162">Microsoft Visual Studio/Build Tools 2010 oder gebündelter .NET Framework 4.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="77869-162">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="77869-163">C# 3</span><span class="sxs-lookup"><span data-stu-id="77869-163">C# 3</span></span>       | <span data-ttu-id="77869-164">Microsoft Visual Studio/Build Tools 2008 oder gebündelter .NET Framework 3.5-Compiler</span><span class="sxs-lookup"><span data-stu-id="77869-164">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="77869-165">C# 2</span><span class="sxs-lookup"><span data-stu-id="77869-165">C# 2</span></span>       | <span data-ttu-id="77869-166">Microsoft Visual Studio/Build Tools 2005 oder gebündelter .NET Framework 2.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="77869-166">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="77869-167">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="77869-167">C# 1.0/1.2</span></span> | <span data-ttu-id="77869-168">Microsoft Visual Studio/Build Tools .NET 2002 oder gebündelter .NET Framework 1.0-Compiler</span><span class="sxs-lookup"><span data-stu-id="77869-168">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="77869-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77869-169">See also</span></span>

- [<span data-ttu-id="77869-170">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="77869-170">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="77869-171">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="77869-171">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
