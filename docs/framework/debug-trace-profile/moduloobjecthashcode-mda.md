---
title: moduloObjectHashcode-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: 65bbdfec2d7050d1b474a8186a9ea6e9bb93bd9e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216181"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="1fb72-102">moduloObjectHashcode-MDA</span><span class="sxs-lookup"><span data-stu-id="1fb72-102">moduloObjectHashcode MDA</span></span>
<span data-ttu-id="1fb72-103">Der `moduloObjectHashcode`-MDA (Assistent für verwaltetes Debuggen) ändert das Verhalten der <xref:System.Object>-Klasse, um einen Modulo-Vorgang auf dem Hashcode auszuführen, der von der <xref:System.Object.GetHashCode%2A>-Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1fb72-103">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="1fb72-104">Der Standard-Modulo dieses MDA beträgt 1, wodurch <xref:System.Object.GetHashCode%2A> für alle Objekte 0 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1fb72-104">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1fb72-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="1fb72-105">Symptoms</span></span>  
 <span data-ttu-id="1fb72-106">Nachdem das Programm auf eine neue Version der Common Language Runtime (CLR) verschoben wurde, wird es nicht mehr ordnungsgemäß ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="1fb72-106">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
- <span data-ttu-id="1fb72-107">Das Programm erhält das falsche Objekt aus einem <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="1fb72-107">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
- <span data-ttu-id="1fb72-108">Die Reihenfolge der Enumeration aus einem <xref:System.Collections.Hashtable> hat eine Änderung, die die Anwendung unterbricht.</span><span class="sxs-lookup"><span data-stu-id="1fb72-108">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
- <span data-ttu-id="1fb72-109">Zwei Objekte, die gleich waren, sind nicht mehr gleich.</span><span class="sxs-lookup"><span data-stu-id="1fb72-109">Two objects that used to be equal are no longer equal.</span></span>  
  
- <span data-ttu-id="1fb72-110">Zwei Objekte, die nicht gleich waren, sind nun gleich.</span><span class="sxs-lookup"><span data-stu-id="1fb72-110">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1fb72-111">Ursache</span><span class="sxs-lookup"><span data-stu-id="1fb72-111">Cause</span></span>  
 <span data-ttu-id="1fb72-112">Ihr Programm erhält möglicherweise das falsche Objekt aus einer <xref:System.Collections.Hashtable>, da die Implementierung der <xref:System.Object.Equals%2A>-Methode der Klasse für den Schlüssel in der <xref:System.Collections.Hashtable> auf Objektgleichheit überprüft, indem die Ergebnisse des Aufrufs der <xref:System.Object.GetHashCode%2A>-Methode verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="1fb72-112">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="1fb72-113">Hashcodes sollten nicht verwendet werden, um auf Objektgleichheit zu testen, da zwei Objekte denselben Hashcode haben können, auch wenn ihre jeweiligen Felder unterschiedliche Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1fb72-113">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="1fb72-114">Diese Hashcodekonflikte sind in der Praxis zwar selten, aber sie kommen vor.</span><span class="sxs-lookup"><span data-stu-id="1fb72-114">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="1fb72-115">Als Konsequenz gibt es zwei Schlüssel in einem <xref:System.Collections.Hashtable>-Lookup, die nicht gleich sind, aber gleich zu sein scheinen, und das falsche Objekt wird aus der <xref:System.Collections.Hashtable> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1fb72-115">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="1fb72-116">Zur Verbesserung der Leistung kann sich die Implementierung der <xref:System.Object.GetHashCode%2A> zwischen Laufzeitversionen unterscheiden, damit Konflikte, die auf einer Version nicht auftreten, in nachfolgenden Versionen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="1fb72-116">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="1fb72-117">Aktivieren Sie diesen MDA, um zu überprüfen, ob der Code Fehler aufweist, wenn Hashcodes in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="1fb72-117">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="1fb72-118">Wenn dieser MDA aktiviert ist, gibt die <xref:System.Object.GetHashCode%2A>-Methode 0 (null) zurück, was zu einer Kollision aller Hashcodes führt.</span><span class="sxs-lookup"><span data-stu-id="1fb72-118">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="1fb72-119">Die einzige Auswirkung, die die Aktivierung dieses MDAs auf Ihr Programm haben sollte, ist die, dass das Programm langsamer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1fb72-119">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="1fb72-120">Die Reihenfolge der Enumeration aus einem <xref:System.Collections.Hashtable> kann sich möglicherweise von einer Laufzeitversion zur anderen ändern, wenn der Algorithmus für die Berechnung der Hashcodes für die Schlüsseländerung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1fb72-120">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="1fb72-121">Sie können diesen MDA aktivieren, um zu überprüfen, ob das Programm eine Abhängigkeit von der Reihenfolge der Enumeration der Schlüssel oder Werte aus einer Hashtabelle erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="1fb72-121">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1fb72-122">Lösung</span><span class="sxs-lookup"><span data-stu-id="1fb72-122">Resolution</span></span>  
 <span data-ttu-id="1fb72-123">Verwenden Sie niemals Hashcodes als Ersatz für die Objektidentität.</span><span class="sxs-lookup"><span data-stu-id="1fb72-123">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="1fb72-124">Implementieren Sie die Außerkraftsetzung der <xref:System.Object.Equals%2A?displayProperty=nameWithType>-Methode, um Hashcodes nicht zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="1fb72-124">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="1fb72-125">Erstellen Sie keine Abhängigkeiten von der Reihenfolge der Schlüsselenumerationen oder Werte in Hashtabellen.</span><span class="sxs-lookup"><span data-stu-id="1fb72-125">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1fb72-126">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1fb72-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="1fb72-127">Anwendungen werden langsamer ausgeführt, wenn dieser MDA aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1fb72-127">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="1fb72-128">Dieser MDA übernimmt lediglich den Hashcode, der zurückgegeben wurde und gibt stattdessen den Rest nach dem Dividieren durch einen Modulo zurück.</span><span class="sxs-lookup"><span data-stu-id="1fb72-128">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1fb72-129">Output</span><span class="sxs-lookup"><span data-stu-id="1fb72-129">Output</span></span>  
 <span data-ttu-id="1fb72-130">Es gibt keine Ausgabe für diesen MDA.</span><span class="sxs-lookup"><span data-stu-id="1fb72-130">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1fb72-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1fb72-131">Configuration</span></span>  
 <span data-ttu-id="1fb72-132">Das `modulus`-Attribut gibt den Modulo an, der auf dem Hashcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1fb72-132">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="1fb72-133">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="1fb72-133">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fb72-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fb72-134">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1fb72-135">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="1fb72-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
