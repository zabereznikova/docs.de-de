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
author: KrzysztofCwalina
ms.openlocfilehash: a43ec815275e58f4bc6462fb4f5cb4733267de31
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972117"
---
# <a name="constructor-design"></a><span data-ttu-id="16c7e-102">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="16c7e-102">Constructor Design</span></span>

<span data-ttu-id="16c7e-103">Es gibt zwei Arten von Konstruktoren: Typkonstruktoren und Instanzkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="16c7e-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="16c7e-104">Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der-Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16c7e-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="16c7e-105">Instanzkonstruktoren werden ausgeführt, wenn eine Instanz eines Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="16c7e-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="16c7e-106">Typkonstruktoren können keine Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="16c7e-107">Instanzkonstruktoren können dies tun.</span><span class="sxs-lookup"><span data-stu-id="16c7e-107">Instance constructors can.</span></span> <span data-ttu-id="16c7e-108">Instanzkonstruktoren, die keine Parameter annehmen, werden häufig als Parameter lose Konstruktoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="16c7e-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="16c7e-109">Konstruktoren sind die natürlichste Methode, Instanzen eines Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="16c7e-110">Die meisten Entwickler suchen und versuchen, einen Konstruktor zu verwenden, bevor Sie alternative Methoden zum Erstellen von Instanzen (z. b. Factorymethoden) berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="16c7e-111">**✓ CONSIDER** einfach, im Idealfall Standard, Konstruktoren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="16c7e-112">Ein einfacher Konstruktor verfügt über eine sehr geringe Anzahl von Parametern, und alle Parameter sind primitive oder enumeraten.</span><span class="sxs-lookup"><span data-stu-id="16c7e-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="16c7e-113">Solche einfachen Konstruktoren erhöhen die Verwendbarkeit des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="16c7e-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="16c7e-114">**✓ CONSIDER** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.</span><span class="sxs-lookup"><span data-stu-id="16c7e-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="16c7e-115">**✓ DO** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="16c7e-116">Es sollte kein Unterschied in der Semantik zwischen der Verwendung des leeren Konstruktors bestehen, gefolgt von einigen Eigenschafts Sätzen und der Verwendung eines Konstruktors mit mehreren Argumenten.</span><span class="sxs-lookup"><span data-stu-id="16c7e-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="16c7e-117">**✓ DO** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="16c7e-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="16c7e-118">Der einzige Unterschied zwischen diesen Parametern und den Eigenschaften sollte die Schreibweise sein.</span><span class="sxs-lookup"><span data-stu-id="16c7e-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="16c7e-119">**✓ DO** nur minimale Arbeitsschritte im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="16c7e-119">**✓ DO** minimal work in the constructor.</span></span>

<span data-ttu-id="16c7e-120">Konstruktoren sollten nicht viel Arbeitsaufgaben ausführen, außer die Konstruktorparameter zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="16c7e-121">Die Kosten für jede andere Verarbeitung sollten verzögert werden, bis Sie erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="16c7e-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="16c7e-122">**✓ DO** Ausnahmen von Instanzkonstruktoren, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="16c7e-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="16c7e-123">"-" Wird explizit den öffentlichen Parameter losen Konstruktor in Klassen deklarieren, wenn ein solcher Konstruktor erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="16c7e-123">**✓ DO** explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="16c7e-124">Wenn Sie nicht explizit Konstruktoren für einen Typ deklarieren, fügen viele Sprachen (z C#. b.) automatisch einen öffentlichen Parameter losen Konstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="16c7e-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="16c7e-125">(Abstrakte Klassen erhalten einen geschützten Konstruktor.)</span><span class="sxs-lookup"><span data-stu-id="16c7e-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="16c7e-126">Durch das Hinzufügen eines parametrisierten Konstruktors zu einer Klasse wird verhindert, dass der Compiler den Parameter losen Konstruktor hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="16c7e-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="16c7e-127">Dies verursacht häufig versehentlich wichtige Änderungen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="16c7e-128">**X vermeiden** Sie das explizite Definieren von Parameter losen Konstruktoren für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-128">**X AVOID** explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="16c7e-129">Dadurch wird die Array Erstellung beschleunigt, denn wenn der Parameter lose Konstruktor nicht definiert ist, muss er nicht an jedem Slot im Array ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="16c7e-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="16c7e-130">Beachten Sie, dass viele Compiler, C#einschließlich, nicht zulassen, dass Strukturen aus diesem Grundparameter lose Konstruktoren aufweisen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="16c7e-131">**X AVOID** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="16c7e-132">Das Aufrufen eines virtuellen Members bewirkt, dass die am meisten abgeleitete außer Kraft Setzung aufgerufen wird, auch wenn der Konstruktor des am weitesten abgeleiteten Typs noch nicht vollständig ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="16c7e-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="16c7e-133">Typkonstruktorrichtlinien</span><span class="sxs-lookup"><span data-stu-id="16c7e-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="16c7e-134">**✓ DO** als statische Konstruktoren privat festlegen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-134">**✓ DO** make static constructors private.</span></span>

<span data-ttu-id="16c7e-135">Ein statischer Konstruktor, der auch als Klassenkonstruktor bezeichnet wird, wird verwendet, um einen Typ zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="16c7e-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="16c7e-136">Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erstellt wird oder statische Member dieses Typs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16c7e-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="16c7e-137">Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="16c7e-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="16c7e-138">Wenn ein statischer Konstruktor nicht privat ist, kann er von Code aufgerufen werden, der nicht die CLR ist.</span><span class="sxs-lookup"><span data-stu-id="16c7e-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="16c7e-139">Abhängig von den Vorgängen, die im Konstruktor ausgeführt werden, kann dies zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="16c7e-140">Der C# Compiler erzwingt, dass statische Konstruktoren privat sind.</span><span class="sxs-lookup"><span data-stu-id="16c7e-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="16c7e-141">**X DO NOT** lösen Ausnahmen aus statischen Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="16c7e-141">**X DO NOT** throw exceptions from static constructors.</span></span>

<span data-ttu-id="16c7e-142">Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, kann der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16c7e-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="16c7e-143">**✓ CONSIDER** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="16c7e-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="16c7e-144">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="16c7e-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="16c7e-145">*Neu gedruckt durch die Berechtigung von Pearson Education, Inc. [von Framework-Entwurfs Richtlinien: Konventionen, Idiome und Muster für wiederverwendbare .NET-Bibliotheken, 2. Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows-Entwicklungs Serie.*</span><span class="sxs-lookup"><span data-stu-id="16c7e-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="16c7e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c7e-146">See also</span></span>

- [<span data-ttu-id="16c7e-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="16c7e-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="16c7e-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="16c7e-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
