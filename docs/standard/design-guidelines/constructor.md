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
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: b140be34d9359cfdca1250a924db787563127d19
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127783"
---
# <a name="constructor-design"></a><span data-ttu-id="3b81e-102">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="3b81e-102">Constructor Design</span></span>
<span data-ttu-id="3b81e-103">Es gibt zwei Arten von Konstruktoren: Geben Sie die Konstruktoren und Instanz.</span><span class="sxs-lookup"><span data-stu-id="3b81e-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="3b81e-104">Typkonstruktoren sind statisch und von der CLR ausgeführt werden, bevor der Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b81e-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="3b81e-105">Instanzkonstruktoren wird ausgeführt, wenn eine Instanz eines Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b81e-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="3b81e-106">Typen können keine Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="3b81e-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="3b81e-107">Instanzkonstruktoren können.</span><span class="sxs-lookup"><span data-stu-id="3b81e-107">Instance constructors can.</span></span> <span data-ttu-id="3b81e-108">Instanzkonstruktoren, die Parameter annehmen, nicht werden standardmäßige Konstruktoren häufig bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="3b81e-109">Konstruktoren sind die beste Möglichkeit zum Erstellen von Instanzen eines Typs.</span><span class="sxs-lookup"><span data-stu-id="3b81e-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="3b81e-110">Die meisten Entwickler durchsucht und versuchen, einen Konstruktor zu verwenden, bevor sie alternative Methoden zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="3b81e-111">**✓ CONSIDER** einfach, im Idealfall Standard, Konstruktoren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="3b81e-112">Eine sehr kleine Anzahl von Parametern über einen einfachen Konstruktor verfügt, und alle Parameter sind primitive oder Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="3b81e-113">Diese einfache Konstruktoren erhöhen Nutzbarkeit des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="3b81e-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="3b81e-114">**✓ CONSIDER** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.</span><span class="sxs-lookup"><span data-stu-id="3b81e-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="3b81e-115">**✓ DO** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="3b81e-116">Es muss kein Unterschied in der Semantik zwischen mit dem leeren Konstruktor gefolgt von einigen Eigenschaftensätze und über einen Konstruktor mit mehreren Argumenten.</span><span class="sxs-lookup"><span data-stu-id="3b81e-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="3b81e-117">**✓ DO** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3b81e-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="3b81e-118">Der einzige Unterschied zwischen Eigenschaften und solche Parameter muss Groß-/Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="3b81e-119">**✓ DO** nur minimale Arbeitsschritte im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3b81e-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="3b81e-120">Konstruktoren tun nicht viel Arbeit als Capture Parameter des Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="3b81e-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="3b81e-121">Die Kosten für weitere Verarbeitungsschritte muss verzögert werden, bis erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3b81e-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="3b81e-122">**✓ DO** Ausnahmen von Instanzkonstruktoren, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="3b81e-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="3b81e-123">**✓ DO** in Klassen, die öffentlichen Standardkonstruktor explizit deklariert werden, wenn ein solcher Konstruktor erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3b81e-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="3b81e-124">Wenn Sie für einen Typ explizit keine Konstruktoren deklarieren nicht, werden viele Sprachen (z. B. C# -Referenz) automatisch einen öffentlichen Standardkonstruktor hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3b81e-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="3b81e-125">(Abstrakte Klassen erhalten einen geschützten Konstruktor.)</span><span class="sxs-lookup"><span data-stu-id="3b81e-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="3b81e-126">Eine Klasse einen parametrisierten Konstruktor hinzugefügt wird verhindert, dass den Compiler die standardmäßigen Konstruktor hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="3b81e-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="3b81e-127">Dies führt häufig zu versehentlichen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="3b81e-128">**X AVOID** explizit standardmäßige Konstruktoren für Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="3b81e-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="3b81e-129">Dadurch Arrayerstellung schneller, da der Standardkonstruktor nicht definiert ist, es nicht unbedingt auf alle Slot im Array ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="3b81e-130">Beachten Sie, dass viele Compiler, u. a. c#, Strukturen, die aus diesem Grund parameterlose Konstruktoren besitzen nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="3b81e-131">**X AVOID** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="3b81e-132">Aufrufen eines virtuellen Members bewirkt die am stärksten abgeleitete Außerkraftsetzung aufgerufen wird, selbst wenn der Konstruktor, der am weitesten abgeleiteten Typ noch vollständig nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3b81e-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="3b81e-133">Richtlinien für die Typen-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="3b81e-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="3b81e-134">**✓ DO** als statische Konstruktoren privat festlegen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="3b81e-135">Ein statischer Konstruktor auch einen Klassenkonstruktor, genannt wird verwendet, um einen Typ zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3b81e-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="3b81e-136">Die CLR ruft den statischen Konstruktor aus, bevor die erste Instanz des Typs erstellt oder auf irgendwelche statischen Member für diesen Typ aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="3b81e-137">Der Benutzer hat keine Kontrolle darüber, wenn der statische Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3b81e-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="3b81e-138">Wenn ein statischer Konstruktor nicht privat ist, kann es durch anderen Code als die CLR aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="3b81e-139">Je nach den Operationen, die im Konstruktor ausgeführt wird kann dies unerwartetes Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="3b81e-140">Der C#-Compiler erzwingt, dass statische Konstruktoren privat sein.</span><span class="sxs-lookup"><span data-stu-id="3b81e-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="3b81e-141">**X DO NOT** lösen Ausnahmen aus statischen Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="3b81e-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="3b81e-142">Wenn von einem Typkonstruktor eine Ausnahme ausgelöst wird, ist der Typ in der aktuellen Anwendungsdomäne nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b81e-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="3b81e-143">**✓ CONSIDER** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="3b81e-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="3b81e-144">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3b81e-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3b81e-145">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="3b81e-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b81e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b81e-146">See also</span></span>

- [<span data-ttu-id="3b81e-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="3b81e-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="3b81e-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3b81e-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
