---
title: / addmodule | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2db0db5b5dd94f03e67d8680624e2a4ad23587f7
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="addmodule"></a><span data-ttu-id="2f57f-102">/addmodule</span><span class="sxs-lookup"><span data-stu-id="2f57f-102">/addmodule</span></span>
<span data-ttu-id="2f57f-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2f57f-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f57f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f57f-104">Syntax</span></span>  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f57f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2f57f-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="2f57f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2f57f-106">Required.</span></span> <span data-ttu-id="2f57f-107">Durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, jedoch keine Assemblymanifeste enthalten.</span><span class="sxs-lookup"><span data-stu-id="2f57f-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="2f57f-108">Dateinamen mit Leerzeichen sollten in Anführungszeichen eingeschlossen werden ("").</span><span class="sxs-lookup"><span data-stu-id="2f57f-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f57f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f57f-109">Remarks</span></span>  
 <span data-ttu-id="2f57f-110">Die Dateien von der `fileList` Parameter muss erstellt werden, mit der `/target:module` Option oder mit einem anderen Compiler entspricht `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="2f57f-110">The files listed by the `fileList` parameter must be created with the `/target:module` option, or with another compiler's equivalent to `/target:module`.</span></span>  
  
 <span data-ttu-id="2f57f-111">Alle Module mit hinzugefügt `/addmodule` muss sich im gleichen Verzeichnis wie die Ausgabedatei zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2f57f-111">All modules added with `/addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="2f57f-112">D. h. Sie können ein Modul in einem Verzeichnis zur Kompilierungszeit angeben, aber das Modul muss im Verzeichnis Anwendung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2f57f-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="2f57f-113">Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException>Fehler.</xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="2f57f-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="2f57f-114">Bei Angabe von (implizit oder explizit) alle[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) -Option als `/target:module` mit `/addmodule`, übergeben Sie an, Dateien `/addmodule` Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="2f57f-114">If you specify (implicitly or explicitly) any[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `/target:module` with `/addmodule`, the files you pass to `/addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="2f57f-115">Eine Assembly muss eine Ausgabedatei ausführen, die eine oder mehrere Dateien mit hinzugefügt `/addmodule`.</span><span class="sxs-lookup"><span data-stu-id="2f57f-115">An assembly is required to run an output file that has one or more files added with `/addmodule`.</span></span>  
  
 <span data-ttu-id="2f57f-116">Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="2f57f-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f57f-117">Die `/addmodule` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="2f57f-117">The `/addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f57f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f57f-118">Example</span></span>  
 <span data-ttu-id="2f57f-119">Der folgende Code erstellt ein Modul.</span><span class="sxs-lookup"><span data-stu-id="2f57f-119">The following code creates a module.</span></span>  
  
 <span data-ttu-id="2f57f-120">[!code-vb[VbVbalrCompiler&#47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f57f-120">[!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span></span>  
  
 <span data-ttu-id="2f57f-121">Der folgende Code importiert die Typen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="2f57f-121">The following code imports the module's types.</span></span>  
  
 <span data-ttu-id="2f57f-122">[!code-vb[VbVbalrCompiler&#48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f57f-122">[!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span></span>  
  
 <span data-ttu-id="2f57f-123">Beim Ausführen von `t1`, gibt es `802`.</span><span class="sxs-lookup"><span data-stu-id="2f57f-123">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f57f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f57f-124">See Also</span></span>  
 <span data-ttu-id="2f57f-125">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f57f-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2f57f-126"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="2f57f-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="2f57f-127"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="2f57f-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="2f57f-128"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2f57f-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
