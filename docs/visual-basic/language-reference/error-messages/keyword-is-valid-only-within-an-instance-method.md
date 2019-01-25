---
title: '&#39;&lt;Schlüsselwort&gt; &#39; ist nur innerhalb einer Instanzenmethode gültig'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595941"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="cf0a8-102">&#39;&lt;Schlüsselwort&gt; &#39; ist nur innerhalb einer Instanzenmethode gültig</span><span class="sxs-lookup"><span data-stu-id="cf0a8-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="cf0a8-103">Die `Me`, `MyClass`, und `MyBase` Schlüsselwörter beziehen sich auf bestimmte Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="cf0a8-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="cf0a8-104">Können Sie nicht in einem gemeinsam verwendeten `Function` oder `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="cf0a8-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="cf0a8-105">**Fehler-ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="cf0a8-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf0a8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf0a8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="cf0a8-107">Entfernen Sie das Schlüsselwort aus der Prozedur, oder Entfernen der `Shared` -Schlüsselwort aus der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="cf0a8-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0a8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf0a8-108">See also</span></span>
- [<span data-ttu-id="cf0a8-109">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="cf0a8-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="cf0a8-110">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="cf0a8-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="cf0a8-111">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="cf0a8-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
