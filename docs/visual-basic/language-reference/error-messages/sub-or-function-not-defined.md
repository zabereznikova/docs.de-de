---
title: Sub oder Funktion ist nicht definiert (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 397648618ea3764efafb5cff41deaef320bbeff3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982435"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="65bac-102">Sub oder Funktion ist nicht definiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65bac-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="65bac-103">Ein `Sub` oder `Function` muss definiert werden, damit Sie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="65bac-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="65bac-104">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="65bac-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="65bac-105">Der Prozedurname.</span><span class="sxs-lookup"><span data-stu-id="65bac-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="65bac-106">Versucht, eine Prozedur aus einem anderen Projekt aufzurufen, ohne Sie explizit einen Verweis auf das Projekt in der **Verweise** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="65bac-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="65bac-107">Angeben von einer Prozedur, die nicht an die aufrufende Prozedur angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65bac-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="65bac-108">Deklarieren einer Routine für Windows-Dynamic Link Library (DLL) oder Macintosh Coderessourcen-Routine, die nicht in der angegebenen Bibliothek oder einem Code-Ressource ist.</span><span class="sxs-lookup"><span data-stu-id="65bac-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="65bac-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="65bac-109">To correct this error</span></span>  
  
1. <span data-ttu-id="65bac-110">Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="65bac-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="65bac-111">Suchen Sie den Namen des Projekts mit der Prozedur, die Sie aufrufen möchten die **Verweise** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="65bac-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="65bac-112">Wenn es nicht angezeigt wird, klicken Sie auf die **Durchsuchen** Schaltfläche, um ihn zu suchen.</span><span class="sxs-lookup"><span data-stu-id="65bac-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="65bac-113">Wählen Sie das Kontrollkästchen links neben den Namen des Projekts, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="65bac-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="65bac-114">Überprüfen Sie den Namen der Routine.</span><span class="sxs-lookup"><span data-stu-id="65bac-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bac-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65bac-115">See also</span></span>

- [<span data-ttu-id="65bac-116">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="65bac-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="65bac-117">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="65bac-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="65bac-118">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="65bac-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="65bac-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="65bac-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
