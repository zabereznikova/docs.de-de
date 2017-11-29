---
title: /addmodule
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fff292605e125776ae25e667d4813d770ed0a0aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="addmodule"></a><span data-ttu-id="7a296-102">/addmodule</span><span class="sxs-lookup"><span data-stu-id="7a296-102">/addmodule</span></span>
<span data-ttu-id="7a296-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7a296-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a296-104">Syntax</span></span>  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a296-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7a296-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="7a296-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7a296-106">Required.</span></span> <span data-ttu-id="7a296-107">Durch Trennzeichen getrennte Liste der Dateien, die Metadaten enthalten, jedoch werden keine Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="7a296-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="7a296-108">Dateinamen mit Leerzeichen sollten in Anführungszeichen eingeschlossen sein ("").</span><span class="sxs-lookup"><span data-stu-id="7a296-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a296-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a296-109">Remarks</span></span>  
 <span data-ttu-id="7a296-110">Durch aufgelisteten Dateien der `fileList` Parameter muss erstellt werden, mit der `/target:module` -Option oder mit einem anderen Compiler entspricht `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="7a296-110">The files listed by the `fileList` parameter must be created with the `/target:module` option, or with another compiler's equivalent to `/target:module`.</span></span>  
  
 <span data-ttu-id="7a296-111">Alle Module mit hinzugefügt `/addmodule` muss sich im selben Verzeichnis wie die Ausgabedatei zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="7a296-111">All modules added with `/addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="7a296-112">D. h. Sie können ein Modul in einem beliebigen Verzeichnis angeben, zum Zeitpunkt der Kompilierung, aber das Modul muss zur Laufzeit im Anwendungsverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="7a296-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="7a296-113">Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="7a296-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="7a296-114">Bei Angabe von (implizit oder explizit) alle[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option außer `/target:module` mit `/addmodule`, die Dateien, die Sie übergeben `/addmodule` werden Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="7a296-114">If you specify (implicitly or explicitly) any[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `/target:module` with `/addmodule`, the files you pass to `/addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="7a296-115">Eine Assembly ist erforderlich, um eine Ausgabedatei ausführen, die einen oder mehrere Dateien hinzugefügt, mit `/addmodule`.</span><span class="sxs-lookup"><span data-stu-id="7a296-115">An assembly is required to run an output file that has one or more files added with `/addmodule`.</span></span>  
  
 <span data-ttu-id="7a296-116">Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="7a296-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a296-117">Die `/addmodule` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7a296-117">The `/addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a296-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a296-118">Example</span></span>  
 <span data-ttu-id="7a296-119">Der folgende Code erstellt ein Modul.</span><span class="sxs-lookup"><span data-stu-id="7a296-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 <span data-ttu-id="7a296-120">Im folgende Code werden die Typen des Moduls importiert.</span><span class="sxs-lookup"><span data-stu-id="7a296-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 <span data-ttu-id="7a296-121">Bei der Ausführung `t1`, gibt sie konsistent `802`.</span><span class="sxs-lookup"><span data-stu-id="7a296-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a296-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a296-122">See Also</span></span>  
 [<span data-ttu-id="7a296-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7a296-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7a296-124">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a296-124">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="7a296-125">/ Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a296-125">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="7a296-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7a296-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
