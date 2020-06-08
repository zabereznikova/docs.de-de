---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 9e8146497d63d949f138d6cd08c9ea8c7b03c651
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414310"
---
# <a name="-addmodule"></a><span data-ttu-id="e0ced-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="e0ced-102">-addmodule</span></span>
<span data-ttu-id="e0ced-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e0ced-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ced-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0ced-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0ced-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e0ced-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="e0ced-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0ced-106">Required.</span></span> <span data-ttu-id="e0ced-107">Eine durch Trennzeichen getrennte Liste mit Dateien, die Metadaten enthalten, jedoch keine Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="e0ced-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="e0ced-108">Dateinamen, die Leerzeichen enthalten, müssen in Anführungszeichen ("") eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e0ced-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0ced-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0ced-109">Remarks</span></span>  
 <span data-ttu-id="e0ced-110">Die durch den `fileList`-Parameter aufgelisteten Dateien müssen mit der Option `-target:module` oder einer entsprechenden Option eines anderen Compilers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ced-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="e0ced-111">Alle mit `-addmodule` hinzugefügten Module müssen sich zur Laufzeit im selben Verzeichnis wie die Ausgabedatei befinden.</span><span class="sxs-lookup"><span data-stu-id="e0ced-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="e0ced-112">Das bedeutet, dass Sie zur Kompilierzeit ein Modul in einem beliebigen Verzeichnis angeben können, sich das Modul zur Laufzeit jedoch im Anwendungsverzeichnis befinden muss.</span><span class="sxs-lookup"><span data-stu-id="e0ced-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="e0ced-113">Andernfalls wird ein <xref:System.TypeLoadException>-Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0ced-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="e0ced-114">Wenn Sie mit `-addmodule` (implizit oder explizit) eine andere [-target (Visual Basic)](target.md)-Option als `-target:module` angeben, werden die Dateien, die Sie an `-addmodule` übergeben, Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="e0ced-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="e0ced-115">Eine Assembly ist zum Ausführen einer Ausgabedatei erforderlich, die mindestens eine mit `-addmodule` hinzugefügte Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="e0ced-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="e0ced-116">Verwenden Sie zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält, die Option [-reference (Visual Basic)](reference.md).</span><span class="sxs-lookup"><span data-stu-id="e0ced-116">Use [-reference (Visual Basic)](reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0ced-117">Die Option `-addmodule` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e0ced-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0ced-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0ced-118">Example</span></span>  
 <span data-ttu-id="e0ced-119">Mit dem folgenden Code wird ein Modul erstellt:</span><span class="sxs-lookup"><span data-stu-id="e0ced-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="e0ced-120">Mit dem folgenden Code werden die Modultypen importiert:</span><span class="sxs-lookup"><span data-stu-id="e0ced-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="e0ced-121">Wenn Sie `t1` ausführen, wird `802` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0ced-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ced-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0ced-122">See also</span></span>

- [<span data-ttu-id="e0ced-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e0ced-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e0ced-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0ced-124">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="e0ced-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0ced-125">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="e0ced-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e0ced-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
