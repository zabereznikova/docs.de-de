---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839216"
---
# <a name="-addmodule"></a><span data-ttu-id="8ca8c-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="8ca8c-102">-addmodule</span></span>
<span data-ttu-id="8ca8c-103">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ca8c-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="8ca8c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8ca8c-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="8ca8c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-106">Required.</span></span> <span data-ttu-id="8ca8c-107">Durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, aber Manifesten nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="8ca8c-108">Dateinamen mit Leerzeichen müssen in Anführungszeichen eingeschlossen werden ("").</span><span class="sxs-lookup"><span data-stu-id="8ca8c-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ca8c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ca8c-109">Remarks</span></span>  
 <span data-ttu-id="8ca8c-110">Die Dateien sortiert nach der `fileList` Parameter muss erstellt werden, mit der `-target:module` Option oder mit einem anderen Compiler entspricht `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="8ca8c-111">Alle Module mit hinzugefügten `-addmodule` zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei muss.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="8ca8c-112">D. h. Sie können ein Modul in einem Verzeichnis angeben, zum Zeitpunkt der Kompilierung, aber das Modul muss zur Laufzeit im Anwendungsverzeichnis sein.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="8ca8c-113">Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="8ca8c-114">Bei Angabe von (implizit oder explizit) alle[-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option, die nicht `-target:module` mit `-addmodule`, übergeben Sie an, Dateien `-addmodule` Teil der Assembly des Projekts.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="8ca8c-115">Eine Assembly ist erforderlich, um eine Ausgabedatei ausführen, die eine oder mehrere Dateien hinzugefügt, mit `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="8ca8c-116">Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) um Metadaten aus einer Datei zu importieren, die eine Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ca8c-117">Die `-addmodule` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca8c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ca8c-118">Example</span></span>  
 <span data-ttu-id="8ca8c-119">Der folgende Code erstellt ein Modul.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="8ca8c-120">Im folgende Code werden die Typen des Moduls importiert.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="8ca8c-121">Beim Ausführen von `t1`, es gibt `802`.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca8c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ca8c-122">See also</span></span>

- [<span data-ttu-id="8ca8c-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8ca8c-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8ca8c-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ca8c-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="8ca8c-125">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ca8c-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="8ca8c-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8ca8c-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
