---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524483"
---
# <a name="-addmodule"></a><span data-ttu-id="6b962-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="6b962-102">-addmodule</span></span>
<span data-ttu-id="6b962-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6b962-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b962-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b962-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b962-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6b962-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="6b962-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b962-106">Required.</span></span> <span data-ttu-id="6b962-107">Eine durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, aber keine Assemblymanifeste enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b962-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="6b962-108">Dateinamen, die Leerzeichen enthalten, müssen in Anführungszeichen ("") eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6b962-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b962-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b962-109">Remarks</span></span>  
 <span data-ttu-id="6b962-110">Die Dateien, die mit dem `fileList`-Parameter aufgelistet werden, müssen mit der `-target:module`-Option oder mit einem anderen Compiler, der `-target:module` entspricht, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b962-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="6b962-111">Alle Module, die mit `-addmodule` hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden.</span><span class="sxs-lookup"><span data-stu-id="6b962-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="6b962-112">Das heißt, Sie können zur Kompilierzeit ein Modul in einem beliebigen Verzeichnis angeben, das Modul muss sich jedoch zur Laufzeit im Anwendungsverzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="6b962-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="6b962-113">Wenn dies nicht der Fall ist, erhalten Sie einen <xref:System.TypeLoadException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="6b962-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="6b962-114">Wenn Sie (implizit oder explizit) eine beliebige[Ziel Option (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) als `-target:module` mit `-addmodule` angeben, werden die Dateien, die an `-addmodule` übergeben werden, Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="6b962-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="6b962-115">Eine Assembly ist erforderlich, um eine Ausgabedatei auszuführen, der eine oder mehrere Dateien mit `-addmodule` hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b962-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="6b962-116">Verwenden Sie [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) , um Metadaten aus einer Datei zu importieren, die eine Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="6b962-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b962-117">Die `-addmodule`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6b962-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b962-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b962-118">Example</span></span>  
 <span data-ttu-id="6b962-119">Mit dem folgenden Code wird ein Modul erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b962-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="6b962-120">Mit dem folgenden Code werden die Modultypen importiert.</span><span class="sxs-lookup"><span data-stu-id="6b962-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="6b962-121">Wenn Sie `t1` ausführen, wird `802` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b962-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b962-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b962-122">See also</span></span>

- [<span data-ttu-id="6b962-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6b962-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6b962-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b962-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="6b962-125">-Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b962-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="6b962-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6b962-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
