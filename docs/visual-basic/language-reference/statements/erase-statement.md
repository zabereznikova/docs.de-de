---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="b6ac2-102">Erase-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6ac2-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="b6ac2-103">Zum Arrayvariablen freigeben und Aufheben der Zuordnung für ihre Elemente verwendeten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ac2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6ac2-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="b6ac2-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b6ac2-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="b6ac2-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-106">Required.</span></span> <span data-ttu-id="b6ac2-107">Liste der Arrayvariablen gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-107">List of array variables to be erased.</span></span> <span data-ttu-id="b6ac2-108">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6ac2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6ac2-109">Remarks</span></span>  
 <span data-ttu-id="b6ac2-110">Die `Erase` Anweisung kann nur auf Prozedurebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="b6ac2-111">Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur, aber nicht auf Klassen-oder Modulebene freigeben können.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="b6ac2-112">Die `Erase` Anweisung ist äquivalent zum Zuweisen von `Nothing` jedes Array-Variable.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6ac2-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6ac2-113">Example</span></span>  
 <span data-ttu-id="b6ac2-114">Im folgenden Beispiel wird die `Erase` Anweisung zum Löschen von zwei Arrays und Freigeben von Speicher (1000 und 100 Speicherelemente bzw.).</span><span class="sxs-lookup"><span data-stu-id="b6ac2-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="b6ac2-115">Die `ReDim` Anweisung dann weist eine neue Arrayinstanz auf das dreidimensionale Array.</span><span class="sxs-lookup"><span data-stu-id="b6ac2-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b6ac2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6ac2-116">See Also</span></span>  
 [<span data-ttu-id="b6ac2-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="b6ac2-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="b6ac2-118">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b6ac2-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
