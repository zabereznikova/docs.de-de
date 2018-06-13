---
title: Struktur &#39; &lt;Structurename&gt; &#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet enthalten &#39;benutzerdefinierte&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594497"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="18395-102">Struktur &#39; &lt;Structurename&gt; &#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet enthalten &#39;benutzerdefinierte&#39;</span><span class="sxs-lookup"><span data-stu-id="18395-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="18395-103">Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="18395-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="18395-104">Jede Struktur benötigen, eine Variable oder ein Ereignis, das für jede spezifische Instanz (nicht freigegebene) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="18395-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="18395-105">Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht.</span><span class="sxs-lookup"><span data-stu-id="18395-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="18395-106">Darüber hinaus treten keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis, das Ereignis nicht mit einem `Custom` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="18395-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="18395-107">**Fehler-ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="18395-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="18395-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="18395-108">To correct this error</span></span>  
  
-   <span data-ttu-id="18395-109">Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`.</span><span class="sxs-lookup"><span data-stu-id="18395-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="18395-110">Wenn Sie nur ein Ereignis definieren, muss es sowohl nicht benutzerdefinierte als auch nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="18395-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18395-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18395-111">See Also</span></span>  
 [<span data-ttu-id="18395-112">Strukturen</span><span class="sxs-lookup"><span data-stu-id="18395-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="18395-113">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="18395-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="18395-114">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18395-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
