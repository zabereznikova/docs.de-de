---
title: -vbruntime
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6c6529fabddc75fb6ac751e0314011f05db7869
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-vbruntime"></a><span data-ttu-id="b3f86-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="b3f86-102">-vbruntime</span></span>
<span data-ttu-id="b3f86-103">Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="b3f86-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3f86-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="b3f86-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b3f86-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="b3f86-106">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3f86-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="b3f86-107">Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3f86-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="b3f86-108">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek und betten Sie Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in die Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="b3f86-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="b3f86-109">Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).</span><span class="sxs-lookup"><span data-stu-id="b3f86-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3f86-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3f86-110">Remarks</span></span>  
 <span data-ttu-id="b3f86-111">Die `-vbruntime` (Compileroption) können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="b3f86-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="b3f86-112">Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf an eine Visual Basic-Laufzeit-Hilfsprogramm zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b3f86-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="b3f86-113">(Ein *Visual Basic-Laufzeit-Hilfsprogramm* ist eine Funktion, die in "Microsoft.VisualBasic.dll", die zur Laufzeit zum Ausführen einer bestimmten Sprache semantische aufgerufen wird.)</span><span class="sxs-lookup"><span data-stu-id="b3f86-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="b3f86-114">Die `-vbruntime+` Option führt zum gleichen Verhalten, das auftritt, wenn kein `-vbruntime` -Schalter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b3f86-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="b3f86-115">Können Sie die `-vbruntime+` Option aus, um die vorherigen überschreiben `-vbruntime` Switches.</span><span class="sxs-lookup"><span data-stu-id="b3f86-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="b3f86-116">Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `-vbruntime-` oder `-vbruntime:path` Optionen.</span><span class="sxs-lookup"><span data-stu-id="b3f86-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="b3f86-117">Einbetten von Visual Basic-Laufzeit-Kernfunktionalität</span><span class="sxs-lookup"><span data-stu-id="b3f86-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="b3f86-118">Die `-vbruntime*` Option ermöglicht es Ihnen, ohne einen Verweis auf eine Laufzeitbibliothek kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b3f86-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="b3f86-119">Stattdessen ist Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet.</span><span class="sxs-lookup"><span data-stu-id="b3f86-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="b3f86-120">Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die der Visual Basic-Laufzeit nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3f86-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="b3f86-121">Die folgenden Elemente für die Common Language Runtime eingebettet werden:</span><span class="sxs-lookup"><span data-stu-id="b3f86-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="b3f86-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse</span><span class="sxs-lookup"><span data-stu-id="b3f86-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="b3f86-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="b3f86-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="b3f86-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="b3f86-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="b3f86-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="b3f86-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="b3f86-126"><xref:Microsoft.VisualBasic.Constants.vbBack> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="b3f86-127"><xref:Microsoft.VisualBasic.Constants.vbCr> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="b3f86-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="b3f86-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="b3f86-130"><xref:Microsoft.VisualBasic.Constants.vbLf> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="b3f86-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="b3f86-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="b3f86-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="b3f86-134"><xref:Microsoft.VisualBasic.Constants.vbTab> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="b3f86-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Konstante</span><span class="sxs-lookup"><span data-stu-id="b3f86-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="b3f86-136">Einige Objekte von der `My` Typ</span><span class="sxs-lookup"><span data-stu-id="b3f86-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="b3f86-137">Wenn Sie mit: Kompilieren Sie die `-vbruntime*` Option und dem Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit der Kernfunktionalität eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass der Member nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b3f86-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="b3f86-138">Verweis auf eine angegebene Bibliothek</span><span class="sxs-lookup"><span data-stu-id="b3f86-138">Referencing a specified library</span></span>  
 <span data-ttu-id="b3f86-139">Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle des standardmäßigen Visual Basic-Laufzeitbibliothek kompiliert.</span><span class="sxs-lookup"><span data-stu-id="b3f86-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="b3f86-140">Wenn der Wert für die `path` -Argument einen vollqualifizierten Pfad zu einer DLL ist, verwendet der Compiler diese Datei als der Common Language Runtime-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="b3f86-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="b3f86-141">Wenn der Wert für die `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, Visual Basic-Compiler sucht zuerst nach der angegebenen DLL im aktuellen Ordner.</span><span class="sxs-lookup"><span data-stu-id="b3f86-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="b3f86-142">Sucht dann in den Pfad, die Sie angegeben haben die [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="b3f86-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="b3f86-143">Wenn die `-sdkpath` -Compileroption nicht verwendet wird, sucht des Compilers nach der angegebenen DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="b3f86-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3f86-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3f86-144">Example</span></span>  
 <span data-ttu-id="b3f86-145">Das folgende Beispiel zeigt, wie Sie die `-vbruntime` Option aus, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b3f86-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3f86-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3f86-146">See Also</span></span>  
 [<span data-ttu-id="b3f86-147">Visual Basic Core – neue Kompilierungsmodus in Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="b3f86-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="b3f86-148">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b3f86-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b3f86-149">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b3f86-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b3f86-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="b3f86-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
