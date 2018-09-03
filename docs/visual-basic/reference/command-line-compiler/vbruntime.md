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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e83a85e29eb4447f8d3b9dddc4f6ccdbc771b23c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483774"
---
# <a name="-vbruntime"></a><span data-ttu-id="7a99c-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="7a99c-102">-vbruntime</span></span>
<span data-ttu-id="7a99c-103">Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="7a99c-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a99c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a99c-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a99c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7a99c-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="7a99c-106">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="7a99c-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="7a99c-107">Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="7a99c-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="7a99c-108">Ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren und Kernfunktionen, die aus der Visual Basic-Laufzeitbibliothek in die Assembly einbetten.</span><span class="sxs-lookup"><span data-stu-id="7a99c-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="7a99c-109">Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).</span><span class="sxs-lookup"><span data-stu-id="7a99c-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a99c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a99c-110">Remarks</span></span>  
 <span data-ttu-id="7a99c-111">Die `-vbruntime` Compileroption können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="7a99c-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="7a99c-112">Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf einer Visual Basic-Laufzeit-Hilfsprogramm zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7a99c-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="7a99c-113">(Ein *Visual Basic-Laufzeit-Hilfsprogramm* ist eine Funktion definiert, die in "Microsoft.VisualBasic.dll", die zur Laufzeit zum Ausführen einer bestimmten Sprache semantische aufgerufen wird.)</span><span class="sxs-lookup"><span data-stu-id="7a99c-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="7a99c-114">Die `-vbruntime+` Option erzeugt das gleiche Verhalten, wenn kein `-vbruntime` -Schalter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7a99c-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="7a99c-115">Sie können die `-vbruntime+` Option zum Überschreiben der vorherigen `-vbruntime` Switches.</span><span class="sxs-lookup"><span data-stu-id="7a99c-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="7a99c-116">Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `-vbruntime-` oder `-vbruntime:path` Optionen.</span><span class="sxs-lookup"><span data-stu-id="7a99c-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="7a99c-117">Einbetten von Visual Basic-Laufzeit-Kernfunktionen</span><span class="sxs-lookup"><span data-stu-id="7a99c-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="7a99c-118">Die `-vbruntime*` Option können Sie ohne einen Verweis auf eine Common Language Runtime-Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7a99c-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="7a99c-119">Stattdessen wird Kernfunktionen aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet.</span><span class="sxs-lookup"><span data-stu-id="7a99c-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="7a99c-120">Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die nicht die Visual Basic-Laufzeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="7a99c-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="7a99c-121">Es werden die folgenden Elemente für die Common Language Runtime eingebettet:</span><span class="sxs-lookup"><span data-stu-id="7a99c-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="7a99c-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse</span><span class="sxs-lookup"><span data-stu-id="7a99c-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="7a99c-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="7a99c-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="7a99c-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="7a99c-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="7a99c-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode</span><span class="sxs-lookup"><span data-stu-id="7a99c-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="7a99c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="7a99c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="7a99c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="7a99c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="7a99c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="7a99c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="7a99c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="7a99c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="7a99c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="7a99c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Konstante</span><span class="sxs-lookup"><span data-stu-id="7a99c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="7a99c-136">Einige Objekte von der `My` Typ</span><span class="sxs-lookup"><span data-stu-id="7a99c-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="7a99c-137">Wenn Sie mit der Kompilierung der `-vbruntime*` Option und den Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit den wichtigsten Funktionen eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass das Element nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7a99c-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="7a99c-138">Verweisen auf einer angegebenen Bibliothek</span><span class="sxs-lookup"><span data-stu-id="7a99c-138">Referencing a specified library</span></span>  
 <span data-ttu-id="7a99c-139">Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle der standardmäßigen Visual Basic-Laufzeitbibliothek kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7a99c-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="7a99c-140">Wenn der Wert für die `path` Argument ist, einen vollqualifizierten Pfad zu einer DLL, die der Compiler verwendet diese Datei als die Runtime-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="7a99c-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="7a99c-141">Wenn der Wert für die `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, Visual Basic-Compiler wird zuerst nach der angegebenen DLL im aktuellen Ordner gesucht.</span><span class="sxs-lookup"><span data-stu-id="7a99c-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="7a99c-142">Danach sucht in den Pfad der von Ihnen mithilfe angegebene der [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="7a99c-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="7a99c-143">Wenn die `-sdkpath` Compileroption nicht verwendet wird, sucht der Compiler nach der angegebenen DLL in .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="7a99c-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a99c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a99c-144">Example</span></span>  
 <span data-ttu-id="7a99c-145">Das folgende Beispiel zeigt, wie Sie mit der `-vbruntime` Option aus, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7a99c-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a99c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a99c-146">See Also</span></span>  
 [<span data-ttu-id="7a99c-147">Visual Basic-Core – neue Kompilierungsmodus in Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="7a99c-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="7a99c-148">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7a99c-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7a99c-149">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7a99c-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="7a99c-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="7a99c-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
