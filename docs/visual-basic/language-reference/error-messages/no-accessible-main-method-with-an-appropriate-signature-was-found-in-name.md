---
title: Keine zugreifbare &#39;Main&#39; Methode mit entsprechender Signatur wurde finden Sie unter &#39; &lt;Name&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501489"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="0f91f-102">Keine zugreifbare &#39;Main&#39; Methode mit entsprechender Signatur wurde finden Sie unter &#39; &lt;Name&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="0f91f-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="0f91f-103">Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="0f91f-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="0f91f-104">`Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="0f91f-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="0f91f-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="0f91f-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f91f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0f91f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="0f91f-107">Definieren einer `Public Sub Main` Verfahren für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="0f91f-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="0f91f-108">Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="0f91f-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f91f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f91f-109">See also</span></span>
- [<span data-ttu-id="0f91f-110">Struktur der Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="0f91f-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="0f91f-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="0f91f-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
