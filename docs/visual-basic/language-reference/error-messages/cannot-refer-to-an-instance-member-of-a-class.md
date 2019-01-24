---
title: Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: da3aa17c55a4ccc95e5f4c98d0f12712ef77d5c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729222"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="27e4e-102">Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="27e4e-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="27e4e-103">Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse über ein gemeinsames Verfahren zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="27e4e-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="27e4e-104">Das folgende Beispiel zeigt eine solche Situation.</span><span class="sxs-lookup"><span data-stu-id="27e4e-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="27e4e-105">Im vorherigen Beispiel die zuweisungsanweisung `x = 10` generiert diese Fehlermeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27e4e-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="27e4e-106">Dies ist, da ein gemeinsames Verfahren eine Instanzvariable zugreifen möchte.</span><span class="sxs-lookup"><span data-stu-id="27e4e-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="27e4e-107">Die Variable `x` ein Instanzmember ist, da er nicht als deklariert wird [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="27e4e-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="27e4e-108">Jede Instanz der Klasse `sample` enthält eine eigene Variable `x`.</span><span class="sxs-lookup"><span data-stu-id="27e4e-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="27e4e-109">Wenn eine Instanz legt fest oder ändert den Wert des `x`, es hat keine Auswirkungen auf den Wert der `x` in einer anderen Instanz.</span><span class="sxs-lookup"><span data-stu-id="27e4e-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="27e4e-110">Allerdings die Prozedur `setX` ist `Shared` von allen Instanzen der Klasse `sample`.</span><span class="sxs-lookup"><span data-stu-id="27e4e-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="27e4e-111">Dies bedeutet, es ist nicht mit einer Instanz der Klasse verknüpft und unabhängig von den einzelnen Instanzen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="27e4e-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="27e4e-112">Da sie keine Verbindung mit einer bestimmten Instanz ist, hat `setX` eine Instanzvariable kann nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="27e4e-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="27e4e-113">Es muss nur auf ausgeführt `Shared` Variablen.</span><span class="sxs-lookup"><span data-stu-id="27e4e-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="27e4e-114">Wenn `setX` legt fest oder ändert den Wert für eine freigegebene Variable, dass der neue Wert für alle Instanzen der Klasse verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="27e4e-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="27e4e-115">**Fehler-ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="27e4e-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="27e4e-116">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="27e4e-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="27e4e-117">Entscheiden Sie, ob das Element für alle Instanzen der Klasse freigegeben oder jeder Instanz beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="27e4e-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="27e4e-118">Wenn Sie eine einzelne Kopie des Elements, die für alle Instanzen freigegeben werden soll, Hinzufügen der `Shared` Schlüsselwort zur Memberdeklaration.</span><span class="sxs-lookup"><span data-stu-id="27e4e-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="27e4e-119">Beibehalten der `Shared` -Schlüsselwort in der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="27e4e-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="27e4e-120">Wenn Sie jede Instanz über ein eigenes Exemplar des Elements haben möchten, geben Sie keine `Shared` für die Element-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="27e4e-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="27e4e-121">Entfernen Sie die `Shared` -Schlüsselwort aus der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="27e4e-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e4e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27e4e-122">See also</span></span>
- [<span data-ttu-id="27e4e-123">Shared</span><span class="sxs-lookup"><span data-stu-id="27e4e-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
