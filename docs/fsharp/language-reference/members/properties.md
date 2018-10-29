---
title: Eigenschaften (F#)
description: Informationen Sie zu F#-Eigenschaften, die Mitglieder sind, die einem Objekt zugeordneten Werte darstellen.
ms.date: 05/16/2016
ms.openlocfilehash: 75d21415b44ccc1c26ef5f478d5f5de20c3412e8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197924"
---
# <a name="properties"></a><span data-ttu-id="586f7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="586f7-103">Properties</span></span>

<span data-ttu-id="586f7-104">*Eigenschaften* angehören, die einem Objekt zugeordneten Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="586f7-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="586f7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="586f7-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="586f7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="586f7-106">Remarks</span></span>

<span data-ttu-id="586f7-107">Eigenschaften stellen die "verfügt über eine" Beziehung in der objektorientierten Programmierung datendarstellung, die Objektinstanzen oder, für statische Eigenschaften, mit dem Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="586f7-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="586f7-108">Sie können deklarieren, Eigenschaften, die auf zwei Arten, abhängig davon, ob Sie explizit den zugrunde liegenden Wert (auch als "Sicherungsspeicher" bezeichnet) für die Eigenschaft angeben möchten oder wenn den Compiler automatisch der Sicherungsspeicher für Sie generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="586f7-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="586f7-109">Im Allgemeinen sollten Sie die explizitere Weise, wenn die Eigenschaft eine nicht triviale Implementierung verfügt und die automatische Methode verwenden, wenn die Eigenschaft nur ein einfacher Wrapper für ein Wert oder eine Variable ist.</span><span class="sxs-lookup"><span data-stu-id="586f7-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="586f7-110">Um eine Eigenschaft explizit deklarieren, verwenden die `member` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="586f7-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="586f7-111">Diese deklarative Syntax folgt die Syntax, der angibt, die `get` und `set` Methoden, die auch mit dem Namen *Accessoren*.</span><span class="sxs-lookup"><span data-stu-id="586f7-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="586f7-112">Die verschiedenen Formen der expliziten Syntax im Syntaxabschnitt dargestellt werden für Lese-/Schreibzugriff, schreibgeschützte und lesegeschützte Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="586f7-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="586f7-113">Für schreibgeschützte Eigenschaften, definieren Sie nur eine `get` Methode für nur-schreiben-Eigenschaften, definieren Sie nur eine `set` Methode.</span><span class="sxs-lookup"><span data-stu-id="586f7-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="586f7-114">Beachten Sie, dass, wenn eine Eigenschaft sowohl hat `get` und `set` -Accessor angeben, die alternative Syntax können Sie angeben, Attribute und Zugriffsmodifizierer, die sich für jeden Accessor, wie im folgenden Code gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="586f7-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="586f7-115">Eigenschaften von Lese-/Schreibzugriff, die jeweils eine `get` und `set` -Methode, die Reihenfolge der `get` und `set` rückgängig gemacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="586f7-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="586f7-116">Alternativ können Sie die Syntax für die bereitstellen `get` nur und die Syntax für `set` nur anstelle der kombinierten Syntax.</span><span class="sxs-lookup"><span data-stu-id="586f7-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="586f7-117">Dies macht es einfacher, kommentieren Sie die einzelnen `get` oder `set` -Methode, wenn dies etwas ist müssen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="586f7-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="586f7-118">Diese Alternative zur Verwendung von der kombinierten Syntax ist in den folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="586f7-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="586f7-119">Private Werte, die Daten für Eigenschaften heißen, halten *Sicherungsspeicher*.</span><span class="sxs-lookup"><span data-stu-id="586f7-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="586f7-120">Damit den Compiler automatisch den Sicherungsspeicher zu erstellen, verwenden Sie die Schlüsselwörter `member val`, lassen Sie die Self-ID, und geben Sie einen Ausdruck, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="586f7-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="586f7-121">Wenn die Eigenschaft ist veränderlich sein müssen, schließen Sie `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="586f7-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="586f7-122">Der folgende Klassentyp enthält beispielsweise zwei automatisch implementierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="586f7-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="586f7-123">`Property1` ist schreibgeschützt und wird mit dem Argument bereitgestellt, um den primären Konstruktor, initialisiert und `Property2` ist eine Eigenschaft festgelegt werden kann, die auf eine leere Zeichenfolge initialisiert:</span><span class="sxs-lookup"><span data-stu-id="586f7-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="586f7-124">Automatisch implementierte Eigenschaften sind Teil der Initialisierung eines Typs an, damit sie genau wie vor anderen Memberdefinitionen aufgenommen werden müssen `let` Bindungen und `do` Bindungen in einer Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="586f7-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="586f7-125">Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert nur ausgewertet wird, bei der Initialisierung und nicht jedes Mal, wenn die Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="586f7-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="586f7-126">Dieses Verhalten unterscheidet sich das Verhalten einer explizit implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="586f7-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="586f7-127">Was dies bedeutet, die den Code zum Initialisieren dieser Eigenschaften ist, wird an den Konstruktor einer Klasse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="586f7-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="586f7-128">Betrachten Sie den folgenden Code, der diese Abweichung zeigt:</span><span class="sxs-lookup"><span data-stu-id="586f7-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="586f7-129">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="586f7-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="586f7-130">Die Ausgabe der obige Code zeigt, dass der Wert des AutoProperty unverändert ist, wenn wird wiederholt aufgerufen, während die ExplicitProperty jedes Mal ändert, die sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="586f7-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="586f7-131">Dies zeigt, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht jedes Mal ausgewertet wird, wie die Gettermethode für die explizite Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="586f7-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
<span data-ttu-id="586f7-132">Es gibt einige Bibliotheken, z. B. Entity Framework (`System.Data.Entity`), benutzerdefinierte Vorgänge ausführen, in den Konstruktoren, die auch mit der Initialisierung des automatisch implementierte Eigenschaften nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="586f7-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="586f7-133">Verwenden Sie in diesen Fällen explizite Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="586f7-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="586f7-134">Eigenschaften können Mitglieder der Klassen, Strukturen, Unterscheidungs-Unions, Datensätze, Schnittstellen und Erweiterungen des Typs sein, und es können auch in Object-Ausdrücke definiert werden.</span><span class="sxs-lookup"><span data-stu-id="586f7-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="586f7-135">Attribute können auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="586f7-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="586f7-136">Schreiben Sie zum Anwenden eines Attributs auf eine Eigenschaft des Attributs in einer separaten Zeile vor der Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="586f7-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="586f7-137">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="586f7-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="586f7-138">Werden standardmäßig sind öffentlich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="586f7-138">By default, properties are public.</span></span> <span data-ttu-id="586f7-139">Zugriffsmodifizierer können auch auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="586f7-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="586f7-140">Zum Anwenden eines Zugriffsmodifizierers hinzufügen unmittelbar vor den Namen der Eigenschaft, wenn es für beide gelten sollen, ist die `get` und `set` Methoden vor dem Hinzufügen der `get` und `set` -Schlüsselwörter verwenden, wenn ein anderer Zugriff ist für jeden Accessor erforderlich.</span><span class="sxs-lookup"><span data-stu-id="586f7-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="586f7-141">Die *Zugriffsmodifizierer* kann einen der folgenden sein: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="586f7-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="586f7-142">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="586f7-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="586f7-143">Eigenschaft-Implementierungen werden jedes Mal ausgeführt, die eine Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="586f7-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="586f7-144">Statische und -Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="586f7-144">Static and Instance Properties</span></span>

<span data-ttu-id="586f7-145">Eigenschaften können statisch sein oder Instanzeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="586f7-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="586f7-146">Statische Eigenschaften aufgerufen werden können, ohne eine Instanz und werden für Werte, die dem Typ, nicht mit einzelnen Objekten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="586f7-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="586f7-147">Lassen Sie für statische Eigenschaften die Self-ID ein.</span><span class="sxs-lookup"><span data-stu-id="586f7-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="586f7-148">Die Self-ID ist für Instanzeigenschaften erforderlich.</span><span class="sxs-lookup"><span data-stu-id="586f7-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="586f7-149">Die folgende Definition für die statische Eigenschaft basiert darauf, dass ein Szenario in dem Sie ein statisches Feld `myStaticValue` d. h. der Sicherungsspeicher für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="586f7-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="586f7-150">Eigenschaften können auch arrayähnlichen, in diesem Fall werden sie aufgerufen werden *indizierte Eigenschaften*.</span><span class="sxs-lookup"><span data-stu-id="586f7-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="586f7-151">Weitere Informationen finden Sie unter [indizierte Eigenschaften](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="586f7-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="586f7-152">Typ-Anmerkung für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="586f7-152">Type Annotation for Properties</span></span>

<span data-ttu-id="586f7-153">In vielen Fällen der Compiler verfügt über genügend Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungsspeichers ableiten, aber Sie können den Typ explizit festlegen, durch das Hinzufügen einer Typ-Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="586f7-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="586f7-154">Set-Accessoren mit der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="586f7-154">Using Property set Accessors</span></span>

<span data-ttu-id="586f7-155">Sie Eigenschaften festlegen, die bieten `set` Accessoren mit der `<-` Operator.</span><span class="sxs-lookup"><span data-stu-id="586f7-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="586f7-156">Die Ausgabe ist **20**.</span><span class="sxs-lookup"><span data-stu-id="586f7-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="586f7-157">Abstrakte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="586f7-157">Abstract Properties</span></span>

<span data-ttu-id="586f7-158">Eigenschaften können abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="586f7-158">Properties can be abstract.</span></span> <span data-ttu-id="586f7-159">Wie bei Methoden `abstract` bedeutet lediglich, dass ein virtueller Dispatch, die der Eigenschaft zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="586f7-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="586f7-160">Abstrakte Eigenschaften können tatsächlich abstrakt sein, d. h. ohne Definition in der gleichen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="586f7-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="586f7-161">Klasse, die diese Eigenschaft enthält, ist daher eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="586f7-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="586f7-162">Alternativ kann nur abstrakt bedeuten, dass eine Eigenschaft virtuell ist und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="586f7-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="586f7-163">Beachten Sie, dass abstrakte Eigenschaften müssen nicht privat sein, wenn ein Accessor abstrakt ist, die andere auch muss sein abstrakt.</span><span class="sxs-lookup"><span data-stu-id="586f7-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="586f7-164">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="586f7-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="586f7-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="586f7-165">See also</span></span>

- [<span data-ttu-id="586f7-166">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="586f7-166">Members</span></span>](index.md)
- [<span data-ttu-id="586f7-167">Methoden</span><span class="sxs-lookup"><span data-stu-id="586f7-167">Methods</span></span>](methods.md)
