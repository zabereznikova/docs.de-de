---
title: Neues in C# 6 – C#-Leitfaden
description: Neues zu den neuen Features in Version 6 von C#
keywords: .NET, .NET Core
author: BillWagner
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: ea54e9a05120134eea8e1bc9d82302a7513b43e7
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="31820-104">Neues in C# 6</span><span class="sxs-lookup"><span data-stu-id="31820-104">What's New in C# 6</span></span>

<span data-ttu-id="31820-105">Die Version 6.0 von C# enthält zahlreiche Features, die die Produktivität für Entwickler verbessern.</span><span class="sxs-lookup"><span data-stu-id="31820-105">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="31820-106">Features in dieser Version sind:</span><span class="sxs-lookup"><span data-stu-id="31820-106">Features in this release include:</span></span>

* <span data-ttu-id="31820-107">[Schreibgeschützte Auto-Eigenschaften](#read-only-auto-properties):</span><span class="sxs-lookup"><span data-stu-id="31820-107">[Read-only Auto-properties](#read-only-auto-properties):</span></span>
    - <span data-ttu-id="31820-108">Sie können schreibgeschützte automatische Eigenschaften erstellen, die nur in Konstruktoren festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="31820-108">You can create read-only auto-properties that can be set only in constructors.</span></span>
* <span data-ttu-id="31820-109">[Auto-Eigenschaft-Initialisierer](#auto-property-initializers):</span><span class="sxs-lookup"><span data-stu-id="31820-109">[Auto-Property Initializers](#auto-property-initializers):</span></span>
    - <span data-ttu-id="31820-110">Sie können Initialisierungsausdrücke zum Festlegen des Anfangswerts einer Auto-Eigenschaft schreiben.</span><span class="sxs-lookup"><span data-stu-id="31820-110">You can write initialization expressions to set the initial value of an auto-property.</span></span>
* <span data-ttu-id="31820-111">[Ausdruckskörper-Funktionsmember](#expression-bodied-function-members):</span><span class="sxs-lookup"><span data-stu-id="31820-111">[Expression-bodied function members](#expression-bodied-function-members):</span></span>
    - <span data-ttu-id="31820-112">Sie können einzeilige Methoden mithilfe von Lambdaausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="31820-112">You can author one-line methods using lambda expressions.</span></span>
* <span data-ttu-id="31820-113">[verwendet statische](#using-static):</span><span class="sxs-lookup"><span data-stu-id="31820-113">[using static](#using-static):</span></span>
    - <span data-ttu-id="31820-114">Sie können alle Methoden einer einzelnen Klasse in den aktuellen Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="31820-114">You can import all the methods of a single class into the current namespace.</span></span>
* <span data-ttu-id="31820-115">[Bedingte NULL-Operatoren](#null-conditional-operators):</span><span class="sxs-lookup"><span data-stu-id="31820-115">[Null - conditional operators](#null-conditional-operators):</span></span>
    - <span data-ttu-id="31820-116">Sie können präzise und sicher auf Member eines Objekts zugreifen, während Sie noch nach NULL mit dem bedingten NULL-Operator suchen.</span><span class="sxs-lookup"><span data-stu-id="31820-116">You can concisely and safely access members of an object while still checking for null with the null conditional operator.</span></span>
* <span data-ttu-id="31820-117">[Zeichenfolgeninterpolierung](#string-interpolation):</span><span class="sxs-lookup"><span data-stu-id="31820-117">[String Interpolation](#string-interpolation):</span></span>
    - <span data-ttu-id="31820-118">Sie können die Zeichenfolgenformatierungsausdrücke mithilfe von Inlineausdrücken anstatt mit positionellen Argumenten schreiben.</span><span class="sxs-lookup"><span data-stu-id="31820-118">You can write string formatting expressions using inline expressions instead of positional arguments.</span></span>
* <span data-ttu-id="31820-119">[Ausnahmefilter](#exception-filters):</span><span class="sxs-lookup"><span data-stu-id="31820-119">[Exception filters](#exception-filters):</span></span>
    - <span data-ttu-id="31820-120">Sie können Ausdrücke basierend auf den Eigenschaften der Ausnahme oder basierend auf anderen Programmstatus abfangen.</span><span class="sxs-lookup"><span data-stu-id="31820-120">You can catch expressions based on properties of the exception or other program state.</span></span> 
* <span data-ttu-id="31820-121">[„nameof“-Ausdrücke](#nameof-expressions):</span><span class="sxs-lookup"><span data-stu-id="31820-121">[nameof Expressions](#nameof-expressions):</span></span>
    - <span data-ttu-id="31820-122">Sie können den Compiler Zeichenfolgendarstellungen von Symbolen generieren lassen.</span><span class="sxs-lookup"><span data-stu-id="31820-122">You can let the compiler generate string representations of symbols.</span></span>
* <span data-ttu-id="31820-123">[„Await“ in Catch- und Finally-Blöcken](#await-in-catch-and-finally-blocks)</span><span class="sxs-lookup"><span data-stu-id="31820-123">[await in catch and finally blocks](#await-in-catch-and-finally-blocks):</span></span>
    - <span data-ttu-id="31820-124">Sie können `await`-Ausdrücke an Orten verwenden, die diese zuvor als unzulässig deklariert haben.</span><span class="sxs-lookup"><span data-stu-id="31820-124">You can use `await` expressions in locations that previously disallowed them.</span></span>
* <span data-ttu-id="31820-125">[Indexinitialisierer](#index-initializers)</span><span class="sxs-lookup"><span data-stu-id="31820-125">[index initializers](#index-initializers):</span></span>
    - <span data-ttu-id="31820-126">Sie können Initialisierungsausdrücke für assoziative Container sowie Sequenzcontainer erstellen.</span><span class="sxs-lookup"><span data-stu-id="31820-126">You can author initialization expressions for associative containers as well as sequence containers.</span></span>
* <span data-ttu-id="31820-127">[Erweiterungsmethoden für Auflistungsinitialisierer](#extension-add-methods-in-collection-initializers):</span><span class="sxs-lookup"><span data-stu-id="31820-127">[Extension methods for collection initializers](#extension-add-methods-in-collection-initializers):</span></span>
    - <span data-ttu-id="31820-128">Auflistungsinitialisierer können neben Membermethoden zugängliche Erweiterungsmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-128">Collection initializers can rely on accessible extension methods, in addition to member methods.</span></span>
* <span data-ttu-id="31820-129">[Verbesserte Überladungsauflösung](#improved-overload-resolution):</span><span class="sxs-lookup"><span data-stu-id="31820-129">[Improved overload resolution](#improved-overload-resolution):</span></span>
    - <span data-ttu-id="31820-130">Einige Konstrukte, die zuvor mehrdeutige Methodenaufrufe generiert haben, werden nun korrekt aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="31820-130">Some constructs that previously generated ambiguous method calls now resolve correctly.</span></span>

<span data-ttu-id="31820-131">Der Gesamteffekt dieser Features ist es, dass Sie präziseren Code schreiben, der zudem lesbarer ist.</span><span class="sxs-lookup"><span data-stu-id="31820-131">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="31820-132">Die Syntax benötigt weniger Aufwand für viele allgemeine Methoden.</span><span class="sxs-lookup"><span data-stu-id="31820-132">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="31820-133">Es ist einfacher, die Entwurfsabsicht mit weniger Aufwand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31820-133">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="31820-134">Lernen Sie diese Features gut, und Sie können produktiver sein, mehr lesbaren Code schreiben und sich vermehrt auf Ihre Codefeatures konzentrieren, anstatt auf die Konstrukte der Sprache.</span><span class="sxs-lookup"><span data-stu-id="31820-134">Learn these features well, and you'll be more productive, write more readable code, and concentrate more on your core features than on the constructs of the language.</span></span>

<span data-ttu-id="31820-135">Im weiteren Verlauf dieses Themas werden die einzelnen Features detailliert erklärt.</span><span class="sxs-lookup"><span data-stu-id="31820-135">The remainder of this topic provides details on each of these features.</span></span>

## <a name="auto-property-enhancements"></a><span data-ttu-id="31820-136">Verbesserungen der Auto-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="31820-136">Auto-Property enhancements</span></span> 

<span data-ttu-id="31820-137">Die Syntax für automatisch implementierte Eigenschaften (in der Regel als „Auto-Eigenschaften“ bezeichnet) hat es stark vereinfacht, Eigenschaften zu erstellen, die einfache Get- und Set-Accessoren hatten.</span><span class="sxs-lookup"><span data-stu-id="31820-137">The syntax for automatically implemented properties (usually referred to as 'auto-properties') made it very easy to create properties that had simple get and set accessors:</span></span>

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

<span data-ttu-id="31820-138">Diese einfache Syntax beschränkte die Arten der Entwürfe, die Sie mithilfe von Auto-Eigenschaften unterstützen konnten.</span><span class="sxs-lookup"><span data-stu-id="31820-138">However, this simple syntax limited the kinds of designs you could support using auto-properties.</span></span> <span data-ttu-id="31820-139">C# 6 verbessert die Funktionen der Auto-Eigenschaften, damit Sie sie in mehr Szenarios verwenden können.</span><span class="sxs-lookup"><span data-stu-id="31820-139">C# 6 improves the auto-properties capabilities so that you can use them in more scenarios.</span></span> <span data-ttu-id="31820-140">Sie müssen nicht so oft auf die ausführlichere Syntax zum Deklarieren und Bearbeiten des Unterstützungsfeld von Hand zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="31820-140">You won't need to fall back on the more verbose syntax of declaring and manipulating the backing field by hand so often.</span></span>

<span data-ttu-id="31820-141">Die neue Syntax eignet sich in Szenarios für schreibgeschützte Eigenschaften sowie jene zum Initialisieren des Speichers der Variable hinter einer Auto-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="31820-141">The new syntax addresses scenarios for read-only properties, and for initializing the variable storage behind an auto-property.</span></span>

### <a name="read-only-auto-properties"></a><span data-ttu-id="31820-142">Schreibgeschützte Auto-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="31820-142">Read-only auto-properties</span></span>

<span data-ttu-id="31820-143">*Schreibgeschützte Auto-Eigenschaften* ermöglichen eine präzisere Syntax um unveränderliche Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="31820-143">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="31820-144">Sie kamen in früheren Versionen von C# am ehesten an unveränderlichen Typen heran, wenn Sie private Setter deklariert haben.</span><span class="sxs-lookup"><span data-stu-id="31820-144">The closest you could get to immutable types in earlier versions of C# was to declare private setters:</span></span>

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
<span data-ttu-id="31820-145">Mit dieser Syntax stellt der Compiler nicht sicher, dass der Typ tatsächlich unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31820-145">Using this syntax, the compiler doesn't ensure that the type really is immutable.</span></span> <span data-ttu-id="31820-146">Sie erzwingt nur, dass die Eigenschaften `FirstName` und `LastName` nicht von Codes außerhalb der Klasse bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="31820-146">It only enforces that the `FirstName` and `LastName` properties are not modified from any code outside the class.</span></span>

<span data-ttu-id="31820-147">Schreibgeschützte Auto-Eigenschaften lassen wahres schreibgeschütztes Verhalten zu.</span><span class="sxs-lookup"><span data-stu-id="31820-147">Read-only auto-properties enable true read-only behavior.</span></span> <span data-ttu-id="31820-148">Sie deklarieren die Auto-Eigenschaft nur mit einem Get-Accessor:</span><span class="sxs-lookup"><span data-stu-id="31820-148">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="31820-149">Die `FirstName`- und `LastName`-Eigenschaften können nur im Text eines Konstruktors festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="31820-149">The `FirstName` and `LastName` properties can be set only in the body of a constructor:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="31820-150">Wenn Sie versuchen, `LastName` in einer anderen Methode festzulegen, wird ein `CS0200`-Kompilierungsfehler erzeugt:</span><span class="sxs-lookup"><span data-stu-id="31820-150">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="31820-151">Diese Feature ermöglicht wahrhaftige Sprachenunterstützung zum Erstellen unveränderlicher Typen und zum Verwenden der präziseren und einfacheren Auto-Eigenschaft-Syntax</span><span class="sxs-lookup"><span data-stu-id="31820-151">This feature enables true language support for creating immutable types and using the more concise and convenient auto-property syntax.</span></span>

### <a name="auto-property-initializers"></a><span data-ttu-id="31820-152">Auto-Eigenschaft-Initialisierer</span><span class="sxs-lookup"><span data-stu-id="31820-152">Auto-Property Initializers</span></span>

<span data-ttu-id="31820-153">Mit *Auto-Eigenschaft-Initialisierer* können Sie den ursprünglichen Wert für eine Auto-Eigenschaft als Teil der Eigenschaftendeklaration deklarieren.</span><span class="sxs-lookup"><span data-stu-id="31820-153">*Auto-Property Initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>  <span data-ttu-id="31820-154">In früheren Versionen mussten diese Eigenschaften über Setter verfügen und Sie müssten diesen Setter verwenden, um den vom Unterstützungsfeld verwendeten Datenspeicher zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="31820-154">In earlier versions, these properties would need to have setters and you would need to use that setter to initialize the data storage used by the backing field.</span></span> <span data-ttu-id="31820-155">Betrachten Sie diese Klasse als für einen Studenten, die den Namen sowie eine Liste der Noten des Studenten enthält:</span><span class="sxs-lookup"><span data-stu-id="31820-155">Consider this class for a student that contains the name and a list of the student's grades:</span></span>

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
<span data-ttu-id="31820-156">Mit zunehmender Größe der Klasse, können Sie andere Konstruktoren einschließen.</span><span class="sxs-lookup"><span data-stu-id="31820-156">As this class grows, you may include other constructors.</span></span> <span data-ttu-id="31820-157">Jeder Konstruktor muss dieses Feld initialisieren, andernfalls werden Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="31820-157">Each constructor needs to initialize this field, or you'll introduce errors.</span></span>

<span data-ttu-id="31820-158">Mit C# 6 können Sie einen Anfangswert für den von einer Auto-Eigenschaft verwendeten Speicher in der Auto-Eigenschaft-Deklaration zuweisen:</span><span class="sxs-lookup"><span data-stu-id="31820-158">C# 6 enables you to assign an initial value for the storage used by an auto-property in the auto-property declaration:</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="31820-159">Der `Grades`-Member wird initialisiert, wo er deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="31820-159">The `Grades` member is initialized where it is declared.</span></span> <span data-ttu-id="31820-160">Dies erleichtert die einmalige Ausführung der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="31820-160">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="31820-161">Die Initialisierung ist Teil der Eigenschaftendeklaration, was es einfacher macht, die Speicherzuweisung mit der öffentlichen Schnittstelle für `Student`-Objekte gleichzustellen.</span><span class="sxs-lookup"><span data-stu-id="31820-161">The initialization is part of the property declaration, making it easier to equate the storage allocation with public interface for `Student` objects.</span></span>

<span data-ttu-id="31820-162">Eigenschafteninitialisierer können wie im Folgenden dargestellt mit Lese-/Schreibeigenschaften sowie mit schreibgeschützten Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31820-162">Property Initializers can be used with read/write properties as well as read-only properties, as shown here.</span></span>

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a><span data-ttu-id="31820-163">Ausdruckskörper-Funktionsmember</span><span class="sxs-lookup"><span data-stu-id="31820-163">Expression-bodied function members</span></span>

<span data-ttu-id="31820-164">Der Text von vielen Member, die wir schreiben, besteht aus nur einer Anweisung, die als Ausdruck dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31820-164">The body of a lot of members that we write consist of only one statement that can be represented as an expression.</span></span> <span data-ttu-id="31820-165">Sie können diese Syntax reduzieren, indem Sie stattdessen einen Ausdruckskörpermember schreiben.</span><span class="sxs-lookup"><span data-stu-id="31820-165">You can reduce that syntax by writing an expression-bodied member instead.</span></span> <span data-ttu-id="31820-166">Dies funktioniert für Methoden und schreibgeschützte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="31820-166">It works for methods and read-only properties.</span></span> <span data-ttu-id="31820-167">Das Außerkraftsetzen von `ToString()` ist z.B. oft eine gute Wahl:</span><span class="sxs-lookup"><span data-stu-id="31820-167">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="31820-168">Sie können auch Ausdruckskörpermember in schreibgeschützten Eigenschaften verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-168">You can also use expression-bodied members in read-only properties as well:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a><span data-ttu-id="31820-169">verwendet statische</span><span class="sxs-lookup"><span data-stu-id="31820-169">using static</span></span>

<span data-ttu-id="31820-170">Die Erweiterung *verwendet statische* erlaubt Ihnen das Importieren der statischen Methoden einer einzelnen Klasse.</span><span class="sxs-lookup"><span data-stu-id="31820-170">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="31820-171">Zuvor hat die `using`-Anweisungen alle Typen in einen Namespace importiert.</span><span class="sxs-lookup"><span data-stu-id="31820-171">Previously, the `using` statement imported all types in a namespace.</span></span> 

<span data-ttu-id="31820-172">Häufig verwenden wir die statischen Methoden einer Klasse für unseren Code.</span><span class="sxs-lookup"><span data-stu-id="31820-172">Often we use a class' static methods throughout our code.</span></span> <span data-ttu-id="31820-173">Das wiederholte Eingeben des Klassennamens kann die Bedeutung Ihres Codes verschleiern.</span><span class="sxs-lookup"><span data-stu-id="31820-173">Repeatedly typing the class name can obscure the meaning of your code.</span></span> <span data-ttu-id="31820-174">Ein häufig verwendetes Beispiel ist, wenn Sie Klassen schreiben, die viele numerische Berechnungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="31820-174">A common example is when you write classes that perform many numeric calculations.</span></span>
<span data-ttu-id="31820-175">Ihr Code wird mit <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> und anderen Aufrufen von unterschiedlichen Methoden in der <xref:System.Math>-Klasse überhäuft.</span><span class="sxs-lookup"><span data-stu-id="31820-175">Your code will be littered with <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> and other calls to different methods in the <xref:System.Math> class.</span></span> <span data-ttu-id="31820-176">Durch die neue `using static`-Syntax können die Klassen viel besser gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="31820-176">The new `using static` syntax can make these classes much cleaner to read.</span></span> <span data-ttu-id="31820-177">Sie geben die von Ihnen verwendete Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="31820-177">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="31820-178">Nun können Sie beliebige statische Methoden in der <xref:System.Math>-Klasse verwenden, ohne die <xref:System.Math>-Klasse zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="31820-178">And now, you can use any static method in the <xref:System.Math> class without qualifying the <xref:System.Math> class.</span></span> <span data-ttu-id="31820-179">Die <xref:System.Math>-Klasse ist ein hervorragender Anwendungsfall für dieses Feature, da keine Instanzenmethoden enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="31820-179">The <xref:System.Math> class is a great use case for this feature because it does not contain any instance methods.</span></span> <span data-ttu-id="31820-180">Sie können auch `using static` zum Importieren von statischen Methoden einer Klasse für eine Klasse verwenden, die jeweils über statische Methoden und Instanzenmethoden verfügt.</span><span class="sxs-lookup"><span data-stu-id="31820-180">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="31820-181">Eines der nützlichsten Beispiele ist <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="31820-181">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="31820-182">Sie müssen den vollqualifizierten Klassennamen `System.String` in einer statischen using-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-182">You must use the fully qualified class name, `System.String` in a static using statement.</span></span> <span data-ttu-id="31820-183">Sie können das `string`-Schlüsselwort nicht stattdessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-183">You cannot use the `string` keyword instead.</span></span> 

<span data-ttu-id="31820-184">Sie können nun statische Methoden aufrufen, die in der <xref:System.String>-Klasse definiert sind, ohne diese Methoden als Member der Klasse zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="31820-184">You can now call static methods defined in the <xref:System.String> class without qualifying those methods as members of that class:</span></span>

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

<span data-ttu-id="31820-185">Die `static using`-Funktionen und Erweiterungsmethoden interagieren auf interessante Weise, und der Sprachentwurf erhielt einige Regeln, die besonders diese Interaktionen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="31820-185">The `static using` feature and extension methods interact in interesting ways, and the language design included some rules that specifically address those interactions.</span></span> <span data-ttu-id="31820-186">Das Ziel ist, die Risiken von beeinträchtigenden Änderungen in vorhandenen Codebasen – einschließlich der Ihren – zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="31820-186">The goal is to minimize any chances of breaking changes in existing codebases, including yours.</span></span>

<span data-ttu-id="31820-187">Erweiterungsmethoden befinden sich nur bei Aufruf mithilfe der Aufrufsyntax der Erweiterungsmethode im Gültigkeitsbereich und nicht, wenn sie als statische Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31820-187">Extension methods are only in scope when called using the extension method invocation syntax, not when called as a static method.</span></span>
<span data-ttu-id="31820-188">Sie sehen dies oft in LINQ-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="31820-188">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="31820-189">Sie können das LINQ-Muster importieren, indem Sie <xref:System.Linq.Enumerable> importieren.</span><span class="sxs-lookup"><span data-stu-id="31820-189">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="31820-190">Daraufhin werden alle Methoden in der <xref:System.Linq.Enumerable>-Klasse importiert.</span><span class="sxs-lookup"><span data-stu-id="31820-190">This imports all the methods in the <xref:System.Linq.Enumerable> class.</span></span>
<span data-ttu-id="31820-191">Allerdings befinden sich Erweiterungsmethoden nur im Gültigkeitsbereich, wenn sie als Erweiterungsmethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31820-191">However, the extension methods are only in scope when called as extension methods.</span></span> <span data-ttu-id="31820-192">Sie befinden sich nicht im Gültigkeitsbereich, wenn sie mithilfe der Syntax für statische Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31820-192">They are not in scope if they are called using the static method syntax:</span></span>

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

<span data-ttu-id="31820-193">Diese Entscheidung beruht darauf, dass Erweiterungsmethoden normalerweise mithilfe von Aufrufausdrücken für Erweiterungsmethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31820-193">This decision is because extension methods are typically called using extension method invocation expressions.</span></span> <span data-ttu-id="31820-194">Im seltenen Fall, wenn sie mithilfe der Syntax für statische Methoden aufgerufen werden, dient dies zur Auflösung von Mehrdeutigkeit.</span><span class="sxs-lookup"><span data-stu-id="31820-194">In the rare case where they are called using the static method call syntax it is to resolve ambiguity.</span></span>
<span data-ttu-id="31820-195">Es scheint wohlüberlegt zu sein, dass der Klassenname als Teil des Aufrufs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31820-195">Requiring the class name as part of the invocation seems wise.</span></span>

<span data-ttu-id="31820-196">Es gibt noch eine weitere Funktion von `static using`.</span><span class="sxs-lookup"><span data-stu-id="31820-196">There's one last feature of `static using`.</span></span> <span data-ttu-id="31820-197">Die `static using`-Direktive importiert auch keine geschachtelten Typen.</span><span class="sxs-lookup"><span data-stu-id="31820-197">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="31820-198">Dadurch können Sie auf alle geschachtelten Typen ohne Qualifikation verweisen.</span><span class="sxs-lookup"><span data-stu-id="31820-198">That enables you to reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="31820-199">Bedingter NULL-Operator</span><span class="sxs-lookup"><span data-stu-id="31820-199">Null-conditional operators</span></span>

<span data-ttu-id="31820-200">NULL-Werte erschweren den Code.</span><span class="sxs-lookup"><span data-stu-id="31820-200">Null values complicate code.</span></span> <span data-ttu-id="31820-201">Sie müssen jeden Zugriff von Variablen überprüfen, um sicherzugehen, dass Sie `null` nicht dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="31820-201">You need to check every access of variables to ensure you are not dereferencing `null`.</span></span> <span data-ttu-id="31820-202">Der *NULL-bedingte Operator* erleichtert diese Überprüfungen und macht sie flüssiger.</span><span class="sxs-lookup"><span data-stu-id="31820-202">The *null conditional operator* makes those checks much easier and fluid.</span></span>

<span data-ttu-id="31820-203">Ersetzen Sie einfach den Memberzugriff `.` mit `?.`:</span><span class="sxs-lookup"><span data-stu-id="31820-203">Simply replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="31820-204">Im vorangegangenen Beispiel, ist die Variable `first` `null` zugewiesen, wenn das Person-Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="31820-204">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="31820-205">Andernfalls wird ihr der Wert der `FirstName`-Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="31820-205">Otherwise, it gets assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="31820-206">Beachten Sie, dass `?.` bedeutet, dass diese Codezeile keine `NullReferenceException` generiert, wenn die `person`-Variable `null` ist.</span><span class="sxs-lookup"><span data-stu-id="31820-206">Most importantly, the `?.` means that this line of code does not generate a `NullReferenceException` when the `person` variable is `null`.</span></span> <span data-ttu-id="31820-207">Stattdessen wird direkt `null` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31820-207">Instead, it short-circuits and produces `null`.</span></span>

<span data-ttu-id="31820-208">Beachten Sie auch, die dieser Ausdruck einen `string` zurückgibt, unabhängig vom Wert der `person`.</span><span class="sxs-lookup"><span data-stu-id="31820-208">Also, note that this expression returns a `string`, regardless of the value of `person`.</span></span>
<span data-ttu-id="31820-209">Im Falle einer Verkürzung wird der zurückgegebene `null`-Wert aufgelistet, damit er mit dem vollständigen Ausdruck übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="31820-209">In the case of short circuiting, the `null` value returned is typed to match the full expression.</span></span>

<span data-ttu-id="31820-210">Häufig können Sie dieses Konstrukt mit dem *NULL-Sammeloperator* verwenden, um die Standardwerte zuzuweisen, wenn eines der Eigenschaften `null` ist:</span><span class="sxs-lookup"><span data-stu-id="31820-210">You can often use this construct with the *null coalescing* operator to assign default values when one of the properties are `null`:</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="31820-211">Der Operand auf der rechten Seite des `?.`-Operators ist nicht auf Eigenschaften oder Felder beschränkt.</span><span class="sxs-lookup"><span data-stu-id="31820-211">The right hand side operand of the `?.` operator is not limited to properties or fields.</span></span>
<span data-ttu-id="31820-212">Sie können ihn auch verwenden, um Methoden bedingt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31820-212">You can also use it to conditionally invoke methods.</span></span> <span data-ttu-id="31820-213">Die häufigste Verwendung von Memberfunktionen mit dem NULL-bedingten Operator ist, Delegaten (oder Ereignishandler), die möglicherweise `null` sind, sicher aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31820-213">The most common use of member functions with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="31820-214">Dazu müssen sie die `Invoke`-Methode des Delegaten mithilfe des `?.`-Operators aufrufen, um auf den Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="31820-214">You'll do this by calling the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="31820-215">Ein Beispiel dazu finden Sie im</span><span class="sxs-lookup"><span data-stu-id="31820-215">You can see an example in the</span></span>  
<span data-ttu-id="31820-216">Thema [delegate patterns (Delegieren von Mustern)](../delegates-patterns.md#handling-null-delegates).</span><span class="sxs-lookup"><span data-stu-id="31820-216">[delegate patterns](../delegates-patterns.md#handling-null-delegates) topic.</span></span>

<span data-ttu-id="31820-217">Die Regeln des `?.`-Operators stellen sicher, dass die linke Seite des Operators nur einmal ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="31820-217">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="31820-218">Dies ist wichtig und aktiviert viele Idiome, einschließlich das Beispiel mithilfe von Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="31820-218">This is important and enables many idioms, including the example using event handlers.</span></span> <span data-ttu-id="31820-219">Beginnen wir mit dem Gebrauch des Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="31820-219">Let's start with the event handler usage.</span></span> <span data-ttu-id="31820-220">In früheren Versionen von C# wurden Sie ermutigt, Code wie folgt zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="31820-220">In previous versions of C#, you were encouraged to write code like this:</span></span>

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

<span data-ttu-id="31820-221">Dies war einer einfacheren Syntax vorzuziehen:</span><span class="sxs-lookup"><span data-stu-id="31820-221">This was preferred over a simpler syntax:</span></span>

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> <span data-ttu-id="31820-222">Das obige Beispiel führt eine Racebedingung ein.</span><span class="sxs-lookup"><span data-stu-id="31820-222">The preceding example introduces a race condition.</span></span> <span data-ttu-id="31820-223">Das `SomethingHappened`-Ereignis hat womöglich Abonnenten, wenn es mit `null` verglichen wird. Diese Abonnenten wurden möglicherweise entfernt, bevor das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="31820-223">The `SomethingHappened` event may have subscribers when checked against `null`, and those subscribers may have been removed before the event is raised.</span></span> <span data-ttu-id="31820-224">Das würde dazu führen, dass eine <xref:System.NullReferenceException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="31820-224">That would cause a <xref:System.NullReferenceException> to be thrown.</span></span>

<span data-ttu-id="31820-225">In der zweiten Version, ist der `SomethingHappened`-Ereignishändler bei der Überprüfung möglicherweise nicht NULL. Wenn jedoch ein Handler von einem anderen Code entfernt wird, kann er trotzdem NULL sein, wenn der Ereignishandler aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="31820-225">In this second version, the `SomethingHappened` event handler might be non-null when tested, but if other code removes a handler, it could still be null when the event handler was called.</span></span>

<span data-ttu-id="31820-226">Der Compiler generiert Code für den `?.`-Operator, der gewährleistet, dass die linke Seite (`this.SomethingHappened`) des `?.`-Ausdrucks einmal ausgewertet und das Ergebnis zwischengespeichert wird:</span><span class="sxs-lookup"><span data-stu-id="31820-226">The compiler generates code for the `?.` operator that ensures the left side (`this.SomethingHappened`) of the `?.` expression is evaluated once, and the result is cached:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="31820-227">Wenn gewährleistet werden kann, dass die linke Seite nur einmal ausgewertet wird, dann können Sie beliebige Ausdrücke verwenden. Dazu gehören Methodenaufrufe auf der linken Seite von `?.` Auch wenn diese Nebeneffekte haben, werden sie nur einmal ausgewertet, sodass der Nebeneffekt nur einmal auftritt.</span><span class="sxs-lookup"><span data-stu-id="31820-227">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.` Even if these have side-effects, they are evaluated once, so the side effects occur only once.</span></span> <span data-ttu-id="31820-228">Ein Beispiel dazu finden Sie unter [Introduction to Events (Einführung in Ereignisse)](../events-overview.md#language-support-for-events).</span><span class="sxs-lookup"><span data-stu-id="31820-228">You can see an example in our content on [events](../events-overview.md#language-support-for-events).</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="31820-229">Zeichenfolgeninterpolierung</span><span class="sxs-lookup"><span data-stu-id="31820-229">String Interpolation</span></span>

<span data-ttu-id="31820-230">C# 6 enthält eine neue Syntax für die Zusammensetzung von Zeichenfolgen aus einer Formatzeichenfolge und aus Ausdrücken, die mit dem Ziel evaluiert werden, andere Zeichenfolgenwerte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="31820-230">C# 6 contains new syntax for composing strings from a format string and expressions that are evaluated to produce other string values.</span></span>

<span data-ttu-id="31820-231">In der Vergangenheit mussten Sie positionelle Parameter in einer Methode wie `string.Format` verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-231">Traditionally, you needed to use positional parameters in a method like `string.Format`:</span></span>

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

<span data-ttu-id="31820-232">Ab C# 6 hilft Ihnen das neue Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) dabei, die Ausdrücke in die Formatzeichenfolge einzubetten.</span><span class="sxs-lookup"><span data-stu-id="31820-232">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed the expressions in the format string.</span></span> <span data-ttu-id="31820-233">Stellen sie ganz einfach `$` vor die Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="31820-233">Simply preface the string with `$`:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="31820-234">In diesem ersten Beispiel werden Eigenschaftsausdrücke für die ersetzten Ausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="31820-234">This initial example uses property expressions for the substituted expressions.</span></span> <span data-ttu-id="31820-235">Sie können diese Syntax erweitern, damit Sie jeden beliebigen Ausdruck verwenden können</span><span class="sxs-lookup"><span data-stu-id="31820-235">You can expand on this syntax to use any expression.</span></span> <span data-ttu-id="31820-236">Sie können z.B. den Notendurchschnitt eines Studenten als Teil der Interpolation berechnen:</span><span class="sxs-lookup"><span data-stu-id="31820-236">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

<span data-ttu-id="31820-237">Sie bemerken vielleicht, dass die Ausgabe von `Grades.Average()`, die im vorherigen Beispiel ausgeführt wird, womöglich mehr Dezimalstellen hat, als Ihnen lieb ist.</span><span class="sxs-lookup"><span data-stu-id="31820-237">Running the preceding example, you would find that the output for `Grades.Average()` might have more decimal places than you would like.</span></span> <span data-ttu-id="31820-238">Die Zeichenfolgen-Interpolationssyntax unterstützt alle verfügbaren Formatzeichenfolgen mithilfe der vorherigen Formatierungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="31820-238">The string interpolation syntax supports all the format strings available using earlier formatting methods.</span></span> <span data-ttu-id="31820-239">Sie fügen die Formatzeichenfolgen innerhalb der geschweiften Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="31820-239">You add the format strings inside the braces.</span></span> <span data-ttu-id="31820-240">Fügen Sie ein `:` nach dem zu formatierenden Ausdruck ein:</span><span class="sxs-lookup"><span data-stu-id="31820-240">Add a `:` following the expression to format:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="31820-241">Die vorherige Codezeile formatiert den Wert für `Grades.Average()` als Gleitkommazahl mit zwei Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="31820-241">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="31820-242">Der `:` wird immer als Trennlinie zwischen dem Ausdruck, der formatiert wird, und der Formatzeichenfolge interpretiert.</span><span class="sxs-lookup"><span data-stu-id="31820-242">The `:` is always interpreted as the separator between the expression being formatted and the format string.</span></span> <span data-ttu-id="31820-243">Dies kann zu Problemen führen, wenn Ihr Ausdruck einen `:` anders verwendet, z.B. ein bedingter Operator:</span><span class="sxs-lookup"><span data-stu-id="31820-243">This can introduce problems when your expression uses a `:` in another way, such as a conditional operator:</span></span>

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

<span data-ttu-id="31820-244">Im vorhergehenden Beispiel wird der `:` als der Anfang der Formatzeichenfolge analysiert und nicht als Teil des bedingter Operator.</span><span class="sxs-lookup"><span data-stu-id="31820-244">In the preceding example, the `:` is parsed as the beginning of the format string, not part of the conditional operator.</span></span> <span data-ttu-id="31820-245">In den Fällen, in denen dies vorkommt, können Sie den Ausdruck mit Klammern umschließen, um den Compiler zu zwingen, den Ausdruck wie gewünscht zu interpretieren:</span><span class="sxs-lookup"><span data-stu-id="31820-245">In all cases where this happens, you can surround the expression with parentheses to force the compiler to interpret the expression as you intend:</span></span>

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

<span data-ttu-id="31820-246">Es gibt keine Einschränkungen für Ausdrücke, die Sie zwischen die geschweiften Klammern platzieren können.</span><span class="sxs-lookup"><span data-stu-id="31820-246">There aren't any limitations on the expressions you can place between the braces.</span></span> <span data-ttu-id="31820-247">Sie können eine komplexe LINQ-Abfrage in eine interpolierten Zeichenfolge ausführen, um Berechnungen auszuführen die Ergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="31820-247">You can execute a complex LINQ query inside an interpolated string to perform computations and display the result:</span></span>

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

<span data-ttu-id="31820-248">Sie können in diesem Beispiel sehen, dass Sie sogar eine Zeichenfolgeninterpolation in ein andere Zeichenfolgeninterpolation verschachteln können.</span><span class="sxs-lookup"><span data-stu-id="31820-248">You can see from this sample that you can even nest a string interpolation expression inside another string interpolation expression.</span></span> <span data-ttu-id="31820-249">Dieses Beispiel ist sicherlich viel komplexer, als wie Sie es im Produktionscode haben möchten.</span><span class="sxs-lookup"><span data-stu-id="31820-249">This example is very likely more complex than you would want in production code.</span></span>
<span data-ttu-id="31820-250">Es ist viel mehr zur Veranschaulichung der Breite der Funktion gedacht.</span><span class="sxs-lookup"><span data-stu-id="31820-250">Rather, it is illustrative of the breadth of the feature.</span></span> <span data-ttu-id="31820-251">Jeder C#-Ausdruck kann zwischen die geschweiften Klammern einer interpolierten Zeichenfolge platziert werden.</span><span class="sxs-lookup"><span data-stu-id="31820-251">Any C# expression can be placed between the curly braces of an interpolated string.</span></span>

### <a name="string-interpolation-and-specific-cultures"></a><span data-ttu-id="31820-252">Zeichenfolgeninterpolation und bestimmte Kulturen</span><span class="sxs-lookup"><span data-stu-id="31820-252">String interpolation and specific cultures</span></span>

<span data-ttu-id="31820-253">Alle Beispiele aus dem vorherigen Abschnitt formatieren die Zeichenfolgen mithilfe der aktuellen Kultur und Sprache auf dem Computer, auf dem der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31820-253">All the examples shown in the preceding section format the strings using the current culture and language on the machine where the code executes.</span></span> <span data-ttu-id="31820-254">Häufig müssen Sie die Zeichenfolge formatieren, die unter Verwendung einer bestimmten Kultur erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="31820-254">Often you may need to format the string produced using a specific culture.</span></span>
<span data-ttu-id="31820-255">Hierbei nutzen Sie die Tatsache, dass das Objekt, das durch die Zeichenfolgeninterpolation erstellt wurde, implizit in <xref:System.FormattableString> konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="31820-255">To do that use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString>.</span></span>

<span data-ttu-id="31820-256">Die <xref:System.FormattableString>-Instanz enthält die Formatzeichenfolge sowie die Ergebnisse der Auswertung der Ausdrücke, bevor sie in Zeichenfolgen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="31820-256">The <xref:System.FormattableString> instance contains the format string, and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="31820-257">Sie können öffentliche Methoden von <xref:System.FormattableString> verwenden, um die Kultur anzugeben, wenn Sie eine Zeichenfolge formatieren.</span><span class="sxs-lookup"><span data-stu-id="31820-257">You can use public methods of <xref:System.FormattableString> to specify the culture when formatting a string.</span></span> <span data-ttu-id="31820-258">Im folgenden Beispiel wird mit der deutschen Kultur eine Zeichenfolge erstellt.</span><span class="sxs-lookup"><span data-stu-id="31820-258">For example, the following example produces a string using German culture.</span></span> <span data-ttu-id="31820-259">Dazu wird das Zeichen „,“ für das Dezimaltrennzeichen sowie das Zeichen „.“ als Tausendertrennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="31820-259">(It uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="31820-260">Weitere Informationen finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="31820-260">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="31820-261">Ausnahmefilter</span><span class="sxs-lookup"><span data-stu-id="31820-261">Exception Filters</span></span>

<span data-ttu-id="31820-262">Ein weiteres neues Feature in C# 6 ist das der *Ausnahmefilter*.</span><span class="sxs-lookup"><span data-stu-id="31820-262">Another new feature in C# 6 is *exception filters*.</span></span> <span data-ttu-id="31820-263">Ausnahmefilter sind Klauseln, die festlegen, wenn eine bestimmte Catch-Klausel angewendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="31820-263">Exception Filters are clauses that determine when a given catch clause should be applied.</span></span>
<span data-ttu-id="31820-264">Wenn der für einen Ausnahmefilter verwendete Ausdruck `true` ergibt, führt die Catch-Klausel die normale Verarbeitung auf einer Ausnahme durch.</span><span class="sxs-lookup"><span data-stu-id="31820-264">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="31820-265">Wenn der Ausdruck `false` ergibt, wird die `catch`-Klausel übersprungen.</span><span class="sxs-lookup"><span data-stu-id="31820-265">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span>

<span data-ttu-id="31820-266">Eine Verwendung ist, Informationen über eine Ausnehme zu untersuchen, um zu bestimmen, ob eine `catch`-Klausel die Ausnahme verarbeiten kann:</span><span class="sxs-lookup"><span data-stu-id="31820-266">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

<span data-ttu-id="31820-267">Der vom Ausnahmefilter generierte Code bietet bessere Informationen zu einer Ausnahme, die ausgelöst und nicht verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="31820-267">The code generated by exception filters provides better information about an exception that is thrown and not processed.</span></span> <span data-ttu-id="31820-268">Bevor Ausnahmefilter zur Sprache hinzugefügt wurden, muss der Code wie folgt erstellt worden sein:</span><span class="sxs-lookup"><span data-stu-id="31820-268">Before exception filters were added to the language, you would need to create code like the following:</span></span>

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

<span data-ttu-id="31820-269">Der Zeitpunkt, an dem die Ausnahme ausgelöst wird, ändert sich zwischen diesen beiden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="31820-269">The point where the exception is thrown changes between these two examples.</span></span>
<span data-ttu-id="31820-270">Im vorherigen Code, in dem eine `throw`-Klausel verwendet wird, zeigt jede Stapelüberwachungsanalyse oder Untersuchung von Absturzimages, dass die Ausnahme von der `throw`-Anweisung in Ihrer Catch-Klausel ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="31820-270">In the previous code, where a `throw` clause is used, any stack trace analysis or examination of crash dumps will show that the exception was thrown from the `throw` statement in your catch clause.</span></span> <span data-ttu-id="31820-271">Das tatsächliche Ausnahmeobjekt enthält die ursprüngliche Aufrufliste, jedoch sind alle anderen Informationen über Variablen in der Aufrufliste zwischen diesem Auslösepunkt und dem Ort des ursprünglichen Auslösepunkts verloren.</span><span class="sxs-lookup"><span data-stu-id="31820-271">The actual exception object will contain the original call stack, but all other information about any variables in the call stack between this throw point and the location of the original throw point has been lost.</span></span> 

<span data-ttu-id="31820-272">Im Gegensatz dazu steht die Vorgehensweise, wie der Code mithilfe einer Ausnahmedatei verarbeitet wird: Der Ausnahmefilterausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="31820-272">Contrast that with how the code using an exception filter is processed: the exception filter expression evaluates to `false`.</span></span> <span data-ttu-id="31820-273">Daher geht die Ausnahme nie in die `catch`-Klausel hinein.</span><span class="sxs-lookup"><span data-stu-id="31820-273">Therefore, execution never enters the `catch` clause.</span></span> <span data-ttu-id="31820-274">Da die `catch`-Klausel nicht ausgeführt wird, findet keine Stapelentladung statt.</span><span class="sxs-lookup"><span data-stu-id="31820-274">Because the `catch` clause does not execute, no stack unwinding takes place.</span></span> <span data-ttu-id="31820-275">Das bedeutet, dass die ursprüngliche Auslöseposition für jegliche Debugaktivitäten beibehalten wird, die später ausgeführt werden wird.</span><span class="sxs-lookup"><span data-stu-id="31820-275">That means the original throw location is preserved for any debugging activities that would take place later.</span></span>

<span data-ttu-id="31820-276">Wann immer Sie Felder oder Eigenschaften einer Ausnahme auswerten müssen, anstatt sich ausschließlich auf den Ausnahmetyp zu verlassen, verwenden Sie einen Ausnahmefilter, um weitere Debuginformationen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="31820-276">Whenever you need to evaluate fields or properties of an exception, instead of relying solely on the exception type, use an exception filter to preserve more debugging information.</span></span>

<span data-ttu-id="31820-277">Ein weiteres empfohlenen Muster mit Ausnahmefiltern ist, diese für die Protokollierung von Routinen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-277">Another recommended pattern with exception filters is to use them for logging routines.</span></span> <span data-ttu-id="31820-278">Diese Verwendung nutzt auch die Art, wie der Auslösepunkt der Ausnahme beibehalten wird, wenn ein Ausnahmefilter `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="31820-278">This usage also leverages the manner in which the exception throw point is preserved when an exception filter evaluates to `false`.</span></span>

<span data-ttu-id="31820-279">Eine Protokollierungsmethode wäre eine Methode, deren Argument die Ausnahme ist, die ohne Bedingung `false` zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="31820-279">A logging method would be a method whose argument is the exception that unconditionally returns `false`:</span></span>

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

<span data-ttu-id="31820-280">Wenn Sie eine Ausnahme protokollieren möchten, können Sie eine Catch-Klausel hinzufügen und diese Methode als Ausnahmefilter verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-280">Whenever you want to log an exception, you can add a catch clause, and use this method as the exception filter:</span></span>

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

<span data-ttu-id="31820-281">Die Ausnahmen werden nie abgefangen, da die `LogException`-Methode immer `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="31820-281">The exceptions are never caught, because the `LogException` method always returns `false`.</span></span> <span data-ttu-id="31820-282">Der Ausnahmefilter „always false“ (immer falsch) bedeutet, dass Sie diesen Logging Handler vor jedem anderen Ausnahmehandler platzieren können.</span><span class="sxs-lookup"><span data-stu-id="31820-282">That always false exception filter means that you can place this logging handler before any other exception handlers:</span></span>

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

<span data-ttu-id="31820-283">Im vorherigen Beispiel wird ein sehr wichtiger Aspekt der Ausnahmefilter hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="31820-283">The preceding example highlights a very important facet of exception filters.</span></span>
<span data-ttu-id="31820-284">Die Ausnahmefilter ermöglichen Szenarios, in denen eine allgemeine Ausnahme-Catch-Klausel vor einer spezifischeren angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31820-284">The exception filters enable scenarios where a more general exception catch clause may appear before a more specific one.</span></span> <span data-ttu-id="31820-285">Es ist auch möglich, dass derselbe Ausnahmetyp in mehrere Catch-Klauseln vorkommt:</span><span class="sxs-lookup"><span data-stu-id="31820-285">It's also possible to have the same exception type appear in multiple catch clauses:</span></span>

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

<span data-ttu-id="31820-286">Ein weiteres empfohlenen Muster hilft zu verhindern, dass Catch-Klauseln Ausnahmen verarbeiten, wenn ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="31820-286">Another recommended pattern helps prevent catch clauses from processing exceptions when a debugger is attached.</span></span> <span data-ttu-id="31820-287">Mit dieser Technik können Sie eine Anwendung mit dem Debugger ausführen und diese Ausführung anhalten, wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="31820-287">This technique enables you to run an application with the debugger, and stop execution when an exception is thrown.</span></span>

<span data-ttu-id="31820-288">Fügen Sie in ihrem Code einen Ausnahmefilter hinzu, damit jeder Wiederherstellungscode nur ausgeführt wird, wenn kein Debugger angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="31820-288">In your code, add an exception filter so that any recovery code executes only when a debugger is not attached:</span></span>

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

<span data-ttu-id="31820-289">Nachdem Sie diesen in den Code hinzugefügt haben, richten Sie Ihren Debugger so ein, dass er alle Ausnahmefehler unterbrechen soll.</span><span class="sxs-lookup"><span data-stu-id="31820-289">After adding this in code, you set your debugger to break on all unhandled exceptions.</span></span> <span data-ttu-id="31820-290">Führen Sie das Programm unter dem Debugger aus, und der Debugger unterbricht jedes Mal, wenn `PerformFailingOperation()` eine `RecoverableException` auslöst.</span><span class="sxs-lookup"><span data-stu-id="31820-290">Run the program under the debugger, and the debugger breaks whenever `PerformFailingOperation()` throws a `RecoverableException`.</span></span>
<span data-ttu-id="31820-291">Der Debugger unterbricht das Programm, da aufgrund des falsch zurückgegebenen Ausnahmefilters die Catch-Klausel nicht ausgeführt werden würde.</span><span class="sxs-lookup"><span data-stu-id="31820-291">The debugger breaks your program, because the catch clause won't be executed due to the false-returning exception filter.</span></span>

## <a name="nameof-expressions"></a><span data-ttu-id="31820-292">`nameof`-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="31820-292">`nameof` Expressions</span></span>

<span data-ttu-id="31820-293">Der `nameof`-Ausdruck wertet den Namen des Symbols aus.</span><span class="sxs-lookup"><span data-stu-id="31820-293">The `nameof` expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="31820-294">Es ist eine hervorragende Möglichkeit, Tools zum Arbeiten zu bringen, wenn Sie den Namen einer Variable, Eigenschaften oder eines Memberfelds benötigen.</span><span class="sxs-lookup"><span data-stu-id="31820-294">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span>

<span data-ttu-id="31820-295">Eine der häufigsten Verwendungszwecke für `nameof` besteht darin, den Namen eines Symbols bereitzustellen, die eine Ausnahme ausgelöst hat:</span><span class="sxs-lookup"><span data-stu-id="31820-295">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="31820-296">Sie können den Ausdruck auch mit auf XAML basierenden Anwendungen verwenden, die die `INotifyPropertyChanged`-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="31820-296">Another use is with XAML based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

<span data-ttu-id="31820-297">Der Vorteil der Verwendung des `nameof`-Operators im Gegensatz zu einer konstanten Zeichenfolge ist, dass Tools das Symbol verstehen können.</span><span class="sxs-lookup"><span data-stu-id="31820-297">The advantage of using the `nameof` operator over a constant string is that tools can understand the symbol.</span></span> <span data-ttu-id="31820-298">Wenn Sie Umgestaltungstools verwenden, um das Symbol umzubenennen, wird es im `nameof`-Ausdruck umbenannt.</span><span class="sxs-lookup"><span data-stu-id="31820-298">If you use refactoring tools to rename the symbol, it will rename it in the `nameof` expression.</span></span> <span data-ttu-id="31820-299">Konstante Zeichenfolgen besitzen nicht diesen Vorteil.</span><span class="sxs-lookup"><span data-stu-id="31820-299">Constant strings don't have that advantage.</span></span> <span data-ttu-id="31820-300">Probieren Sie es in Ihrem bevorzugten Editor aus: Benennen Sie eine Variable um, und jeder `nameof`-Ausdruck wird ebenso aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="31820-300">Try it yourself in your favorite editor: rename a variable, and any `nameof` expressions will update as well.</span></span>

<span data-ttu-id="31820-301">Der `nameof`-Ausdruck erstellt den unqualifizierten Namen seines Arguments (`LastName` in den vorherigen Beispielen), auch wenn Sie den vollqualifizierten Namen für das Argument verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-301">The `nameof` expression produces the unqualified name of its argument (`LastName` in the previous examples) even if you use the fully qualified name for the argument:</span></span>

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

<span data-ttu-id="31820-302">Dieser `nameof`-Ausdruck erzeugt `FirstName` und nicht `UXComponents.ViewModel.FirstName`.</span><span class="sxs-lookup"><span data-stu-id="31820-302">This `nameof` expression produces `FirstName`, not `UXComponents.ViewModel.FirstName`.</span></span>

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="31820-303">„Await“ in Catch- und Finally-Blöcken</span><span class="sxs-lookup"><span data-stu-id="31820-303">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="31820-304">C# 5 hat mehrere Einschränkungen im Hinblick auf die Position von `await`-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="31820-304">C# 5 had several limitations around where you could place `await` expressions.</span></span>
<span data-ttu-id="31820-305">Eine solche wurde in C#6 entfernt.</span><span class="sxs-lookup"><span data-stu-id="31820-305">One of those has been removed in C# 6.</span></span> <span data-ttu-id="31820-306">Sie können nun `await` in `catch`- oder `finally`-Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-306">You can now use `await` in `catch` or `finally` expressions.</span></span> 

<span data-ttu-id="31820-307">Das Hinzufügen von await-Ausdrücken in Catch- und Finally-Blöcken scheint die Verarbeitung von diesen zu erschweren.</span><span class="sxs-lookup"><span data-stu-id="31820-307">The addition of await expressions in catch and finally blocks may appear to complicate how those are processed.</span></span> <span data-ttu-id="31820-308">Lassen Sie uns ein Beispiel hinzufügen, um zu Erläutern, warum das so ist.</span><span class="sxs-lookup"><span data-stu-id="31820-308">Let's add an example to discuss how this appears.</span></span> <span data-ttu-id="31820-309">In einer async-Methode können Sie einen await-Ausdruck in einer Finally-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-309">In any async method, you can use an await expression in a finally clause.</span></span>

<span data-ttu-id="31820-310">Mit C# 6 können Sie await auch in Catch-Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-310">With C# 6, you can also await in catch expressions.</span></span> <span data-ttu-id="31820-311">Dies wird am häufigsten in Protokollierungsszenarios verwendet:</span><span class="sxs-lookup"><span data-stu-id="31820-311">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="31820-312">Die Implementierungsdetails für das Hinzufügen von `await`-Unterstützung in `catch`- und `finally`-Klauseln stellt sicher, dass das Verhalten konsistent mit dem Verhalten für synchronen Code ist.</span><span class="sxs-lookup"><span data-stu-id="31820-312">The implementation details for adding `await` support inside `catch` and `finally` clauses ensures that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="31820-313">Wenn Code, der in einer `catch`- oder `finally`-Klausel ausgeführt wird, ausgelöst wird, so sucht die Ausführung nach einer passenden `catch`-Klausel im nächsten Block in der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="31820-313">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="31820-314">Wenn eine aktuelle Ausnahme aufgetreten ist, geht diese Ausnahme verloren.</span><span class="sxs-lookup"><span data-stu-id="31820-314">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="31820-315">Das Gleiche passiert bei erwarteten Ausdrücken in `catch`- und `finally`-Klauseln: eine passende `catch` wird gesucht und die aktuelle Ausnahme, falls vorhanden, geht verloren.</span><span class="sxs-lookup"><span data-stu-id="31820-315">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="31820-316">Dieses Verhalten ist der Grund, warum es empfohlen wird, `catch`- und `finally`-Klauseln sorgfältig zu schreiben, um die Einführung neuer Ausnahmen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="31820-316">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="index-initializers"></a><span data-ttu-id="31820-317">Indexinitialisierer</span><span class="sxs-lookup"><span data-stu-id="31820-317">Index Initializers</span></span>

<span data-ttu-id="31820-318">Der *Indexinitialisierer* ist eine von zwei Funktionen, die Auflistungsinitialisierer konsistenter machen.</span><span class="sxs-lookup"><span data-stu-id="31820-318">*Index Initializers* is one of two features that make collection initializers more consistent.</span></span> <span data-ttu-id="31820-319">In früheren Versionen von C# konnten Sie *Auflistungsinitialisierer* nur mit Auflistungen im Sequenzformat verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-319">In earlier releases of C#, you could use *collection initializers* only with sequence style collections:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

<span data-ttu-id="31820-320">Sie können diese nun mit <xref:System.Collections.Generic.Dictionary%602>-Auflistungen und ähnlichen Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-320">Now, you can also use them with <xref:System.Collections.Generic.Dictionary%602> collections and similar types:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="31820-321">Dieses Feature bedeutet, dass assoziative Container mithilfe von Syntax initialisiert werden können, die ähnlich dem ist, was für Sequenzcontainern für einige Versionen vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="31820-321">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

### <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="31820-322">Erweiterungs-`Add`-Methoden in Auflistungsinitialisierern</span><span class="sxs-lookup"><span data-stu-id="31820-322">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="31820-323">Ein weiteres Feature zur Vereinfachung der Auflistungsinitialisierer ist die Möglichkeit, eine *Erweiterungsmethode* für die `Add`-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="31820-323">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="31820-324">Dieses Feature wurde für die Parität mit Visual Basic hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="31820-324">This feature was added for parity with Visual Basic.</span></span> 

<span data-ttu-id="31820-325">Das Feature ist am nützlichsten, wenn Sie über eine benutzerdefinierte Auflistungsklasse verfügen, die eine Methode mit einem anderen Namen besitzt, um semantisch neue Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="31820-325">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

<span data-ttu-id="31820-326">Betrachten Sie z.B. eine Auflistung von Studenten, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="31820-326">For example, consider a collection of students like this:</span></span>

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

<span data-ttu-id="31820-327">Die `Enroll`-Methode fügt einen Studenten hinzu.</span><span class="sxs-lookup"><span data-stu-id="31820-327">The `Enroll` method adds a student.</span></span> <span data-ttu-id="31820-328">Aber dies entspricht nicht den Regeln des `Add`-Musters.</span><span class="sxs-lookup"><span data-stu-id="31820-328">But it doesn't follow the `Add` pattern.</span></span>
<span data-ttu-id="31820-329">In früheren Versionen von C# konnten Sie keine Auflistungsinitialisierer mit einem `Enrollment`-Objekt benutzen.</span><span class="sxs-lookup"><span data-stu-id="31820-329">In previous versions of C#, you could not use collection initializers with an `Enrollment` object:</span></span>

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

<span data-ttu-id="31820-330">Das können Sie nun tun, jedoch nur, wenn Sie eine Erweiterungsmethode erstellen, die `Add` `Enroll` zuordnet.</span><span class="sxs-lookup"><span data-stu-id="31820-330">Now you can, but only if you create an extension method that maps `Add` to `Enroll`:</span></span>

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

<span data-ttu-id="31820-331">Mit diesem Feature ordnen Sie die Methode, die Elemente zu einer Sammlung hinzufügt, einer Methode mit dem Namen `Add` zu, indem Sie eine Erweiterungsmethode erstellen.</span><span class="sxs-lookup"><span data-stu-id="31820-331">What you are doing with this feature is to map whatever method adds items to a collection to a method named `Add` by creating an extension method:</span></span> 

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]
[!code-csharp[ExtensionAddSample](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAddSample)]

## <a name="improved-overload-resolution"></a><span data-ttu-id="31820-332">Verbesserte Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="31820-332">Improved overload resolution</span></span>

<span data-ttu-id="31820-333">Dieses letzte Feature ist eines, das Sie bestimmt nicht bemerken.</span><span class="sxs-lookup"><span data-stu-id="31820-333">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="31820-334">Es gab Konstrukte, bei denen die vorherige Version des C#-Compilers womögliche einige Methodenaufrufe erkannt hat, einschließlich mehrdeutige Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="31820-334">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="31820-335">Betrachten Sie diese Methode:</span><span class="sxs-lookup"><span data-stu-id="31820-335">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="31820-336">In früheren Methoden von C# schlug der Aufruf dieser Methode mithilfe der Syntax für die Methodengruppe fehl:</span><span class="sxs-lookup"><span data-stu-id="31820-336">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
<span data-ttu-id="31820-337">Der frühere Compiler konnte nicht richtig zwischen `Task.Run(Action)` und `Task.Run(Func<Task>())` unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="31820-337">The earlier compiler could not distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="31820-338">In früheren Versionen müssten Sie einen Lambdaausdruck als Argument verwenden:</span><span class="sxs-lookup"><span data-stu-id="31820-338">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="31820-339">Der C# 6-Compiler bestimmt ordnungsgemäß, dass `Task.Run(Func<Task>())` eine bessere Wahl ist.</span><span class="sxs-lookup"><span data-stu-id="31820-339">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>
