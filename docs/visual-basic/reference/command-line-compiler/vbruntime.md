---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 31b719fb7e43cdd6ac44424b359999410dd608a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403043"
---
# <a name="-vbruntime"></a><span data-ttu-id="d9139-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="d9139-102">-vbruntime</span></span>
<span data-ttu-id="d9139-103">Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="d9139-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9139-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9139-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9139-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d9139-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="d9139-106">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek.</span><span class="sxs-lookup"><span data-stu-id="d9139-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="d9139-107">Kompilieren Sie mit einem Verweis auf die Visual Basic-Standardruntimebibliothek.</span><span class="sxs-lookup"><span data-stu-id="d9139-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="d9139-108">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek, und betten Sie die deren Kernfunktionalität in die Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="d9139-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="d9139-109">Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).</span><span class="sxs-lookup"><span data-stu-id="d9139-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9139-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9139-110">Remarks</span></span>  
 <span data-ttu-id="d9139-111">Mit der `-vbruntime`-Compileroption können Sie festlegen, dass der Compiler ohne einen Verweis auf die Visual Basic-Runtimebibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="d9139-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="d9139-112">Wenn Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek kompilieren, werden Fehler oder Warnungen für Code- oder Sprachkonstrukte protokolliert, die einen Aufruf eines Visual Basic-Runtimehilfsprogramms bewirken.</span><span class="sxs-lookup"><span data-stu-id="d9139-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="d9139-113">(Ein *Visual Basic-Runtimehilfsprogramm* ist eine in Microsoft.VisualBasic.dll definierte Funktion, die zur Laufzeit aufgerufen wird, um eine bestimmte Sprachsemantik auszuführen.)</span><span class="sxs-lookup"><span data-stu-id="d9139-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="d9139-114">Die Option `-vbruntime+` führt zum selben Verhalten wie bei einem nicht angegebenem `-vbruntime`-Switch.</span><span class="sxs-lookup"><span data-stu-id="d9139-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="d9139-115">Sie können die Option `-vbruntime+` verwenden, um vorherige `-vbruntime`-Switches zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d9139-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="d9139-116">Die meisten Objekte des `My`-Typs sind nicht verfügbar, wenn Sie die Optionen `-vbruntime-` oder `-vbruntime:path` verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9139-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="d9139-117">Einbetten der Kernfunktionalität der Visual Basic-Runtimebibliothek</span><span class="sxs-lookup"><span data-stu-id="d9139-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="d9139-118">Mit der `-vbruntime*`-Option können Sie ohne einen Verweis auf eine Runtimebibliothek kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d9139-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="d9139-119">Stattdessen wird die Kernfunktionalität der Visual Basic-Runtimebibliothek in die Benutzerassembly eingebettet.</span><span class="sxs-lookup"><span data-stu-id="d9139-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="d9139-120">Sie können diese Option verwenden, wenn die Anwendung auf Plattformen ausgeführt wird, die die Visual Basic-Runtimebibliothek nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="d9139-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="d9139-121">Die folgenden Member der Runtimebibliothek sind eingebettet:</span><span class="sxs-lookup"><span data-stu-id="d9139-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="d9139-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse</span><span class="sxs-lookup"><span data-stu-id="d9139-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="d9139-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="d9139-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="d9139-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="d9139-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="d9139-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="d9139-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="d9139-126"><xref:Microsoft.VisualBasic.Constants.vbBack>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="d9139-127"><xref:Microsoft.VisualBasic.Constants.vbCr>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="d9139-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="d9139-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="d9139-130"><xref:Microsoft.VisualBasic.Constants.vbLf>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="d9139-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="d9139-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="d9139-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="d9139-134"><xref:Microsoft.VisualBasic.Constants.vbTab>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="d9139-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>-Konstante</span><span class="sxs-lookup"><span data-stu-id="d9139-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="d9139-136">Objekte des `My`-Typs</span><span class="sxs-lookup"><span data-stu-id="d9139-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="d9139-137">Wenn Sie mithilfe der Option `-vbruntime*` kompilieren und Ihr Code auf einen Member aus der Visual Basic-Runtimebibliothek verweist, der nicht mit der Kernfunktionalität eingebettet ist, gibt der Compiler einen Fehler zurück, der angibt, dass der Member nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d9139-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="d9139-138">Verweisen auf eine angegebene Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d9139-138">Referencing a specified library</span></span>  
 <span data-ttu-id="d9139-139">Sie können das `path`-Argument verwenden, um anstelle der Visual Basic-Standardruntimebibliothek mit einem Verweis auf eine benutzerdefinierte Runtimebibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d9139-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="d9139-140">Wenn der Wert für das `path`-Argument ein vollqualifizierter Pfad zu einer DLL ist, verwendet der Compiler diese Datei als Runtimebibliothek.</span><span class="sxs-lookup"><span data-stu-id="d9139-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="d9139-141">Wenn der Wert für das `path`-Argument kein vollqualifizierter Pfad zu einer DLL ist, sucht der Visual Basic-Compiler zuerst nach der identifizierten DLL im aktuellen Ordner.</span><span class="sxs-lookup"><span data-stu-id="d9139-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="d9139-142">Anschließend wird der Pfad, den Sie angegeben haben, mithilfe der Compileroption [-sdkpath](sdkpath.md) gesucht.</span><span class="sxs-lookup"><span data-stu-id="d9139-142">It will then search in the path that you have specified by using the [-sdkpath](sdkpath.md) compiler option.</span></span> <span data-ttu-id="d9139-143">Wenn die `-sdkpath`-Compileroption nicht verwendet wird, sucht der Compiler nach der identifizierten DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="d9139-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9139-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9139-144">Example</span></span>  
 <span data-ttu-id="d9139-145">Im folgenden Beispiel wird gezeigt, wie die `-vbruntime`-Option verwendet wird, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d9139-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9139-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9139-146">See also</span></span>

- [<span data-ttu-id="d9139-147">Visual Basic Core: Neuer Kompilierungsmodus in Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="d9139-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="d9139-148">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d9139-148">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d9139-149">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d9139-149">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="d9139-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="d9139-150">-sdkpath</span></span>](sdkpath.md)
