---
title: Die Struktur "<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 598aef3943a53ee6eb97064819c9128de1839f52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055107"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="d8deb-102">Struktur '\<Strukturname > "muss mindestens eine Instanzmembervariable oder mindestens eine Instanz Event-Deklaration, die nicht als"Custom"enthalten</span><span class="sxs-lookup"><span data-stu-id="d8deb-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>
<span data-ttu-id="d8deb-103">Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d8deb-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="d8deb-104">Jede Struktur müssen entweder eine Variable oder ein Ereignis, das auf jede spezifische Instanz (nicht freigegeben) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="d8deb-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="d8deb-105">Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht.</span><span class="sxs-lookup"><span data-stu-id="d8deb-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="d8deb-106">Darüber hinaus, wenn keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis vorhanden sind, dieses Ereignis keine `Custom` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d8deb-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="d8deb-107">**Fehler-ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="d8deb-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8deb-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d8deb-108">To correct this error</span></span>  
  
- <span data-ttu-id="d8deb-109">Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`.</span><span class="sxs-lookup"><span data-stu-id="d8deb-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="d8deb-110">Wenn Sie nur ein Ereignis definieren, muss sie sowohl nicht benutzerdefinierte als auch nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d8deb-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8deb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8deb-111">See also</span></span>

- [<span data-ttu-id="d8deb-112">Strukturen</span><span class="sxs-lookup"><span data-stu-id="d8deb-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d8deb-113">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="d8deb-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="d8deb-114">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d8deb-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
