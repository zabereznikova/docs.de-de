---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836726"
---
# <a name="default-visual-basic"></a><span data-ttu-id="7b21e-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b21e-102">Default (Visual Basic)</span></span>
<span data-ttu-id="7b21e-103">Gibt eine Eigenschaft als Standardeigenschaft von der Klasse, Struktur oder Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="7b21e-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b21e-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b21e-104">Remarks</span></span>  
 <span data-ttu-id="7b21e-105">Eine Klasse, Struktur oder Schnittstelle kann höchstens eine der Eigenschaften als Festlegen der *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="7b21e-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="7b21e-106">Wenn der Code einen Verweis auf eine Klasse oder Struktur ist ein Mitglied angegeben, löst Visual Basic dieser Verweis auf die Standardeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7b21e-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="7b21e-107">Standardeigenschaften können dazu führen, eine kleine Reduzierung in Code-Zeichen, aber leisten können Ihren Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7b21e-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="7b21e-108">Wenn der aufrufende Code nicht vertraut sind, mit der Klasse oder Struktur ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur ist es bestimmte nicht möglich, ob der Verweis der Klasse oder Struktur selbst oder an eine Standardeigenschaft greift auf.</span><span class="sxs-lookup"><span data-stu-id="7b21e-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="7b21e-109">Dies kann zu Compilerfehlern oder geringfügige Laufzeitlogik-Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="7b21e-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="7b21e-110">Sie können etwas reduziert die Wahrscheinlichkeit Eigenschaftenfehler standardmäßig immer mit der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) Festlegen der Compiler die typüberprüfung zu `On`.</span><span class="sxs-lookup"><span data-stu-id="7b21e-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="7b21e-111">Wenn Sie beabsichtigen, mit einer vordefinierten Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist wie der Name.</span><span class="sxs-lookup"><span data-stu-id="7b21e-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="7b21e-112">Wegen der genannten Nachteile sollten Sie keine Standardeigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="7b21e-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="7b21e-113">Sie sollten für die Lesbarkeit des Codes berücksichtigen Sie auch immer explizit verweisen, die allen Eigenschaften, auch die Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7b21e-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="7b21e-114">Die `Default` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7b21e-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="7b21e-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7b21e-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b21e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b21e-116">See also</span></span>

- [<span data-ttu-id="7b21e-117">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b21e-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="7b21e-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7b21e-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
