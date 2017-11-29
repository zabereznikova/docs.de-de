---
title: Eigenschaften (F#)
description: Informationen Sie zu F#-Eigenschaften, die Elemente sind, die einem Objekt zugeordneten Werte darstellen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a><span data-ttu-id="1ee00-104">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ee00-104">Properties</span></span>

<span data-ttu-id="1ee00-105">*Eigenschaften* angehören, die einem Objekt zugeordneten Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="1ee00-105">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="1ee00-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ee00-106">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="1ee00-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ee00-107">Remarks</span></span>
<span data-ttu-id="1ee00-108">Eigenschaften stellen die "hat eine" Beziehung in einer objektorientierten Programmierung darstellen von Daten, die mit der Objekt-Instanzen oder für statische Eigenschaften, mit dem Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ee00-108">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="1ee00-109">Sie können Deklarieren von Eigenschaften in zwei Möglichkeiten, je nachdem, ob Sie den zugrunde liegenden Wert (auch als "Sicherungsspeicher" bezeichnet) für die Eigenschaft explizit angeben möchten oder wenn den Compiler den Sicherungsspeicher für Sie automatisch generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ee00-109">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="1ee00-110">Im Allgemeinen sollten Sie die expliziter-Methode, wenn die Eigenschaft eine nicht triviale Implementierung hat und die automatische Methode verwenden, wenn die Eigenschaft nur einen einfachen Wrapper für einen Wert oder eine Variable ist.</span><span class="sxs-lookup"><span data-stu-id="1ee00-110">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="1ee00-111">Um eine Eigenschaft explizit zu deklarieren, verwenden die `member` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1ee00-111">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="1ee00-112">Diese deklarative Syntax wird gefolgt von der Syntax, der angibt, die `get` und `set` Methoden, die auch als *Accessoren*.</span><span class="sxs-lookup"><span data-stu-id="1ee00-112">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="1ee00-113">Für Lese-/Schreibzugriff, schreibgeschützte und lesegeschützte Eigenschaften werden die verschiedenen Formen von explicit-Syntax im Syntaxabschnitt gezeigt verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ee00-113">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="1ee00-114">Für schreibgeschützte Eigenschaften definieren Sie nur eine `get` Methode für nur-schreiben Eigenschaften definieren Sie nur eine `set` Methode.</span><span class="sxs-lookup"><span data-stu-id="1ee00-114">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="1ee00-115">Beachten Sie, dass, wenn eine Eigenschaft sowohl hat `get` und `set` Accessoren, die alternative Syntax können Sie angeben, Attribute und Zugriffsmodifizierer, die für jeden Accessor unterschiedlich, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1ee00-115">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="1ee00-116">Für Lese-/Schreibeigenschaften, die beide verfügen über eine `get` und `set` -Methode, die Reihenfolge der `get` und `set` können rückgängig gemacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ee00-116">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="1ee00-117">Alternativ können Sie die Syntax für bereitstellen `get` nur und die Syntax für `set` nur anstelle der kombinierten Syntax.</span><span class="sxs-lookup"><span data-stu-id="1ee00-117">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="1ee00-118">Dies macht es einfacher, kommentieren Sie die einzelnen `get` oder `set` -Methode, wenn etwas ist Sie möglicherweise erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ee00-118">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="1ee00-119">Diese Alternative zum Verwenden der kombinierten Syntax wird im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1ee00-119">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="1ee00-120">Private Werte, die Daten für Eigenschaften heißen, Aufbewahrungspflicht *Sicherungsspeicher*.</span><span class="sxs-lookup"><span data-stu-id="1ee00-120">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="1ee00-121">Damit den Compiler den Sicherungsspeicher automatisch zu erstellen, verwenden Sie die Schlüsselwörter `member val`, lassen Sie die Self-Bezeichner, und geben Sie einen Ausdruck, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1ee00-121">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="1ee00-122">Wenn die Eigenschaft auf änderbare werden, enthalten `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="1ee00-122">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="1ee00-123">Beispielsweise enthält die folgenden Klassentyp zwei automatisch implementierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1ee00-123">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="1ee00-124">`Property1`ist schreibgeschützt und wird an das Argument bereitgestellt, um den primären Konstruktor initialisiert und `Property2` eine festlegbare Eigenschaft auf eine leere Zeichenfolge initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="1ee00-124">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="1ee00-125">Automatisch implementierte Eigenschaften sind Teil die Initialisierung eines Typs aus, damit sie ebenso wie vor anderen Memberdefinitionen enthalten sein müssen `let` Bindungen und `do` Bindungen in einer Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="1ee00-125">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="1ee00-126">Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert nur ausgewertet wird, bei der Initialisierung und nicht jedes Mal, wenn die Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="1ee00-126">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="1ee00-127">Dieses Verhalten ist im Gegensatz zu das Verhalten einer explizit implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ee00-127">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="1ee00-128">Was dies bedeutet, die der Code zum Initialisieren dieser Eigenschaften ist, wird an den Konstruktor der Klasse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ee00-128">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="1ee00-129">Betrachten Sie den folgenden Code, der diesen Unterschied verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="1ee00-129">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="1ee00-130">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="1ee00-130">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="1ee00-131">Die Ausgabe des vorhergehenden Codes zeigt, dass der Wert des AutoProperty unverändert bei wird wiederholt aufgerufen, während die ExplicitProperty jedes Mal ändert, wenn er aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1ee00-131">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="1ee00-132">Dadurch wird bewiesen, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht in jedem Fall ausgewertet wird, wie die Gettermethode für die explizite-Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="1ee00-132">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="1ee00-133">Es gibt einige Bibliotheken, wie das Entity Framework (`System.Data.Entity`) führen Sie benutzerdefinierte Operationen, die in den Konstruktoren, die auch bei der Initialisierung von automatisch implementierten Eigenschaften nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ee00-133">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="1ee00-134">Verwenden Sie in diesen Fällen explizite Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1ee00-134">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="1ee00-135">Eigenschaften können Mitglieder der Klassen, Strukturen, Unterscheidungs-Unions, Datensätze, Schnittstellen und typerweiterungen sein und können auch im Objektausdrücke definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ee00-135">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="1ee00-136">Attribute können auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ee00-136">Attributes can be applied to properties.</span></span> <span data-ttu-id="1ee00-137">Um ein Attribut auf eine Eigenschaft anwenden möchten, Schreiben Sie das Attribut in einer separaten Zeile vor der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ee00-137">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="1ee00-138">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1ee00-138">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="1ee00-139">Standardmäßig sind die Eigenschaften öffentlich.</span><span class="sxs-lookup"><span data-stu-id="1ee00-139">By default, properties are public.</span></span> <span data-ttu-id="1ee00-140">Eigenschaften können auch Zugriffsmodifizierer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ee00-140">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="1ee00-141">Zum Anwenden eines Zugriffsmodifizierers hinzufügen unmittelbar vor dem Namen der Eigenschaft vorgesehen ist, gelten für beide die `get` und `set` Methoden; fügen Sie ihn ein, bevor die `get` und `set` Schlüsselwörter, wenn unterschiedliche zugriffsmöglichkeiten ist für jeden Accessor erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ee00-141">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="1ee00-142">Die *Zugriffsmodifizierer* kann eines der folgenden sein: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="1ee00-142">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="1ee00-143">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="1ee00-143">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="1ee00-144">Eigenschaft Implementierungen werden jedes Mal ausgeführt, wenn eine Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="1ee00-144">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="1ee00-145">Statische und Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ee00-145">Static and Instance Properties</span></span>
<span data-ttu-id="1ee00-146">Eigenschaften können statisch sein oder Instanzeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1ee00-146">Properties can be static or instance properties.</span></span> <span data-ttu-id="1ee00-147">Statische Eigenschaften können ohne Instanz aufgerufen werden und dienen zur Werte, die dem Typ, nicht für einzelne Objekte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1ee00-147">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="1ee00-148">Lassen Sie für statische Eigenschaften den Self-Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="1ee00-148">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="1ee00-149">Der Self-Bezeichner ist für Instanzeigenschaften erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ee00-149">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="1ee00-150">Die folgende Definition für die statische Eigenschaft basiert auf ein Szenario, in dem Sie ein statisches Feld `myStaticValue` also der Sicherungsspeicher für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ee00-150">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="1ee00-151">Eigenschaften können auch sein arrayähnlichen, in diesem Fall werden sie aufgerufen *indizierte Eigenschaften*.</span><span class="sxs-lookup"><span data-stu-id="1ee00-151">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="1ee00-152">Weitere Informationen finden Sie unter [indizierten Eigenschaften](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1ee00-152">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="1ee00-153">Typanmerkung für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ee00-153">Type Annotation for Properties</span></span>
<span data-ttu-id="1ee00-154">In vielen Fällen wird der Compiler verfügt über genügend Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungsspeichers abgeleitet werden, aber Sie können den Typ explizit festlegen, indem eine typanmerkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1ee00-154">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="1ee00-155">Set-Accessoren mit der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1ee00-155">Using Property set Accessors</span></span>
<span data-ttu-id="1ee00-156">Einstellbaren Eigenschaften bereit `set` Accessoren mithilfe der `<-` Operator.</span><span class="sxs-lookup"><span data-stu-id="1ee00-156">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="1ee00-157">Die Ausgabe lautet **20**.</span><span class="sxs-lookup"><span data-stu-id="1ee00-157">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="1ee00-158">Abstrakte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ee00-158">Abstract Properties</span></span>
<span data-ttu-id="1ee00-159">Eigenschaften können abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="1ee00-159">Properties can be abstract.</span></span> <span data-ttu-id="1ee00-160">Wie bei Methoden, `abstract` bedeutet lediglich, dass ein virtueller Dispatch der Eigenschaft zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ee00-160">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="1ee00-161">Abstrakte Eigenschaften können tatsächlich abstrakt ist, d. h. ohne Definition in der gleichen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="1ee00-161">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="1ee00-162">Die Klasse enthält eine solche Eigenschaft ist daher eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="1ee00-162">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="1ee00-163">Alternativ kann nur abstrakte bedeuten, dass eine Eigenschaft virtuell ist und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1ee00-163">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="1ee00-164">Beachten Sie, dass abstrakte Eigenschaften nicht privat sein, wenn ein Accessor abstrakt ist, der andere auch muss sein abstrakt.</span><span class="sxs-lookup"><span data-stu-id="1ee00-164">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="1ee00-165">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="1ee00-165">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="1ee00-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee00-166">See Also</span></span>
[<span data-ttu-id="1ee00-167">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="1ee00-167">Members</span></span>](index.md)

[<span data-ttu-id="1ee00-168">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ee00-168">Methods</span></span>](methods.md)
