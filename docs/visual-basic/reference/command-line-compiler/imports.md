---
title: / imports (Visual Basic) | Microsoft-Dokumentation
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
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
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
ms.openlocfilehash: e994e94dcc3cd00f868b6ae90e4c019eb5b9e2eb
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="imports-visual-basic"></a><span data-ttu-id="d6128-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6128-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="d6128-103">Importiert Namespaces aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="d6128-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6128-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6128-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6128-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d6128-105">Arguments</span></span>  
  
|<span data-ttu-id="d6128-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d6128-106">Term</span></span>|<span data-ttu-id="d6128-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d6128-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="d6128-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6128-108">Required.</span></span> <span data-ttu-id="d6128-109">Durch Kommas getrennte Liste der Namespaces importiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6128-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6128-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6128-110">Remarks</span></span>  
 <span data-ttu-id="d6128-111">Die `/imports` Option importiert einen Namespace definiert, die in den aktuellen Quelldateien oder einer Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d6128-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="d6128-112">Die Elemente in einem Namespace mit angegebenen `/imports` sind für alle Quellcodedateien in der Kompilierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6128-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="d6128-113">Verwenden Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) , einen Namespace in einer einzelnen Quellcodedatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6128-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="d6128-114">Festlegen/imports in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="d6128-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d6128-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d6128-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d6128-116">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d6128-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d6128-117">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="d6128-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="d6128-118">2.  Klicken Sie auf die **Verweise** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="d6128-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="d6128-119">3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d6128-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="d6128-120">4.  Klicken Sie auf die **Benutzerimport** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d6128-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d6128-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6128-121">Example</span></span>  
 <span data-ttu-id="d6128-122">Der folgende Code wird kompiliert, wenn `/imports:system` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d6128-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 <span data-ttu-id="d6128-123">[!code-vb[VbVbalrCompiler&21;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6128-123">[!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6128-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6128-124">See Also</span></span>  
 <span data-ttu-id="d6128-125">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6128-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d6128-126"> [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d6128-126"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="d6128-127"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="d6128-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
