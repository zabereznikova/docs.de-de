---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 463dd2454aafebf11554fb7bacdb73724c3130d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392157"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="a0e9e-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0e9e-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="a0e9e-103">Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0e9e-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a0e9e-104">Remarks</span></span>  
 <span data-ttu-id="a0e9e-105">Der- `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="a0e9e-106">Der [Overridable](overridable.md) -Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-106">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="a0e9e-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="a0e9e-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="a0e9e-108">Wenn der `Overridable` - `NotOverridable` Modifizierer oder der-Modifizierer nicht angegeben wird, ist die Standardeinstellung davon abhängig, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="a0e9e-109">Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable` . andernfalls ist Sie `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="a0e9e-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="a0e9e-110">Ein Element, das nicht überschrieben werden kann, wird manchmal als *versiegeltes* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="a0e9e-111">Sie können `NotOverridable` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="a0e9e-112">Sie können `NotOverridable` nur für eine Eigenschaft oder Prozedur angeben, die eine andere Eigenschaft oder Prozedur überschreibt, d. h. nur in Kombination mit `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="a0e9e-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="a0e9e-113">Kombinierte modifiziererer</span><span class="sxs-lookup"><span data-stu-id="a0e9e-113">Combined Modifiers</span></span>  
 <span data-ttu-id="a0e9e-114">Sie können `Overridable` oder `NotOverridable` für eine `Private` Methode nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="a0e9e-115">Sie können nicht `NotOverridable` mit `MustOverride` , `Overridable` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="a0e9e-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="a0e9e-116">Verwendung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-116">Usage</span></span>  
 <span data-ttu-id="a0e9e-117">Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a0e9e-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a0e9e-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="a0e9e-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="a0e9e-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="a0e9e-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0e9e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0e9e-121">See also</span></span>

- [<span data-ttu-id="a0e9e-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="a0e9e-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a0e9e-123">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="a0e9e-123">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="a0e9e-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="a0e9e-124">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="a0e9e-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="a0e9e-125">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="a0e9e-126">Überschreibt</span><span class="sxs-lookup"><span data-stu-id="a0e9e-126">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="a0e9e-127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a0e9e-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="a0e9e-128">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0e9e-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
