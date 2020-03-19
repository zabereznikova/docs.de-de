---
title: Konstruktorentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401244"
---
# <a name="constructor-design"></a><span data-ttu-id="55fb6-102">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="55fb6-102">Constructor Design</span></span>

<span data-ttu-id="55fb6-103">Es gibt zwei Arten von Konstruktoren: Typkonstruktoren und Instanzkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="55fb6-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="55fb6-104">Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55fb6-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="55fb6-105">Instanzkonstruktoren werden ausgeführt, wenn eine Instanz eines Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="55fb6-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="55fb6-106">Typkonstruktoren können keine Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="55fb6-107">Instanzkonstruktoren können dies.</span><span class="sxs-lookup"><span data-stu-id="55fb6-107">Instance constructors can.</span></span> <span data-ttu-id="55fb6-108">Instanzkonstruktoren, die keine Parameter annehmen, werden häufig als parameterlose Konstruktoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="55fb6-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="55fb6-109">Konstruktoren sind die natürlichste Möglichkeit, Instanzen eines Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="55fb6-110">Die meisten Entwickler suchen und versuchen, einen Konstruktor zu verwenden, bevor sie alternative Möglichkeiten zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="55fb6-111">✔️ CONSIDER bietet einfache, idealerweise Standardkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="55fb6-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="55fb6-112">Ein einfacher Konstruktor hat eine sehr kleine Anzahl von Parametern, und alle Parameter sind Primitive oder Enumerungen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="55fb6-113">Solche einfachen Konstruktoren erhöhen die Benutzerfreundlichkeit des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="55fb6-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="55fb6-114">✔️ CONSIDER mit einer statischen Factorymethode anstelle eines Konstruktors, wenn die Semantik des gewünschten Vorgangs nicht direkt der Konstruktion einer neuen Instanz zugeordnet wird oder wenn sich die Entwurfsrichtlinien des Konstruktors als unnatürlich anfühlen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="55fb6-115">✔️ verwenden Konstruktorparameter als Verknüpfungen zum Festlegen von Haupteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="55fb6-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="55fb6-116">Es sollte keinen Unterschied in der Semantik zwischen der Verwendung des leeren Konstruktors gefolgt von einigen Eigenschaftssätzen und der Verwendung eines Konstruktors mit mehreren Argumenten geben.</span><span class="sxs-lookup"><span data-stu-id="55fb6-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="55fb6-117">✔️ verwenden denselben Namen für Konstruktorparameter und eine Eigenschaft, wenn die Konstruktorparameter verwendet werden, um einfach die Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="55fb6-118">Der einzige Unterschied zwischen solchen Parametern und den Eigenschaften sollte das Gehäuse sein.</span><span class="sxs-lookup"><span data-stu-id="55fb6-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="55fb6-119">✔️ minimale Arbeit im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="55fb6-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="55fb6-120">Konstruktoren sollten nicht viel anderes tun, als die Konstruktorparameter zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="55fb6-121">Die Kosten für jede andere Verarbeitung sollten bis erforderlich verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="55fb6-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="55fb6-122">✔️ werden ggf. Ausnahmen von Instanzkonstruktoren ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="55fb6-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="55fb6-123">✔️ DO explizit den öffentlichen parameterlosen Konstruktor in Klassen deklarieren, wenn ein solcher Konstruktor erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="55fb6-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="55fb6-124">Wenn Sie keine Konstruktoren für einen Typ explizit deklarieren, fügen viele Sprachen (z. B. C') automatisch einen öffentlichen parameterlosen Konstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="55fb6-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="55fb6-125">(Abstrakte Klassen erhalten einen geschützten Konstruktor.)</span><span class="sxs-lookup"><span data-stu-id="55fb6-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="55fb6-126">Das Hinzufügen eines parametrisierten Konstruktors zu einer Klasse verhindert, dass der Compiler den parameterlosen Konstruktor hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="55fb6-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="55fb6-127">Dies führt häufig zu zufälligen Bruchänderungen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="55fb6-128">❌AVOID definiert explizit parameterlose Konstruktoren für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="55fb6-129">Dies beschleunigt die Arrayerstellung, da der Parameterlose Konstruktor nicht definiert ist und nicht auf jedem Slot im Array ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="55fb6-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="55fb6-130">Beachten Sie, dass viele Compiler, einschließlich C', aus diesem Grund nicht zulassen, dass Strukturen über parameterlose Konstruktoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="55fb6-131">❌AVOID, die virtuelle Member für ein Objekt innerhalb des Konstruktors aufruft.</span><span class="sxs-lookup"><span data-stu-id="55fb6-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="55fb6-132">Wenn ein virtueller Member aufgerufen wird, wird die am häufigsten abgeleitete Außerkraftsetzung aufgerufen, auch wenn der Konstruktor des am häufigsten abgeleiteten Typs noch nicht vollständig ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="55fb6-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="55fb6-133">Typkonstruktorrichtlinien</span><span class="sxs-lookup"><span data-stu-id="55fb6-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="55fb6-134">✔️ machen statische Konstruktoren privat.</span><span class="sxs-lookup"><span data-stu-id="55fb6-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="55fb6-135">Ein statischer Konstruktor, der auch als Klassenkonstruktor bezeichnet wird, wird verwendet, um einen Typ zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="55fb6-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="55fb6-136">Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt oder statische Member für diesen Typ aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="55fb6-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="55fb6-137">Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="55fb6-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="55fb6-138">Wenn ein statischer Konstruktor nicht privat ist, kann er durch einen anderen Code als die CLR aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="55fb6-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="55fb6-139">Abhängig von den im Konstruktor ausgeführten Vorgängen kann dies zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="55fb6-140">Der C-Compiler erzwingt, dass statische Konstruktoren privat sind.</span><span class="sxs-lookup"><span data-stu-id="55fb6-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="55fb6-141">❌Nicht Ausnahmen von statischen Konstruktoren auslösen.</span><span class="sxs-lookup"><span data-stu-id="55fb6-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="55fb6-142">Wenn eine Ausnahme von einem Typkonstruktor ausgelöst wird, kann der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55fb6-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="55fb6-143">✔️ CONSIDER, statische Felder inline zu initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Laufzeit in der Lage ist, die Leistung von Typen zu optimieren, die keinen explizit definierten statischen Konstruktor haben.</span><span class="sxs-lookup"><span data-stu-id="55fb6-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="55fb6-144">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="55fb6-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="55fb6-145">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="55fb6-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="55fb6-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55fb6-146">See also</span></span>

- [<span data-ttu-id="55fb6-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="55fb6-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="55fb6-148">Framework Design-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="55fb6-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
