---
title: Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a15d36c0b3a4d6b1657d583de0dc61621da960d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="a4392-102">Auf einen Instanzmember einer Klasse kann nicht ohne explizite Instanz einer Klasse von einer/m freigegebenen Methode/Member aus verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a4392-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="a4392-103">Sie haben versucht, auf einen nicht freigegebenen Member einer Klasse von eine freigegebene Prozedur verweisen.</span><span class="sxs-lookup"><span data-stu-id="a4392-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="a4392-104">Das folgende Beispiel zeigt eine solche Situation.</span><span class="sxs-lookup"><span data-stu-id="a4392-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="a4392-105">Im vorhergehenden Beispiel die zuweisungsanweisung `x = 10` generiert diese Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="a4392-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="a4392-106">Dies ist eine freigegebene Prozedur versucht, auf eine Instanzvariablen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a4392-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="a4392-107">Die Variable `x` ein Instanzmember ist, da er nicht als deklariert wird [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="a4392-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="a4392-108">Jede Instanz der Klasse `sample` enthält ihre eigene Variable `x`.</span><span class="sxs-lookup"><span data-stu-id="a4392-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="a4392-109">Wenn eine Instanz legt fest oder ändert den Wert des `x`, er hat keine Auswirkungen auf den Wert des `x` in einer anderen Instanz.</span><span class="sxs-lookup"><span data-stu-id="a4392-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="a4392-110">Allerdings die Prozedur `setX` ist `Shared` für alle Instanzen der Klasse `sample`.</span><span class="sxs-lookup"><span data-stu-id="a4392-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="a4392-111">Dies bedeutet, es ist nicht mit einer Instanz der Klasse verknüpft, aber unabhängig von den einzelnen Instanzen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4392-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="a4392-112">Da es keine Verbindung mit einer bestimmten Instanz besitzt `setX` eine Instanzvariablen kann nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a4392-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="a4392-113">Er muss ausgeführt werden, nur auf `Shared` Variablen.</span><span class="sxs-lookup"><span data-stu-id="a4392-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="a4392-114">Wenn `setX` legt fest oder ändert den Wert für eine freigegebene Variable, dass der neue Wert für alle Instanzen der Klasse verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a4392-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="a4392-115">**Fehler-ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="a4392-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a4392-116">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a4392-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="a4392-117">Entscheiden Sie, ob das Element für alle Instanzen der Klasse freigegeben oder jeder Instanz beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a4392-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="a4392-118">Wenn Sie eine einzelne Kopie des Elements, die für alle Instanzen freigegeben werden soll, fügen die `Shared` Schlüsselwort, um die Memberdeklaration.</span><span class="sxs-lookup"><span data-stu-id="a4392-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="a4392-119">Beibehalten der `Shared` -Schlüsselwort in der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a4392-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="a4392-120">Wenn Sie jede Instanz eine eigene Kopie des Elements haben soll, geben Sie keine `Shared` für die Memberdeklaration.</span><span class="sxs-lookup"><span data-stu-id="a4392-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="a4392-121">Entfernen Sie die `Shared` -Schlüsselwort aus der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a4392-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4392-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4392-122">See Also</span></span>  
 [<span data-ttu-id="a4392-123">Shared</span><span class="sxs-lookup"><span data-stu-id="a4392-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
