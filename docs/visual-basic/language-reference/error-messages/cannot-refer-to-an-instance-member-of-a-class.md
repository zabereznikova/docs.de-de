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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701173"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="f89ea-102">Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f89ea-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="f89ea-103">Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse in einer freigegebenen Prozedur zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f89ea-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="f89ea-104">Im folgenden Beispiel wird eine solche Situation veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f89ea-104">The following example demonstrates such a situation.</span></span>  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f89ea-105">Im vorherigen Beispiel generiert die Zuweisungsanweisung `x = 10` diese Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="f89ea-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="f89ea-106">Dies liegt daran, dass eine freigegebene Prozedur versucht, auf eine Instanzvariable zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f89ea-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="f89ea-107">Die Variable `x` ist ein Instanzmember, weil Sie nicht als " [Shared](../../../visual-basic/language-reference/modifiers/shared.md)" deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="f89ea-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="f89ea-108">Jede Instanz der Klasse `sample` enthält eine eigene Variable `x`.</span><span class="sxs-lookup"><span data-stu-id="f89ea-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="f89ea-109">Wenn eine Instanz den Wert `x` festlegt oder ändert, wirkt sich dies nicht auf den Wert von `x` in einer anderen Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="f89ea-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="f89ea-110">Die Prozedur `setX` ist jedoch für alle Instanzen der Klasse `sample` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f89ea-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="f89ea-111">Dies bedeutet, dass Sie keiner Instanz der-Klasse zugeordnet ist, sondern unabhängig von einzelnen Instanzen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f89ea-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="f89ea-112">Da keine Verbindung mit einer bestimmten Instanz besteht, kann `setX` nicht auf eine Instanzvariable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f89ea-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="f89ea-113">Er muss nur für `Shared`-Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f89ea-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="f89ea-114">Wenn `setX` den Wert einer freigegebenen Variablen festlegt oder ändert, ist dieser neue Wert für alle Instanzen der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f89ea-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="f89ea-115">**Fehler-ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="f89ea-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f89ea-116">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f89ea-116">To correct this error</span></span>  
  
1. <span data-ttu-id="f89ea-117">Entscheiden Sie, ob der Member für alle Instanzen der Klasse freigegeben werden soll, oder ob der Member für jede Instanz beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="f89ea-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="f89ea-118">Wenn Sie möchten, dass eine einzelne Kopie des Members von allen Instanzen gemeinsam verwendet wird, fügen Sie der Element Deklaration das Schlüsselwort `Shared` hinzu.</span><span class="sxs-lookup"><span data-stu-id="f89ea-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="f89ea-119">Behalten Sie das `Shared`-Schlüsselwort in der Prozedur Deklaration bei.</span><span class="sxs-lookup"><span data-stu-id="f89ea-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="f89ea-120">Wenn jede Instanz über eine eigene Kopie des Members verfügen soll, geben Sie `Shared` nicht für die Element Deklaration an.</span><span class="sxs-lookup"><span data-stu-id="f89ea-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="f89ea-121">Entfernen Sie das Schlüsselwort "`Shared`" aus der Prozedur Deklaration.</span><span class="sxs-lookup"><span data-stu-id="f89ea-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89ea-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f89ea-122">See also</span></span>

- [<span data-ttu-id="f89ea-123">Shared</span><span class="sxs-lookup"><span data-stu-id="f89ea-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
