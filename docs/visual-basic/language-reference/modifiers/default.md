---
title: Standard
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
ms.openlocfilehash: bc213c3b5564d1833136df8f5b8dab1c6b012296
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875486"
---
# <a name="default-visual-basic"></a><span data-ttu-id="9172c-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9172c-102">Default (Visual Basic)</span></span>

<span data-ttu-id="9172c-103">Identifiziert eine Eigenschaft als Standard Eigenschaft ihrer Klasse, Struktur oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9172c-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9172c-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9172c-104">Remarks</span></span>  

 <span data-ttu-id="9172c-105">Eine Klasse, Struktur oder Schnittstelle kann höchstens eine ihrer Eigenschaften als *Standard Eigenschaft*angeben, vorausgesetzt, dass die Eigenschaft mindestens einen Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="9172c-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="9172c-106">Wenn Code einen Verweis auf eine Klasse oder Struktur erstellt, ohne einen Member anzugeben, löst Visual Basic diesen Verweis auf die Standard Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="9172c-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="9172c-107">Standardeigenschaften können zu einer geringfügigen Reduzierung der Quell Code Zeichen führen, aber Sie können den Code schwieriger lesbar machen.</span><span class="sxs-lookup"><span data-stu-id="9172c-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="9172c-108">Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, kann er, wenn er einen Verweis auf den Klassen-oder Struktur Namen erstellt, nicht sicher sein, ob dieser Verweis auf die Klasse oder Struktur selbst oder eine Standard Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="9172c-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="9172c-109">Dies kann zu Compilerfehlern oder geringfügigen Lauf Zeit Logik-Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="9172c-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="9172c-110">Sie können die Wahrscheinlichkeit von Fehlern bei Standardeigenschaften verringern, indem Sie immer die [Option Strict-Anweisung](../statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf festzulegen `On` .</span><span class="sxs-lookup"><span data-stu-id="9172c-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="9172c-111">Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code zu verwenden, müssen Sie feststellen, ob Sie über eine Default-Eigenschaft verfügt. wenn dies der Fall ist, müssen Sie den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="9172c-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="9172c-112">Aufgrund dieser Nachteile sollten Sie das Definieren von Standardeigenschaften in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="9172c-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="9172c-113">Zur besseren Lesbarkeit des Codes sollten Sie auch immer eine explizite Verweis auf alle Eigenschaften in Erwägung ziehen. Dies gilt auch für Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9172c-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="9172c-114">Der- `Default` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="9172c-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="9172c-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="9172c-115">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9172c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9172c-116">See also</span></span>

- [<span data-ttu-id="9172c-117">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9172c-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="9172c-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9172c-118">Keywords</span></span>](../keywords/index.md)
