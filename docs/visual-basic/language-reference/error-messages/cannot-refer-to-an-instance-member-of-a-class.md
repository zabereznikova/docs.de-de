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
ms.openlocfilehash: 9b388685299469d5865d57b698e3a66de912fa84
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250208"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="4d910-102">Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4d910-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>

<span data-ttu-id="4d910-103">Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse in einer freigegebenen Prozedur zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4d910-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="4d910-104">Das folgende Beispiel veranschaulicht eine solche Situation:</span><span class="sxs-lookup"><span data-stu-id="4d910-104">The following example demonstrates such a situation:</span></span>
  
```vb  
Class Sample
    Public x as Integer  
    Public Shared Sub SetX()
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="4d910-105">Im vorherigen Beispiel generiert die Zuweisungsanweisung `x = 10` diese Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="4d910-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="4d910-106">Dies liegt daran, dass eine freigegebene Prozedur versucht, auf eine Instanzvariable zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4d910-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="4d910-107">Die Variable `x` ist ein Instanzmember, weil Sie nicht als " [Shared](../modifiers/shared.md)" deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="4d910-107">The variable `x` is an instance member because it is not declared as [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="4d910-108">Jede Instanz der Klasse `Sample` enthält eine eigene Variable `x`.</span><span class="sxs-lookup"><span data-stu-id="4d910-108">Each instance of class `Sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="4d910-109">Wenn eine Instanz den Wert `x` festlegt oder ändert, wirkt sich dies nicht auf den Wert von `x` in einer anderen Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="4d910-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>
  
 <span data-ttu-id="4d910-110">Die Prozedur `SetX` ist jedoch für alle Instanzen der Klasse `Sample` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="4d910-110">However, the procedure `SetX` is `Shared` among all instances of class `Sample`.</span></span> <span data-ttu-id="4d910-111">Dies bedeutet, dass Sie keiner Instanz der-Klasse zugeordnet ist, sondern unabhängig von einzelnen Instanzen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4d910-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="4d910-112">Da keine Verbindung mit einer bestimmten Instanz besteht, kann `setX` nicht auf eine Instanzvariable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4d910-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="4d910-113">Er muss nur für `Shared`-Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d910-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="4d910-114">Wenn `SetX` den Wert einer freigegebenen Variablen festlegt oder ändert, ist dieser neue Wert für alle Instanzen der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4d910-114">When `SetX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>
  
 <span data-ttu-id="4d910-115">**Fehler-ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="4d910-115">**Error ID:** BC30369</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d910-116">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4d910-116">To correct this error</span></span>
  
1. <span data-ttu-id="4d910-117">Entscheiden Sie, ob der Member für alle Instanzen der Klasse freigegeben werden soll, oder ob der Member für jede Instanz beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d910-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>

2. <span data-ttu-id="4d910-118">Wenn Sie möchten, dass eine einzelne Kopie des Members von allen Instanzen gemeinsam verwendet wird, fügen Sie der Element Deklaration das Schlüsselwort `Shared` hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d910-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="4d910-119">Behalten Sie das `Shared`-Schlüsselwort in der Prozedur Deklaration bei.</span><span class="sxs-lookup"><span data-stu-id="4d910-119">Retain the `Shared` keyword in the procedure declaration.</span></span>

3. <span data-ttu-id="4d910-120">Wenn jede Instanz über eine eigene Kopie des Members verfügen soll, geben Sie `Shared` nicht für die Element Deklaration an.</span><span class="sxs-lookup"><span data-stu-id="4d910-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="4d910-121">Entfernen Sie das Schlüsselwort "`Shared`" aus der Prozedur Deklaration.</span><span class="sxs-lookup"><span data-stu-id="4d910-121">Remove the `Shared` keyword from the procedure declaration.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d910-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d910-122">See also</span></span>

- [<span data-ttu-id="4d910-123">Shared</span><span class="sxs-lookup"><span data-stu-id="4d910-123">Shared</span></span>](../modifiers/shared.md)
