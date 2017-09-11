---
title: Strukturen und Klassen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c6874192a09db9ff5f247274247630d0bfa05ea3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="44af2-102">Strukturen und Klassen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44af2-102">Structures and Classes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="44af2-103">Die Syntax für Strukturen und Klassen, mit dem Ergebnis, dass größtenteils die gleichen Funktionen unterstützen vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="44af2-103"> unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="44af2-104">Es gibt jedoch auch wichtige Unterschiede zwischen Strukturen und Klassen.</span><span class="sxs-lookup"><span data-stu-id="44af2-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="44af2-105">Klassen haben den Vorteil, Verweistypen – Übergabe eines Verweises ist effizienter als die Übergabe einer Strukturvariablen mit allen zugehörigen Daten.</span><span class="sxs-lookup"><span data-stu-id="44af2-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="44af2-106">Auf der anderen Seite erfordern Strukturen keine Zuordnung von Arbeitsspeicher auf dem globalen Heap.</span><span class="sxs-lookup"><span data-stu-id="44af2-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="44af2-107">Da Sie von einer Struktur geerbt werden können, sollten Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="44af2-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="44af2-108">Verwenden Sie Strukturen, wenn das Objekt, das Sie erstellen möchten, hat eine Größe von kleinen Instanz und die Leistungsmerkmale von Klassen und Strukturen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="44af2-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="44af2-109">Ähnlichkeit</span><span class="sxs-lookup"><span data-stu-id="44af2-109">Similarities</span></span>  
 <span data-ttu-id="44af2-110">Strukturen und Klassen sind ähnlich wie in folgender Hinsicht:</span><span class="sxs-lookup"><span data-stu-id="44af2-110">Structures and classes are similar in the following respects:</span></span>  
  
-   <span data-ttu-id="44af2-111">Beide sind *Container* Typen, d. h., dass sie andere Typen als Member enthalten.</span><span class="sxs-lookup"><span data-stu-id="44af2-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
-   <span data-ttu-id="44af2-112">Beide verfügen über Member, die Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler enthalten können.</span><span class="sxs-lookup"><span data-stu-id="44af2-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="44af2-113">Verwechseln Sie jedoch nicht diese Member mit dem deklarierten *Elemente* einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="44af2-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
-   <span data-ttu-id="44af2-114">Die Member beider können Zugriffsebenen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="44af2-115">Beispielsweise kann ein Member deklariert werden `Public` und anderen `Private`.</span><span class="sxs-lookup"><span data-stu-id="44af2-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
-   <span data-ttu-id="44af2-116">Beide können Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="44af2-116">Both can implement interfaces.</span></span>  
  
-   <span data-ttu-id="44af2-117">Beide können freigegebene Konstruktoren mit oder ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="44af2-117">Both can have shared constructors, with or without parameters.</span></span>  
  
-   <span data-ttu-id="44af2-118">Beide verfügbar machen, können eine *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft nimmt mindestens einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="44af2-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
-   <span data-ttu-id="44af2-119">Beide können deklarieren und Auslösen von Ereignissen, und beide können Delegaten deklarieren.</span><span class="sxs-lookup"><span data-stu-id="44af2-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="44af2-120">Unterschiede</span><span class="sxs-lookup"><span data-stu-id="44af2-120">Differences</span></span>  
 <span data-ttu-id="44af2-121">Strukturen und Klassen unterscheiden sich in den folgenden Angaben:</span><span class="sxs-lookup"><span data-stu-id="44af2-121">Structures and classes differ in the following particulars:</span></span>  
  
-   <span data-ttu-id="44af2-122">Strukturen sind *Werttypen*; Klassen sind *Verweistypen*.</span><span class="sxs-lookup"><span data-stu-id="44af2-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="44af2-123">Eine Variable eines Strukturtyps enthält die Struktur Daten, anstatt mit einem Verweis auf die Daten als Typ einer Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="44af2-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
-   <span data-ttu-id="44af2-124">Strukturen verwenden stapelzuordnung. Klassen verwenden Heapzuweisung.</span><span class="sxs-lookup"><span data-stu-id="44af2-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
-   <span data-ttu-id="44af2-125">Alle Strukturelemente sind `Public` standardmäßig-Klasse Variablen und Konstanten sind `Private` , während andere Klassenmember sind standardmäßig `Public` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="44af2-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="44af2-126">Dieses Verhalten für Klassenmember bietet Kompatibilität mit dem Visual Basic 6.0-System Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="44af2-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
-   <span data-ttu-id="44af2-127">Eine Struktur müssen mindestens eine nicht freigegebene Variable oder weder freigegebenes noch benutzerdefiniertes Ereigniselement. eine Klasse kann völlig leer sein.</span><span class="sxs-lookup"><span data-stu-id="44af2-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
-   <span data-ttu-id="44af2-128">Strukturelemente nicht deklariert werden, als `Protected`; Klassenmember können.</span><span class="sxs-lookup"><span data-stu-id="44af2-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
-   <span data-ttu-id="44af2-129">Eine Strukturprozedur kann Ereignisse behandeln, nur, wenn es eine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Verfahren und nur von der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md); jede Klassenprozedur kann Ereignisse entweder behandeln die [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Schlüsselwort oder `AddHandler` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="44af2-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="44af2-130">Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="44af2-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
-   <span data-ttu-id="44af2-131">Struktur Variablendeklarationen können keine Initialisierer oder Anfangsgröße für Arrays angeben; Klasse Variablendeklarationen können.</span><span class="sxs-lookup"><span data-stu-id="44af2-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
-   <span data-ttu-id="44af2-132">Strukturen erben implizit von der <xref:System.ValueType?displayProperty=fullName>-Klasse und nicht von einem anderen Typ; erben Klassen können von einer Klasse oder einer anderen <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> Klassen erben</xref:System.ValueType?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="44af2-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=fullName> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
-   <span data-ttu-id="44af2-133">Strukturen können nicht vererbt werden; Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="44af2-133">Structures are not inheritable; classes are.</span></span>  
  
-   <span data-ttu-id="44af2-134">Strukturen werden nie beendet, sodass die common Language Runtime (CLR) aufgerufen werden, nie die <xref:System.Object.Finalize%2A>-Methode für eine Struktur; Klassen werden vom Garbage Collector (GC), der aufgerufen wird, beendet <xref:System.Object.Finalize%2A>für eine Klasse, wenn es erkennt keine aktiven Verweise mehr vorhanden sind.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A></span><span class="sxs-lookup"><span data-stu-id="44af2-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
-   <span data-ttu-id="44af2-135">Eine Struktur ist einen Konstruktor nicht erforderlich. eine Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="44af2-135">A structure does not require a constructor; a class does.</span></span>  
  
-   <span data-ttu-id="44af2-136">Strukturen können nicht freigegebene Konstruktoren nur, wenn sie Parameter annehmen; Klassen können sie mit oder ohne Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="44af2-137">Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="44af2-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="44af2-138">Dieser Konstruktor initialisiert alle die Datenmember der Struktur mit ihren Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="44af2-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="44af2-139">Sie können dieses Verhalten nicht neu definieren.</span><span class="sxs-lookup"><span data-stu-id="44af2-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="44af2-140">Instanzen und Variablen</span><span class="sxs-lookup"><span data-stu-id="44af2-140">Instances and Variables</span></span>  
 <span data-ttu-id="44af2-141">Da Strukturen Werttypen sind, wird Strukturvariablen permanent an eine einzelne Strukturinstanz gebunden.</span><span class="sxs-lookup"><span data-stu-id="44af2-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="44af2-142">Jedoch sind Klassen Verweistypen, und eine Objektvariable kann zu unterschiedlichen Zeitpunkten auf unterschiedliche Klasseninstanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="44af2-143">Dieser Unterschied wirkt sich auf folgende Weise auf die Verwendung von Strukturen und Klassen aus:</span><span class="sxs-lookup"><span data-stu-id="44af2-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
-   <span data-ttu-id="44af2-144">**Die Initialisierung.**</span><span class="sxs-lookup"><span data-stu-id="44af2-144">**Initialization.**</span></span> <span data-ttu-id="44af2-145">Eine Strukturvariable umfasst implizit eine Initialisierung der Elemente mithilfe des parameterlosen Konstruktors der Struktur.</span><span class="sxs-lookup"><span data-stu-id="44af2-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="44af2-146">Aus diesem Grund `Dim s As struct1` entspricht `Dim s As struct1 = New struct1()`.</span><span class="sxs-lookup"><span data-stu-id="44af2-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
-   <span data-ttu-id="44af2-147">**Zuweisen von Variablen.**</span><span class="sxs-lookup"><span data-stu-id="44af2-147">**Assigning Variables.**</span></span> <span data-ttu-id="44af2-148">Wenn Sie eine Strukturvariable zu einem anderen zuweisen oder eine Strukturinstanz an Prozedurarguments übergeben, werden die aktuellen Werte aller Variablenelemente in die neue Struktur kopiert.</span><span class="sxs-lookup"><span data-stu-id="44af2-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="44af2-149">Wenn Sie eine Objektvariable zu einem anderen zuweisen oder eine Objektvariable an eine Prozedur übergeben, wird nur der Verweiszeiger kopiert.</span><span class="sxs-lookup"><span data-stu-id="44af2-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
-   <span data-ttu-id="44af2-150">**Zuweisen von Nothing.**</span><span class="sxs-lookup"><span data-stu-id="44af2-150">**Assigning Nothing.**</span></span> <span data-ttu-id="44af2-151">Weisen Sie den Wert [nichts](../../../../visual-basic/language-reference/nothing.md) auf eine Struktur Variable, aber die Instanz weiterhin der Variablen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="44af2-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="44af2-152">Weiterhin können Sie ihre Methoden aufrufen und die Datenelemente zugreifen, obwohl die Variablenelemente durch die Zuweisung erneut initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="44af2-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="44af2-153">Im Gegensatz dazu, wenn Sie eine Objektvariablen auf `Nothing`, heben Sie die Zuweisung von allen Klasseninstanzen und Sie können nicht auf Member über die Variable zugreifen, bis Sie eine andere Instanz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
-   <span data-ttu-id="44af2-154">**Mehrere Instanzen.**</span><span class="sxs-lookup"><span data-stu-id="44af2-154">**Multiple Instances.**</span></span> <span data-ttu-id="44af2-155">Eine Objektvariablen kann verschiedene Klasseninstanzen zu unterschiedlichen Zeiten zugewiesen, und verschiedene Objektvariablen können gleichzeitig auf die gleiche Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="44af2-156">Vorgenommenen Änderungen auf die Werte von Klassenmembern Einfluss auf die Elemente, die beim Zugriff über eine andere Variable, die auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="44af2-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="44af2-157">Strukturelemente sind hingegen in ihrer eigenen Instanz isoliert.</span><span class="sxs-lookup"><span data-stu-id="44af2-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="44af2-158">Ändert die Werte werden nicht widergespiegelt, in anderen Strukturvariablen, auch in anderen Instanzen des gleichen `Structure` Deklaration.</span><span class="sxs-lookup"><span data-stu-id="44af2-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
-   <span data-ttu-id="44af2-159">**Gleichheit.**</span><span class="sxs-lookup"><span data-stu-id="44af2-159">**Equality.**</span></span> <span data-ttu-id="44af2-160">Gleichheitstest zwei Strukturen muss für ein Element für Element durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="44af2-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="44af2-161">Zwei Objektvariablen können verglichen werden, mithilfe der <xref:System.Object.Equals%2A>-Methode.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="44af2-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="44af2-162"><xref:System.Object.Equals%2A>Gibt an, ob die zwei Variablen auf dieselbe Instanz verweisen.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="44af2-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44af2-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44af2-163">See Also</span></span>  
 <span data-ttu-id="44af2-164">[Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-164">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="44af2-165"> [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-165"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="44af2-166"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-166"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="44af2-167"> [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-167"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="44af2-168"> [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-168"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="44af2-169"> [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span><span class="sxs-lookup"><span data-stu-id="44af2-169"> [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span></span>  
<span data-ttu-id="44af2-170"> [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="44af2-170"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>
