---
title: Sub oder Funktion ist nicht definiert (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="fed91-102">Sub oder Funktion ist nicht definiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fed91-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="fed91-103">Ein `Sub` oder `Function` muss definiert werden, um aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fed91-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="fed91-104">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="fed91-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="fed91-105">Der Prozedurname.</span><span class="sxs-lookup"><span data-stu-id="fed91-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="fed91-106">Bei dem Versuch, eine Prozedur aus einem anderen Projekt aufrufen, ohne Sie explizit einen Verweis auf das Projekt in der **Verweise** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="fed91-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="fed91-107">Angeben einer Prozedur, die für die aufrufende Prozedur nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="fed91-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="fed91-108">Deklarieren einer Routine für Windows-Dynamic Link Library (DLL) oder Macintosh Coderessource Routine, die nicht in der angegebenen Bibliothek oder einem Code-Ressource ist.</span><span class="sxs-lookup"><span data-stu-id="fed91-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fed91-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fed91-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="fed91-110">Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="fed91-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="fed91-111">Suchen Sie den Namen des Projekts mit der Prozedur, die Sie aufrufen möchten die **Verweise** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="fed91-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="fed91-112">Wenn dies nicht angezeigt wird, klicken Sie auf die **Durchsuchen** Schaltfläche, um ihn zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fed91-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="fed91-113">Wählen Sie das Kontrollkästchen links neben den Namen des Projekts, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fed91-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fed91-114">Überprüfen Sie den Namen der Routine.</span><span class="sxs-lookup"><span data-stu-id="fed91-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed91-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fed91-115">See Also</span></span>  
 [<span data-ttu-id="fed91-116">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="fed91-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="fed91-117">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="fed91-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="fed91-118">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fed91-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="fed91-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fed91-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
