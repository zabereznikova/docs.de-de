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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524483"
---
# <a name="-addmodule"></a><span data-ttu-id="69b75-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="69b75-102">-addmodule</span></span>
<span data-ttu-id="69b75-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="69b75-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69b75-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="69b75-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="69b75-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="69b75-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69b75-106">Required.</span></span> <span data-ttu-id="69b75-107">Eine durch Trennzeichen getrennte Liste mit Dateien, die Metadaten enthalten, jedoch keine Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="69b75-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="69b75-108">Dateinamen, die Leerzeichen enthalten, müssen in Anführungszeichen ("") eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="69b75-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b75-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69b75-109">Remarks</span></span>  
 <span data-ttu-id="69b75-110">Die durch den `fileList`-Parameter aufgelisteten Dateien müssen mit der Option `-target:module` oder einer entsprechenden Option eines anderen Compilers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="69b75-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="69b75-111">Alle mit `-addmodule` hinzugefügten Module müssen sich zur Laufzeit im selben Verzeichnis wie die Ausgabedatei befinden.</span><span class="sxs-lookup"><span data-stu-id="69b75-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="69b75-112">Das bedeutet, dass Sie zur Kompilierzeit ein Modul in einem beliebigen Verzeichnis angeben können, sich das Modul zur Laufzeit jedoch im Anwendungsverzeichnis befinden muss.</span><span class="sxs-lookup"><span data-stu-id="69b75-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="69b75-113">Andernfalls wird ein <xref:System.TypeLoadException>-Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69b75-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="69b75-114">Wenn Sie mit `-addmodule` (implizit oder explizit) eine andere [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)-Option als `-target:module` angeben, werden die Dateien, die Sie an `-addmodule` übergeben, Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="69b75-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="69b75-115">Eine Assembly ist zum Ausführen einer Ausgabedatei erforderlich, die mindestens eine mit `-addmodule` hinzugefügte Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="69b75-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="69b75-116">Verwenden Sie zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält, die Option [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md).</span><span class="sxs-lookup"><span data-stu-id="69b75-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69b75-117">Die Option `-addmodule` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="69b75-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69b75-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69b75-118">Example</span></span>  
 <span data-ttu-id="69b75-119">Mit dem folgenden Code wird ein Modul erstellt:</span><span class="sxs-lookup"><span data-stu-id="69b75-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="69b75-120">Mit dem folgenden Code werden die Modultypen importiert:</span><span class="sxs-lookup"><span data-stu-id="69b75-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="69b75-121">Wenn Sie `t1` ausführen, wird `802` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="69b75-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b75-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69b75-122">See also</span></span>

- [<span data-ttu-id="69b75-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="69b75-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="69b75-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69b75-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="69b75-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69b75-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="69b75-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="69b75-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
