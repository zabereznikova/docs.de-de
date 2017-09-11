---
title: Sub oder Funktion nicht definiert (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
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
ms.openlocfilehash: 837beec039e1fb8f8a796b2781d93de6d4cfb33a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="399ee-102">Sub oder Funktion ist nicht definiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="399ee-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="399ee-103">Ein `Sub` oder `Function` muss definiert werden, um aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="399ee-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="399ee-104">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="399ee-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="399ee-105">Der Prozedurname.</span><span class="sxs-lookup"><span data-stu-id="399ee-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="399ee-106">Bei dem Versuch, eine Prozedur aus einem anderen Projekt aufrufen, ohne explizit einen Verweis auf das Projekt in der **Verweise** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="399ee-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="399ee-107">Angeben einer Prozedur, die für die aufrufende Prozedur nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="399ee-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="399ee-108">Deklarieren einer Windows-Dynamic Link Library (DLL)-Routine oder Macintosh-Coderessourcen-Routine, die nicht in der angegebenen Bibliothek oder Code-Ressource ist.</span><span class="sxs-lookup"><span data-stu-id="399ee-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="399ee-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="399ee-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="399ee-110">Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="399ee-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="399ee-111">Suchen Sie den Namen des Projekts mit der Prozedur aufrufen, die der **Verweise** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="399ee-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="399ee-112">Wenn es nicht angezeigt wird, klicken Sie auf die **Durchsuchen** Schaltfläche, um ihn zu suchen.</span><span class="sxs-lookup"><span data-stu-id="399ee-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="399ee-113">Wählen Sie das Kontrollkästchen links neben den Namen des Projekts, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="399ee-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="399ee-114">Überprüfen Sie den Namen der Routine.</span><span class="sxs-lookup"><span data-stu-id="399ee-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399ee-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="399ee-115">See Also</span></span>  
 <span data-ttu-id="399ee-116">[Error Types (Fehlertypen)](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="399ee-116">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="399ee-117"> [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="399ee-117"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="399ee-118"> [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="399ee-118"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="399ee-119"> [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)</span><span class="sxs-lookup"><span data-stu-id="399ee-119"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)</span></span>
