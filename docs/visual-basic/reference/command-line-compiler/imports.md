---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="e3ff4-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3ff4-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="e3ff4-103">Importiert Namespaces aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ff4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3ff4-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e3ff4-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e3ff4-105">Arguments</span></span>  
  
|<span data-ttu-id="e3ff4-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e3ff4-106">Term</span></span>|<span data-ttu-id="e3ff4-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e3ff4-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="e3ff4-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-108">Required.</span></span> <span data-ttu-id="e3ff4-109">Durch Trennzeichen getrennte Liste der Namespaces importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3ff4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3ff4-110">Remarks</span></span>  
 <span data-ttu-id="e3ff4-111">Die `/imports` Option importiert alle Namespaces in die aktuelle Gruppe, der Quelldateien oder einer referenzierten Assembly definiert.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="e3ff4-112">Die Elemente in einem Namespace mit angegebenen `/imports` stehen für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="e3ff4-113">Verwenden Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf einen Namespace in einer einzelnen Quellcodedatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="e3ff4-114">Festlegen/importiert Sie in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e3ff4-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e3ff4-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e3ff4-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e3ff4-117">2.  Klicken Sie auf die Registerkarte **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e3ff4-118">3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="e3ff4-119">4.  Klicken Sie auf die **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3ff4-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3ff4-120">Example</span></span>  
 <span data-ttu-id="e3ff4-121">Im folgende Code wird kompiliert, wenn `/imports:system` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e3ff4-121">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e3ff4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3ff4-122">See Also</span></span>  
 [<span data-ttu-id="e3ff4-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e3ff4-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e3ff4-124">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3ff4-124">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="e3ff4-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e3ff4-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
