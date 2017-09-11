---
title: / vbruntime | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cb07ed8c2f6070079cc51c290ff5a61305c5a5d3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="vbruntime"></a><span data-ttu-id="46b33-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="46b33-102">/vbruntime</span></span>
<span data-ttu-id="46b33-103">Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="46b33-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46b33-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="46b33-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="46b33-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="46b33-106">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="46b33-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="46b33-107">Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="46b33-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="46b33-108">Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek und betten Sie Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in die Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="46b33-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="46b33-109">Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).</span><span class="sxs-lookup"><span data-stu-id="46b33-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b33-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46b33-110">Remarks</span></span>  
 <span data-ttu-id="46b33-111">Die `/vbruntime` -Compileroption können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll.</span><span class="sxs-lookup"><span data-stu-id="46b33-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="46b33-112">Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf einer Visual Basic-Laufzeithilfsfunktion zu generieren.</span><span class="sxs-lookup"><span data-stu-id="46b33-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="46b33-113">(Ein *Visual Basic-Laufzeithilfsfunktion* ist eine Funktion definiert, die in Microsoft.VisualBasic.dll, die zur Laufzeit, um eine bestimmte Sprachsemantik auszuführen aufgerufen wird.)</span><span class="sxs-lookup"><span data-stu-id="46b33-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="46b33-114">Die `/vbruntime+` Option führt zum selben Verhalten, das auftritt, wenn kein `/vbruntime` -Schalter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="46b33-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="46b33-115">Können Sie die `/vbruntime+` Option zum Überschreiben von vorherigen `/vbruntime` Switches.</span><span class="sxs-lookup"><span data-stu-id="46b33-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="46b33-116">Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `/vbruntime-` oder `vbruntime:``path` Optionen.</span><span class="sxs-lookup"><span data-stu-id="46b33-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="46b33-117">Einbetten von Visual Basic-Laufzeit-Kernfunktionalität</span><span class="sxs-lookup"><span data-stu-id="46b33-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="46b33-118">Die `/vbruntime*` Option können Sie ohne einen Verweis auf eine Laufzeitbibliothek kompilieren.</span><span class="sxs-lookup"><span data-stu-id="46b33-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="46b33-119">Stattdessen ist Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet.</span><span class="sxs-lookup"><span data-stu-id="46b33-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="46b33-120">Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die die Visual Basic-Laufzeit nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="46b33-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="46b33-121">Die folgenden Elemente für die Common Language Runtime eingebettet werden:</span><span class="sxs-lookup"><span data-stu-id="46b33-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="46b33-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>Klasse</xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="46b33-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="46b33-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>Methode</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="46b33-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="46b33-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>Methode</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="46b33-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="46b33-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>Methode</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="46b33-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="46b33-126"><xref:Microsoft.VisualBasic.Constants.vbBack>Konstante</xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="46b33-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="46b33-127"><xref:Microsoft.VisualBasic.Constants.vbCr>Konstante</xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="46b33-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="46b33-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>Konstante</xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="46b33-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="46b33-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>Konstante</xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="46b33-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="46b33-130"><xref:Microsoft.VisualBasic.Constants.vbLf>Konstante</xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="46b33-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="46b33-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>Konstante</xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="46b33-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="46b33-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>Konstante</xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="46b33-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="46b33-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>Konstante</xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="46b33-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="46b33-134"><xref:Microsoft.VisualBasic.Constants.vbTab>Konstante</xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="46b33-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="46b33-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>Konstante</xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="46b33-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="46b33-136">Einige Objekte von der `My` Typ</span><span class="sxs-lookup"><span data-stu-id="46b33-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="46b33-137">Bei der Kompilierung mit der `/vbruntime*` -Option, und der Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit den Kernfunktionen eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass der Member nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="46b33-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="46b33-138">Verweisen auf eine angegebene Bibliothek</span><span class="sxs-lookup"><span data-stu-id="46b33-138">Referencing a specified library</span></span>  
 <span data-ttu-id="46b33-139">Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle der standardmäßigen Visual Basic-Laufzeitbibliothek kompilieren.</span><span class="sxs-lookup"><span data-stu-id="46b33-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="46b33-140">Wenn der Wert für das `path` -Argument einen vollqualifizierten Pfad zu einer DLL ist, verwendet der Compiler diese Datei als Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="46b33-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="46b33-141">Wenn der Wert für das `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, die Visual Basic-Compiler wird zuerst nach der angegebenen DLL im aktuellen Ordner suchen.</span><span class="sxs-lookup"><span data-stu-id="46b33-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="46b33-142">Danach sucht in den Pfad, die Sie angegeben haben die [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="46b33-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="46b33-143">Wenn die `/sdkpath` -Compileroption nicht verwendet wird, sucht der Compiler nach der angegebenen DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="46b33-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46b33-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46b33-144">Example</span></span>  
 <span data-ttu-id="46b33-145">Das folgende Beispiel zeigt, wie Sie die `/vbruntime` Option einen Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="46b33-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="46b33-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46b33-146">See Also</span></span>  
 <span data-ttu-id="46b33-147">[Visual Basic-Core – neue Kompilierungsmodus in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span><span class="sxs-lookup"><span data-stu-id="46b33-147">[Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span></span>  
<span data-ttu-id="46b33-148"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="46b33-148"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="46b33-149"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="46b33-149"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="46b33-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="46b33-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
