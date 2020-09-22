---
title: Die Struktur "<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a350940cf052aa8fbee4a1e3c61cbeaa4e37408a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870583"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="6b5c0-102">Die Struktur "\<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.</span><span class="sxs-lookup"><span data-stu-id="6b5c0-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>

<span data-ttu-id="6b5c0-103">Eine Struktur Definition enthält keine nicht freigegebenen Variablen oder nicht freigegebene Nichtbenutzer definierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="6b5c0-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="6b5c0-104">Jede Struktur muss entweder über eine Variable oder ein Ereignis verfügen, das für jede spezifische Instanz (nicht freigegeben) gilt, anstatt für alle Instanzen Kollektiv (frei[gegeben](../modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="6b5c0-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="6b5c0-105">Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht.</span><span class="sxs-lookup"><span data-stu-id="6b5c0-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="6b5c0-106">Wenn keine nicht freigegebenen Variablen und nur ein nicht frei gegebenes Ereignis vorhanden sind, kann dieses Ereignis nicht als `Custom` Ereignis verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b5c0-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="6b5c0-107">**Fehler-ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="6b5c0-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b5c0-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6b5c0-108">To correct this error</span></span>  
  
- <span data-ttu-id="6b5c0-109">Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht ist `Shared` .</span><span class="sxs-lookup"><span data-stu-id="6b5c0-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="6b5c0-110">Wenn Sie nur ein Ereignis definieren, darf es Nichtbenutzer definiert und nicht freigegeben sein.</span><span class="sxs-lookup"><span data-stu-id="6b5c0-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5c0-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b5c0-111">See also</span></span>

- [<span data-ttu-id="6b5c0-112">Strukturen</span><span class="sxs-lookup"><span data-stu-id="6b5c0-112">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6b5c0-113">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="6b5c0-113">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="6b5c0-114">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="6b5c0-114">Structure Statement</span></span>](../statements/structure-statement.md)
