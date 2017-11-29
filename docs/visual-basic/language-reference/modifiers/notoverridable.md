---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6fc5fb006b36cda1b6ad0e128604bc3bb427fd94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="93c96-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93c96-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="93c96-103">Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="93c96-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93c96-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93c96-104">Remarks</span></span>  
 <span data-ttu-id="93c96-105">Die `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="93c96-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="93c96-106">Die [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) Modifizierer ermöglicht einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="93c96-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="93c96-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="93c96-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="93c96-108">Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben wird, hängt von der Standardeinstellung gibt an, ob die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="93c96-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="93c96-109">Wenn die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt, die Standardeinstellung ist `Overridable`ist, andernfalls ist er `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="93c96-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="93c96-110">Ein Element, das nicht überschrieben werden kann, wird auch als bezeichnet. eine *versiegelten* Element.</span><span class="sxs-lookup"><span data-stu-id="93c96-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="93c96-111">Sie können `NotOverridable` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="93c96-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="93c96-112">Sie können angeben, `NotOverridable` nur auf eine Eigenschaft oder Prozedur, die eine andere Eigenschaft oder Prozedur, d. h. nur in Kombination mit überschreibt `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="93c96-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="93c96-113">Kombinierte Modifizierer</span><span class="sxs-lookup"><span data-stu-id="93c96-113">Combined Modifiers</span></span>  
 <span data-ttu-id="93c96-114">Sie können keine angeben `Overridable` oder `NotOverridable` für eine `Private` Methode.</span><span class="sxs-lookup"><span data-stu-id="93c96-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="93c96-115">Sie können keine angeben `NotOverridable` zusammen mit `MustOverride`, `Overridable`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="93c96-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="93c96-116">Verwendung</span><span class="sxs-lookup"><span data-stu-id="93c96-116">Usage</span></span>  
 <span data-ttu-id="93c96-117">Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="93c96-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="93c96-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="93c96-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="93c96-119">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="93c96-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="93c96-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="93c96-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="93c96-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93c96-121">See Also</span></span>  
 [<span data-ttu-id="93c96-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="93c96-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="93c96-123">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="93c96-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="93c96-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="93c96-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="93c96-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="93c96-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="93c96-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="93c96-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="93c96-127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="93c96-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="93c96-128">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93c96-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
