---
title: "Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einer &#39; Mit &#39; Anweisung"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="fdaba-102">Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einer &#39; Mit &#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="fdaba-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="fdaba-103">Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht in einem `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="fdaba-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="fdaba-104">Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element mit dem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="fdaba-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="fdaba-105">Dies muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` Block, der den Memberzugriffsoperator enthält.</span><span class="sxs-lookup"><span data-stu-id="fdaba-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="fdaba-106">**Fehler-ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="fdaba-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdaba-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fdaba-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="fdaba-108">Sicherstellen, dass die `With` -Block ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="fdaba-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="fdaba-109">Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element mit dem Element.</span><span class="sxs-lookup"><span data-stu-id="fdaba-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdaba-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdaba-110">See Also</span></span>  
 [<span data-ttu-id="fdaba-111">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="fdaba-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="fdaba-112">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fdaba-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
