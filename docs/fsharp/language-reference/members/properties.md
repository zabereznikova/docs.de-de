---
title: Eigenschaften
description: Erfahren Sie F# mehr über Eigenschaften, die Elemente darstellen, die einem Objekt zugeordneten Werten entsprechen.
ms.date: 05/16/2016
ms.openlocfilehash: c71d61e033501c2d535b5582c82d36ed8cb2241b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216420"
---
# <a name="properties"></a><span data-ttu-id="77631-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77631-103">Properties</span></span>

<span data-ttu-id="77631-104">*Eigenschaften* sind Elemente, die mit einem Objekt verknüpfte Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="77631-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="77631-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="77631-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="77631-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77631-106">Remarks</span></span>

<span data-ttu-id="77631-107">Eigenschaften stellen die Beziehung "hat eine" in der objektorientierten Programmierung dar, die Daten darstellen, die Objektinstanzen zugeordnet sind, oder für statische Eigenschaften mit dem Typ.</span><span class="sxs-lookup"><span data-stu-id="77631-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="77631-108">Sie können Eigenschaften auf zwei Arten deklarieren, je nachdem, ob Sie den zugrunde liegenden Wert (auch als Sicherungs Speicher bezeichnet) für die Eigenschaft explizit angeben möchten, oder wenn Sie zulassen möchten, dass der Compiler automatisch den Sicherungs Speicher für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="77631-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="77631-109">Im Allgemeinen sollten Sie die explizitere Methode verwenden, wenn die Eigenschaft eine nicht triviale Implementierung hat, und die automatische Methode, wenn die Eigenschaft nur ein einfacher Wrapper für einen Wert oder eine Variable ist.</span><span class="sxs-lookup"><span data-stu-id="77631-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="77631-110">Verwenden Sie das `member` -Schlüsselwort, um eine Eigenschaft explizit zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="77631-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="77631-111">Auf diese deklarative Syntax folgt die Syntax, die die- `get` Methode `set` und die-Methode angibt, auch namens *Accessoren*.</span><span class="sxs-lookup"><span data-stu-id="77631-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="77631-112">Die verschiedenen Formen der expliziten Syntax, die im Syntax Abschnitt angezeigt werden, werden für Lese-/Schreib-, schreibgeschützte und Lese geschützte Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="77631-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="77631-113">Für schreibgeschützte Eigenschaften definieren Sie nur eine `get` -Methode. bei schreibgeschützten Eigenschaften definieren Sie nur eine `set` -Methode.</span><span class="sxs-lookup"><span data-stu-id="77631-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="77631-114">Beachten Sie, dass die alternative Syntax `get` es `set` Ihnen ermöglicht, Attribute und Zugriffsmodifizierer anzugeben, die für jeden Accessor unterschiedlich sind, wie im folgenden Code gezeigt, wenn eine Eigenschaft sowohl-als auch-Accessoren aufweist.</span><span class="sxs-lookup"><span data-stu-id="77631-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="77631-115">Für Lese-/Schreibeigenschaften, die `get` sowohl `set` die-als auch die `get` - `set` Methode aufweisen, kann die Reihenfolge von und umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="77631-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="77631-116">Alternativ können Sie die nur für `get` angezeigte Syntax und die Syntax angeben, die nur für angezeigt wird, anstatt die kombinierte Syntax zu `set` verwenden.</span><span class="sxs-lookup"><span data-stu-id="77631-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="77631-117">Dies erleichtert das Auskommentieren der einzelnen `get` -oder `set` -Methode, wenn dies etwas ist, was Sie möglicherweise tun müssen.</span><span class="sxs-lookup"><span data-stu-id="77631-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="77631-118">Diese Alternative zur Verwendung der kombinierten Syntax wird im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="77631-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="77631-119">Private Werte, die die Daten für Eigenschaften enthalten, werden als *Sicherungs Speicher*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="77631-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="77631-120">Damit der Compiler den Sicherungs Speicher automatisch erstellen kann, verwenden Sie die `member val`Schlüsselwörter, lassen Sie den Self-Identifier aus, und geben Sie dann einen Ausdruck an, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="77631-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="77631-121">Wenn die Eigenschaft änderbar sein soll, fügen `with get, set`Sie ein.</span><span class="sxs-lookup"><span data-stu-id="77631-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="77631-122">Der folgende Klassentyp enthält z. b. zwei automatisch implementierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="77631-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="77631-123">`Property1`ist schreibgeschützt und wird mit dem-Argument initialisiert, das für den primären Konstruktor bereit `Property2` gestellt wird, und ist eine festleg Bare Eigenschaft, die auf eine leere Zeichenfolge initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="77631-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="77631-124">Automatisch implementierte Eigenschaften sind Teil der Initialisierung eines Typs, sodass Sie vor allen anderen Element Definitionen eingeschlossen werden müssen, genauso wie `let` Bindungen und `do` Bindungen in einer Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="77631-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="77631-125">Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert, nur bei der Initialisierung ausgewertet wird und nicht jedes Mal, wenn auf die Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="77631-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="77631-126">Dieses Verhalten steht im Gegensatz zum Verhalten einer explizit implementierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77631-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="77631-127">Dies bedeutet, dass der Code zum Initialisieren dieser Eigenschaften dem Konstruktor einer Klasse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="77631-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="77631-128">Sehen Sie sich den folgenden Code an, der diesen Unterschied zeigt:</span><span class="sxs-lookup"><span data-stu-id="77631-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="77631-129">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="77631-129">**Output**</span></span>

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="77631-130">Die Ausgabe des obigen Codes zeigt, dass der Wert der AutoProperty unverändert ist, wenn er wiederholt aufgerufen wird, während die ExplicitProperty sich jedes Mal ändert, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="77631-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="77631-131">Dies zeigt, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht jedes Mal ausgewertet wird, wie die Gettermethode für die explizite Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77631-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="77631-132">Es gibt einige Bibliotheken, z. B. Entity Framework (`System.Data.Entity`), die benutzerdefinierte Vorgänge in den Konstruktoren ausführen, die auch mit der Initialisierung der automatisch implementierten Eigenschaften nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="77631-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="77631-133">Versuchen Sie in diesen Fällen, explizite Eigenschaften zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="77631-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="77631-134">Eigenschaften können Member von Klassen, Strukturen, Unterscheidungs-Unions, Datensätzen, Schnittstellen und Typerweiterungen sein und können auch in Objekt Ausdrücken definiert werden.</span><span class="sxs-lookup"><span data-stu-id="77631-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="77631-135">Attribute können auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="77631-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="77631-136">Wenn Sie ein Attribut auf eine Eigenschaft anwenden möchten, schreiben Sie das-Attribut in einer separaten Zeile vor der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="77631-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="77631-137">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="77631-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="77631-138">Standardmäßig sind Eigenschaften öffentlich.</span><span class="sxs-lookup"><span data-stu-id="77631-138">By default, properties are public.</span></span> <span data-ttu-id="77631-139">Zugriffsmodifizierer können auch auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="77631-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="77631-140">Wenn Sie einen Zugriffsmodifizierer anwenden möchten, fügen Sie ihn direkt vor dem Namen der Eigenschaft ein, wenn `get` er `set` auf die-Methode und die `get` - `set` Methode angewendet werden soll. Fügen Sie ihn vor den Schlüsselwörtern und vor erforderlich für jeden Accessor.</span><span class="sxs-lookup"><span data-stu-id="77631-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="77631-141">Der Zugriffsmodifizierer kann eine der folgenden `public`sein `private`: `internal`,,.</span><span class="sxs-lookup"><span data-stu-id="77631-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="77631-142">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="77631-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="77631-143">Eigenschafts Implementierungen werden jedes Mal ausgeführt, wenn auf eine Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="77631-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="77631-144">Statische Eigenschaften und Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="77631-144">Static and Instance Properties</span></span>

<span data-ttu-id="77631-145">Eigenschaften können statische Eigenschaften oder Instanzeigenschaften sein.</span><span class="sxs-lookup"><span data-stu-id="77631-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="77631-146">Statische Eigenschaften können ohne eine Instanz aufgerufen werden und werden für Werte verwendet, die dem Typ zugeordnet sind, nicht für einzelne Objekte.</span><span class="sxs-lookup"><span data-stu-id="77631-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="77631-147">Lassen Sie für statische Eigenschaften den selbst Bezeichner aus.</span><span class="sxs-lookup"><span data-stu-id="77631-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="77631-148">Der Self-Identifier ist für Instanzeigenschaften erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77631-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="77631-149">Die folgende statische Eigenschafts Definition basiert auf einem Szenario, in dem Sie über ein statisches Feld `myStaticValue` verfügen, das den Sicherungs Speicher für die Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="77631-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="77631-150">Eigenschaften können auch Array ähnlich sein. in diesem Fall werden Sie als *indizierte Eigenschaften*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="77631-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="77631-151">Weitere Informationen finden Sie unter [indizierte Eigenschaften](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="77631-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="77631-152">Typanmerkung für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77631-152">Type Annotation for Properties</span></span>

<span data-ttu-id="77631-153">In vielen Fällen verfügt der Compiler über ausreichende Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungs Speicher abzuleiten, aber Sie können den Typ explizit festlegen, indem Sie eine Typanmerkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="77631-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="77631-154">Verwenden von Eigenschaften Satz Accessoren</span><span class="sxs-lookup"><span data-stu-id="77631-154">Using Property set Accessors</span></span>

<span data-ttu-id="77631-155">Sie können Eigenschaften festlegen, die `set` Accessoren bereitstellen, `<-` indem Sie den-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="77631-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="77631-156">Die Ausgabe beträgt **20**.</span><span class="sxs-lookup"><span data-stu-id="77631-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="77631-157">Abstrakte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77631-157">Abstract Properties</span></span>

<span data-ttu-id="77631-158">Eigenschaften können abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="77631-158">Properties can be abstract.</span></span> <span data-ttu-id="77631-159">Wie bei Methoden bedeutet `abstract` nur, dass der Eigenschaft ein virtueller Verteiler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="77631-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="77631-160">Abstrakte Eigenschaften können wirklich abstrakt sein, d. h. ohne eine Definition in der gleichen Klasse.</span><span class="sxs-lookup"><span data-stu-id="77631-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="77631-161">Die Klasse, die eine solche Eigenschaft enthält, ist daher eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="77631-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="77631-162">Alternativ kann Abstract nur bedeuten, dass eine Eigenschaft virtuell ist, und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="77631-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="77631-163">Beachten Sie, dass abstrakte Eigenschaften nicht privat sein dürfen, und wenn ein Accessor abstrakt ist, muss der andere ebenfalls abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="77631-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="77631-164">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="77631-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="77631-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77631-165">See also</span></span>

- [<span data-ttu-id="77631-166">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="77631-166">Members</span></span>](index.md)
- [<span data-ttu-id="77631-167">Methoden</span><span class="sxs-lookup"><span data-stu-id="77631-167">Methods</span></span>](methods.md)
