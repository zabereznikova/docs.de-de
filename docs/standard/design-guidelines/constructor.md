---
title: Konstruktorentwurf
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575556"
---
# <a name="constructor-design"></a><span data-ttu-id="a282c-102">Konstruktorentwurf</span><span class="sxs-lookup"><span data-stu-id="a282c-102">Constructor Design</span></span>
<span data-ttu-id="a282c-103">Es gibt zwei Arten von Konstruktoren: Geben Sie die Konstruktoren und Instanz.</span><span class="sxs-lookup"><span data-stu-id="a282c-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="a282c-104">Typkonstruktoren sind statisch und werden von der CLR ausgeführt, bevor der Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a282c-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="a282c-105">Instanzkonstruktoren wird ausgeführt, wenn eine Instanz eines Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a282c-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="a282c-106">Typkonstruktoren können keine Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="a282c-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="a282c-107">Instanzkonstruktoren können.</span><span class="sxs-lookup"><span data-stu-id="a282c-107">Instance constructors can.</span></span> <span data-ttu-id="a282c-108">Instanzkonstruktoren, die keine Parameter werden häufig Standardkonstruktoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a282c-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="a282c-109">Konstruktoren sind die meisten natürliche Möglichkeit zum Erstellen von Instanzen eines Typs.</span><span class="sxs-lookup"><span data-stu-id="a282c-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="a282c-110">Die meisten Entwickler suchen und versuchen, einen Konstruktor verwenden, bevor sie alternative Methoden zum Erstellen von Instanzen (z. B. Factorymethoden) in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="a282c-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="a282c-111">**✓ GGF.** einfach, im Idealfall Standard, Konstruktoren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a282c-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="a282c-112">Ein einfache Konstruktor hat eine sehr kleine Anzahl von Parametern, und alle Parameter sind primitive Typen oder Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="a282c-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="a282c-113">Diese einfache Konstruktoren Verwendbarkeit des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a282c-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="a282c-114">**✓ GGF.** eine statische Factorymethode statt einen Konstruktor verwenden, wenn die Semantik des gewünschten Vorgangs nicht direkt der Erstellung einer neuen Instanz zugeordnet sind, oder der Konstruktor Entwurfsrichtlinien unnatürlichen idealer.</span><span class="sxs-lookup"><span data-stu-id="a282c-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="a282c-115">**Führen Sie ✓** Konstruktorparameter als Tastenkombinationen verwenden, für die wichtigsten Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="a282c-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="a282c-116">Es darf kein Unterschied in der Semantik zwischen mit dem leeren Konstruktor gefolgt von einigen Eigenschaftensätze und mit einem Konstruktor mit mehreren Argumenten.</span><span class="sxs-lookup"><span data-stu-id="a282c-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="a282c-117">**Führen Sie ✓** verwenden Sie denselben Namen für Konstruktorparameter und eine Eigenschaft aus, wenn der Konstruktorparameter verwendet werden, einfach die Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a282c-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="a282c-118">Der einzige Unterschied zwischen Eigenschaften und solche Parameter sollten Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="a282c-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="a282c-119">**Führen Sie ✓** nur minimale Arbeitsschritte im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a282c-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="a282c-120">Konstruktoren tun nicht viel Arbeit als Capture die Konstruktorparametern.</span><span class="sxs-lookup"><span data-stu-id="a282c-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="a282c-121">Die Kosten für weitere Verarbeitungsschritte sollten verzögert werden, bis die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a282c-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="a282c-122">**Führen Sie ✓** Ausnahmen von Instanzkonstruktoren, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="a282c-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="a282c-123">**Führen Sie ✓** in Klassen, die öffentlichen Standardkonstruktor explizit deklariert werden, wenn ein solcher Konstruktor erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a282c-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="a282c-124">Wenn Sie keine Konstruktoren explizit auf einen Typ deklarieren nicht, werden viele Sprachen (z. B. c#) einen öffentlichen Standardkonstruktor automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a282c-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="a282c-125">(Abstrakte Klassen get einen geschützten Konstruktor.)</span><span class="sxs-lookup"><span data-stu-id="a282c-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="a282c-126">Eine Klasse einen parametrisierten Konstruktor hinzugefügt wird verhindert, dass den Compiler den Standardkonstruktor hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a282c-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="a282c-127">Dadurch wird häufig eine versehentliche Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a282c-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="a282c-128">**X vermeiden** explizit standardmäßige Konstruktoren für Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="a282c-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="a282c-129">Dadurch Arrayerstellung schneller, da der Standardkonstruktor nicht definiert ist, nicht enthalten ist jeder Steckplatz im Array ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a282c-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="a282c-130">Beachten Sie, dass Strukturen parameterlose Konstruktoren aus diesem Grund haben viele Compiler, z. B. c#, nicht.</span><span class="sxs-lookup"><span data-stu-id="a282c-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="a282c-131">**X vermeiden** virtuelle Member für ein Objekt in seinem Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a282c-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="a282c-132">Aufrufen eines virtuellen Members bewirkt die am stärksten abgeleitete Außerkraftsetzung, die aufgerufen wird, auch wenn Sie der Konstruktor des am weitesten abgeleiteten Typ noch vollständig nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a282c-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="a282c-133">Richtlinien-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="a282c-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="a282c-134">**Führen Sie ✓** als statische Konstruktoren privat festlegen.</span><span class="sxs-lookup"><span data-stu-id="a282c-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="a282c-135">Ein statischer Konstruktor, der einen Klassenkonstruktor, so genannte wird verwendet, Initialisierung eines Typs.</span><span class="sxs-lookup"><span data-stu-id="a282c-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="a282c-136">Die CLR ruft den statischen Konstruktor auf, bevor die erste Instanz des Typs erzeugt wird bzw. irgendwelche statischen Member für diesen Typ aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a282c-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="a282c-137">Der Benutzer hat keine Kontrolle darüber, wann der statische Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a282c-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="a282c-138">Wenn ein statischer Konstruktor nicht privat ist, kann er von anderen Codes als die CLR aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a282c-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="a282c-139">Je nach den Operationen, die im Konstruktor ausgeführt wird kann dies unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="a282c-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="a282c-140">Der C#-Compiler erzwingt, dass statische Konstruktoren privat sein.</span><span class="sxs-lookup"><span data-stu-id="a282c-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="a282c-141">**X nicht** lösen Ausnahmen aus statischen Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="a282c-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="a282c-142">Wenn eine Ausnahme aus eines Konstruktors eines Typs ausgelöst wird, ist der Typ nicht in der aktuellen Anwendungsdomäne verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a282c-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="a282c-143">**✓ GGF.** statische Felder von Inline initialisieren, anstatt explizit statische Konstruktoren zu verwenden, da die Common Language Runtime ist in der Lage, zur Optimierung der Leistung von Typen, die nicht über einen explizit definierten statischen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="a282c-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="a282c-144">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="a282c-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a282c-145">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="a282c-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a282c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a282c-146">See Also</span></span>  
 [<span data-ttu-id="a282c-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="a282c-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="a282c-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a282c-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
