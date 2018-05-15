---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 330a5e6821c9c76f3503a35a5a5eabf24c686b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="18d63-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18d63-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="18d63-103">Importiert Namespaces aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="18d63-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18d63-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="18d63-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="18d63-105">Arguments</span></span>  
  
|<span data-ttu-id="18d63-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="18d63-106">Term</span></span>|<span data-ttu-id="18d63-107">Definition</span><span class="sxs-lookup"><span data-stu-id="18d63-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="18d63-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="18d63-108">Required.</span></span> <span data-ttu-id="18d63-109">Durch Trennzeichen getrennte Liste der Namespaces importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18d63-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18d63-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18d63-110">Remarks</span></span>  
 <span data-ttu-id="18d63-111">Die `-imports` Option importiert alle Namespaces in die aktuelle Gruppe, der Quelldateien oder einer referenzierten Assembly definiert.</span><span class="sxs-lookup"><span data-stu-id="18d63-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="18d63-112">Die Elemente in einem Namespace mit angegebenen `-imports` stehen für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="18d63-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="18d63-113">Verwenden Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf einen Namespace in einer einzelnen Quellcodedatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="18d63-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="18d63-114">Festlegen/importiert Sie in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18d63-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="18d63-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="18d63-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="18d63-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="18d63-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="18d63-117">2.  Klicken Sie auf die Registerkarte **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="18d63-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="18d63-118">3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="18d63-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="18d63-119">4.  Klicken Sie auf die **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="18d63-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18d63-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18d63-120">Example</span></span>  
 <span data-ttu-id="18d63-121">Im folgende Code wird kompiliert, wenn `/imports:system.globalization` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="18d63-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="18d63-122">Ohne diese erfolgreicher Kompilierung erfordert entweder, dass ein `Imports System.Globalization` Anweisung am Anfang der Quellcodedatei eingeschlossen werden, oder die Eigenschaft als voll qualifiziert werden `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="18d63-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="18d63-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18d63-123">See Also</span></span>  
 [<span data-ttu-id="18d63-124">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="18d63-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="18d63-125">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18d63-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="18d63-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="18d63-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
