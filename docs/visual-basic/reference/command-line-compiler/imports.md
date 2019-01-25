---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 9e5adcce85c4ca4863d28784a7d7f61c441a06c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588443"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="f378c-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f378c-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="f378c-103">Importiert Namespaces aus einer angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="f378c-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f378c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f378c-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f378c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f378c-105">Arguments</span></span>  
  
|<span data-ttu-id="f378c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f378c-106">Term</span></span>|<span data-ttu-id="f378c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f378c-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="f378c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f378c-108">Required.</span></span> <span data-ttu-id="f378c-109">Durch Trennzeichen getrennte Liste von Namespaces importiert werden.</span><span class="sxs-lookup"><span data-stu-id="f378c-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f378c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f378c-110">Remarks</span></span>  
 <span data-ttu-id="f378c-111">Die `-imports` Option importiert alle Namespaces, die in den aktuellen Satz von Quelldateien oder einer referenzierten Assembly definiert.</span><span class="sxs-lookup"><span data-stu-id="f378c-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="f378c-112">Die Elemente in einem Namespace, der mit angegebenen `-imports` stehen für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="f378c-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="f378c-113">Verwenden Sie die [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) um einen Namespace in einer einzelnen Quellcodedatei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f378c-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="f378c-114">Festlegen/imports in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f378c-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f378c-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f378c-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f378c-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f378c-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f378c-117">2.  Klicken Sie auf die Registerkarte **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="f378c-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="f378c-118">3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f378c-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="f378c-119">4.  Klicken Sie auf die **Benutzerimport hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="f378c-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f378c-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f378c-120">Example</span></span>  
 <span data-ttu-id="f378c-121">Der folgende Code wird kompiliert, wenn `/imports:system.globalization` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f378c-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="f378c-122">Ohne diese eine erfolgreiche Kompilierung erfordert entweder, dass ein `Imports System.Globalization` Anweisung eingeschlossen werden, am Anfang der Quellcodedatei, oder die Eigenschaft als voll qualifiziert werden `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="f378c-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f378c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f378c-123">See also</span></span>
- [<span data-ttu-id="f378c-124">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f378c-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f378c-125">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f378c-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f378c-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f378c-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
