---
title: Eigenschaften
description: 'Erfahren Sie mehr über die F #-Eigenschaften, die Elemente darstellen, die einem Objekt zugeordneten Werten entsprechen.'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740197"
---
# <a name="properties"></a><span data-ttu-id="2e93a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e93a-103">Properties</span></span>

<span data-ttu-id="2e93a-104">*Eigenschaften* sind Elemente, die mit einem Objekt verknüpfte Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e93a-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e93a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e93a-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="2e93a-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2e93a-106">Remarks</span></span>

<span data-ttu-id="2e93a-107">Eigenschaften stellen die Beziehung "hat eine" in der objektorientierten Programmierung dar, die Daten darstellen, die Objektinstanzen zugeordnet sind, oder für statische Eigenschaften mit dem Typ.</span><span class="sxs-lookup"><span data-stu-id="2e93a-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="2e93a-108">Sie können Eigenschaften auf zwei Arten deklarieren, je nachdem, ob Sie den zugrunde liegenden Wert (auch als Sicherungs Speicher bezeichnet) für die Eigenschaft explizit angeben möchten, oder wenn Sie zulassen möchten, dass der Compiler automatisch den Sicherungs Speicher für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="2e93a-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="2e93a-109">Im Allgemeinen sollten Sie die explizitere Methode verwenden, wenn die Eigenschaft eine nicht triviale Implementierung hat, und die automatische Methode, wenn die Eigenschaft nur ein einfacher Wrapper für einen Wert oder eine Variable ist.</span><span class="sxs-lookup"><span data-stu-id="2e93a-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="2e93a-110">Verwenden Sie das-Schlüsselwort, um eine Eigenschaft explizit zu deklarieren `member` .</span><span class="sxs-lookup"><span data-stu-id="2e93a-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="2e93a-111">Auf diese deklarative Syntax folgt die Syntax, die die `get` -Methode und die- `set` Methode angibt, auch namens *Accessoren*.</span><span class="sxs-lookup"><span data-stu-id="2e93a-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="2e93a-112">Die verschiedenen Formen der expliziten Syntax, die im Syntax Abschnitt angezeigt werden, werden für Lese-/Schreib-, schreibgeschützte und Lese geschützte Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e93a-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="2e93a-113">Für schreibgeschützte Eigenschaften definieren Sie nur eine- `get` Methode. bei schreibgeschützten Eigenschaften definieren Sie nur eine- `set` Methode.</span><span class="sxs-lookup"><span data-stu-id="2e93a-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="2e93a-114">Beachten Sie, dass `get` `set` die alternative Syntax es Ihnen ermöglicht, Attribute und Zugriffsmodifizierer anzugeben, die für jeden Accessor unterschiedlich sind, wie im folgenden Code gezeigt, wenn eine Eigenschaft sowohl-als auch-Accessoren aufweist.</span><span class="sxs-lookup"><span data-stu-id="2e93a-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="2e93a-115">Für Lese-/Schreibeigenschaften, die sowohl die-als auch die- `get` `set` Methode aufweisen, kann die Reihenfolge von `get` und `set` umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="2e93a-116">Alternativ können Sie die nur für angezeigte Syntax `get` und die Syntax angeben, die nur für angezeigt wird, `set` anstatt die kombinierte Syntax zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="2e93a-117">Dies erleichtert das Auskommentieren der einzelnen-oder- `get` `set` Methode, wenn dies etwas ist, was Sie möglicherweise tun müssen.</span><span class="sxs-lookup"><span data-stu-id="2e93a-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="2e93a-118">Diese Alternative zur Verwendung der kombinierten Syntax wird im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2e93a-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="2e93a-119">Private Werte, die die Daten für Eigenschaften enthalten, werden als *Sicherungs Speicher* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2e93a-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="2e93a-120">Damit der Compiler den Sicherungs Speicher automatisch erstellen kann, verwenden Sie die Schlüsselwörter `member val` , lassen Sie den Self-Identifier aus, und geben Sie dann einen Ausdruck an, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2e93a-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="2e93a-121">Wenn die Eigenschaft änderbar sein soll, fügen Sie ein `with get, set` .</span><span class="sxs-lookup"><span data-stu-id="2e93a-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="2e93a-122">Der folgende Klassentyp enthält z. b. zwei automatisch implementierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2e93a-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="2e93a-123">`Property1` ist schreibgeschützt und wird mit dem-Argument initialisiert, das für den primären Konstruktor bereitgestellt wird, und `Property2` ist eine festleg Bare Eigenschaft, die auf eine leere Zeichenfolge initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="2e93a-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="2e93a-124">Automatisch implementierte Eigenschaften sind Teil der Initialisierung eines Typs, sodass Sie vor allen anderen Element Definitionen eingeschlossen werden müssen, genauso wie `let` Bindungen und `do` Bindungen in einer Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="2e93a-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="2e93a-125">Beachten Sie, dass der Ausdruck, der eine automatisch implementierte Eigenschaft initialisiert, nur bei der Initialisierung ausgewertet wird und nicht jedes Mal, wenn auf die Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="2e93a-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="2e93a-126">Dieses Verhalten steht im Gegensatz zum Verhalten einer explizit implementierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e93a-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="2e93a-127">Dies bedeutet, dass der Code zum Initialisieren dieser Eigenschaften dem Konstruktor einer Klasse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2e93a-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="2e93a-128">Sehen Sie sich den folgenden Code an, der diesen Unterschied zeigt:</span><span class="sxs-lookup"><span data-stu-id="2e93a-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

<span data-ttu-id="2e93a-129">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="2e93a-129">**Output**</span></span>

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="2e93a-130">Die Ausgabe des vorangehenden Codes zeigt, dass der Wert von autoproperty unverändert ist, wenn er wiederholt aufgerufen wird, während die explizproperty bei jedem Aufruf geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2e93a-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="2e93a-131">Dies zeigt, dass der Ausdruck für eine automatisch implementierte Eigenschaft nicht jedes Mal ausgewertet wird, wie dies die Getter-Methode für die explizite Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="2e93a-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="2e93a-132">Es gibt einige Bibliotheken, z. b. die Entity Framework ( `System.Data.Entity` ), die benutzerdefinierte Vorgänge in Basisklassenkonstruktoren ausführen, die nicht gut mit der Initialisierung automatisch implementierter Eigenschaften funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2e93a-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="2e93a-133">Versuchen Sie in diesen Fällen, explizite Eigenschaften zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="2e93a-134">Eigenschaften können Member von Klassen, Strukturen, Unterscheidungs-Unions, Datensätzen, Schnittstellen und Typerweiterungen sein und können auch in Objekt Ausdrücken definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="2e93a-135">Attribute können auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="2e93a-136">Wenn Sie ein Attribut auf eine Eigenschaft anwenden möchten, schreiben Sie das-Attribut in einer separaten Zeile vor der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e93a-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="2e93a-137">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2e93a-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="2e93a-138">Standardmäßig sind Eigenschaften öffentlich.</span><span class="sxs-lookup"><span data-stu-id="2e93a-138">By default, properties are public.</span></span> <span data-ttu-id="2e93a-139">Zugriffsmodifizierer können auch auf Eigenschaften angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="2e93a-140">Wenn Sie einen Zugriffsmodifizierer anwenden möchten, fügen Sie ihn direkt vor dem Namen der Eigenschaft ein, wenn er auf die `get` -Methode und die-Methode angewendet werden soll `set` . Fügen Sie ihn vor den `get` Schlüsselwörtern und hinzu, `set` Wenn für jeden Accessor ein anderer Zugriff erforderlich</span><span class="sxs-lookup"><span data-stu-id="2e93a-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="2e93a-141">Der *accessibility-modifier* Zugriffsmodifizierer kann eine der folgenden sein: `public` , `private` , `internal` .</span><span class="sxs-lookup"><span data-stu-id="2e93a-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="2e93a-142">Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="2e93a-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="2e93a-143">Eigenschafts Implementierungen werden jedes Mal ausgeführt, wenn auf eine Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="2e93a-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="2e93a-144">Statische Eigenschaften und Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e93a-144">Static and Instance Properties</span></span>

<span data-ttu-id="2e93a-145">Eigenschaften können statische Eigenschaften oder Instanzeigenschaften sein.</span><span class="sxs-lookup"><span data-stu-id="2e93a-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="2e93a-146">Statische Eigenschaften können ohne eine Instanz aufgerufen werden und werden für Werte verwendet, die dem Typ zugeordnet sind, nicht für einzelne Objekte.</span><span class="sxs-lookup"><span data-stu-id="2e93a-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="2e93a-147">Lassen Sie für statische Eigenschaften den selbst Bezeichner aus.</span><span class="sxs-lookup"><span data-stu-id="2e93a-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="2e93a-148">Der Self-Identifier ist für Instanzeigenschaften erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e93a-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="2e93a-149">Die folgende statische Eigenschafts Definition basiert auf einem Szenario, in dem Sie über ein statisches Feld verfügen `myStaticValue` , das den Sicherungs Speicher für die Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="2e93a-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="2e93a-150">Eigenschaften können auch Array ähnlich sein. in diesem Fall werden Sie als *indizierte Eigenschaften* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2e93a-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="2e93a-151">Weitere Informationen finden Sie unter [indizierte Eigenschaften](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2e93a-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="2e93a-152">Typanmerkung für Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e93a-152">Type Annotation for Properties</span></span>

<span data-ttu-id="2e93a-153">In vielen Fällen verfügt der Compiler über ausreichende Informationen, um den Typ einer Eigenschaft vom Typ des Sicherungs Speicher abzuleiten, aber Sie können den Typ explizit festlegen, indem Sie eine Typanmerkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e93a-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="2e93a-154">Verwenden von Eigenschaften Satz Accessoren</span><span class="sxs-lookup"><span data-stu-id="2e93a-154">Using Property set Accessors</span></span>

<span data-ttu-id="2e93a-155">Sie können Eigenschaften festlegen, die `set` Accessoren bereitstellen, indem Sie den- `<-` Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e93a-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="2e93a-156">Die Ausgabe beträgt **20**.</span><span class="sxs-lookup"><span data-stu-id="2e93a-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="2e93a-157">Abstrakte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e93a-157">Abstract Properties</span></span>

<span data-ttu-id="2e93a-158">Eigenschaften können abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="2e93a-158">Properties can be abstract.</span></span> <span data-ttu-id="2e93a-159">Wie bei Methoden `abstract` bedeutet nur, dass der Eigenschaft ein virtueller Verteiler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2e93a-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="2e93a-160">Abstrakte Eigenschaften können wirklich abstrakt sein, d. h. ohne eine Definition in der gleichen Klasse.</span><span class="sxs-lookup"><span data-stu-id="2e93a-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="2e93a-161">Die Klasse, die eine solche Eigenschaft enthält, ist daher eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="2e93a-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="2e93a-162">Alternativ kann Abstract nur bedeuten, dass eine Eigenschaft virtuell ist, und in diesem Fall muss eine Definition in der gleichen Klasse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2e93a-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="2e93a-163">Beachten Sie, dass abstrakte Eigenschaften nicht privat sein dürfen, und wenn ein Accessor abstrakt ist, muss der andere ebenfalls abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="2e93a-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="2e93a-164">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2e93a-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="2e93a-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e93a-165">See also</span></span>

- [<span data-ttu-id="2e93a-166">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="2e93a-166">Members</span></span>](index.md)
- [<span data-ttu-id="2e93a-167">Methoden</span><span class="sxs-lookup"><span data-stu-id="2e93a-167">Methods</span></span>](methods.md)
