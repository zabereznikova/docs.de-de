---
title: '&#39; AddressOf &#39; Operand muss dem Namen einer Methode (ohne Klammern).'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords: BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="c3d78-102">&#39; AddressOf &#39; Operand muss dem Namen einer Methode (ohne Klammern).</span><span class="sxs-lookup"><span data-stu-id="c3d78-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="c3d78-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="c3d78-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="c3d78-104">Die Syntax lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c3d78-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="c3d78-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="c3d78-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="c3d78-106">Runden Klammern folgende Argument `AddressOf`, wobei keine erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c3d78-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="c3d78-107">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="c3d78-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3d78-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c3d78-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c3d78-109">Entfernen Sie die Klammern um das folgende Argument `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="c3d78-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="c3d78-110">Stellen Sie sicher, dass das Argument ein Methodenname ist.</span><span class="sxs-lookup"><span data-stu-id="c3d78-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d78-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3d78-111">See Also</span></span>  
 [<span data-ttu-id="c3d78-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="c3d78-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="c3d78-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="c3d78-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
