---
title: nameof – C#-Referenz
ms.custom: seodec18
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 349cbf4e918d97a5a2a5c1e873d7fa114be8e2db
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306632"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="1843c-102">nameof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1843c-102">nameof (C# Reference)</span></span>

<span data-ttu-id="1843c-103">Wird verwendet, um den einfachen (nicht qualifizierten) Zeichenfolgennamen einer Variablen, eines Typs oder eines Members abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1843c-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>

<span data-ttu-id="1843c-104">Beim Melden von Fehlern im Code, Einbinden von MVC-Links (Model-View-Controller) und Auslösen von durch Eigenschaften geänderten Ereignissen usw. ist es oft erforderlich, den Zeichenfolgennamen einer Methode zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="1843c-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="1843c-105">Mithilfe von `nameof` bleibt der Code beim Umbenennen von Definitionen gültig.</span><span class="sxs-lookup"><span data-stu-id="1843c-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="1843c-106">Bisher mussten zum Verweisen auf Definitionen Zeichenfolgenliterale verwendet werden; dies ist jedoch fehleranfällig, wenn Codeelemente umbenannt werden, da Tools diese Zeichenfolgenliterale nicht überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="1843c-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>

<span data-ttu-id="1843c-107">Ein `nameof`-Ausdruck hat die folgende Form:</span><span class="sxs-lookup"><span data-stu-id="1843c-107">A `nameof` expression has this form:</span></span>

```csharp
if (x == null) throw new ArgumentNullException(nameof(x));
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"
```

## <a name="key-use-cases"></a><span data-ttu-id="1843c-108">Wichtige Einsatzbeispiele</span><span class="sxs-lookup"><span data-stu-id="1843c-108">Key Use Cases</span></span>

<span data-ttu-id="1843c-109">Diese Beispiele zeigen die wichtigsten Anwendungsfälle für `nameof`.</span><span class="sxs-lookup"><span data-stu-id="1843c-109">These examples show the key use cases for `nameof`.</span></span>

<span data-ttu-id="1843c-110">Überprüfen von Parametern:</span><span class="sxs-lookup"><span data-stu-id="1843c-110">Validate parameters:</span></span>

 ```csharp
void f(string s) {
    if (s == null) throw new ArgumentNullException(nameof(s));
}
```

<span data-ttu-id="1843c-111">MVC-Aktionslinks:</span><span class="sxs-lookup"><span data-stu-id="1843c-111">MVC Action links:</span></span>

```html
<%= Html.ActionLink("Sign up",
             @typeof(UserController),
             @nameof(UserController.SignUp))
%>
```

<span data-ttu-id="1843c-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="1843c-112">INotifyPropertyChanged:</span></span>

```csharp
int p {
    get { return this.p; }
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too
}
```

<span data-ttu-id="1843c-113">XAML-Abhängigkeitseigenschaft:</span><span class="sxs-lookup"><span data-stu-id="1843c-113">XAML dependency property:</span></span>

```csharp
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));
```

<span data-ttu-id="1843c-114">Protokollieren:</span><span class="sxs-lookup"><span data-stu-id="1843c-114">Logging:</span></span>

```csharp
void f(int i) {
    Log(nameof(f), "method entry");
}
```

<span data-ttu-id="1843c-115">Attribute:</span><span class="sxs-lookup"><span data-stu-id="1843c-115">Attributes:</span></span>

```csharp
[DebuggerDisplay("={" + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

## <a name="examples"></a><span data-ttu-id="1843c-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1843c-116">Examples</span></span>

<span data-ttu-id="1843c-117">Einige C#-Beispiele:</span><span class="sxs-lookup"><span data-stu-id="1843c-117">Some C# examples:</span></span>

```csharp
using Stuff = Some.Cool.Functionality
class C {
    static int Method1 (string x, int y) {}
    static int Method1 (string x, string y) {}
    int Method2 (int z) {}
    string f<T>() => nameof(T);
}

var c = new C()

class Test {
    static void Main (string[] args) {
        Console.WriteLine(nameof(C)); // -> "C"
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]
        Console.WriteLine(nameof(f)); // -> "f"
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]
        // Console.WriteLine(nameof(f<>)); -> [syntax error]
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]
    }
}
```

## <a name="remarks"></a><span data-ttu-id="1843c-118">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="1843c-118">Remarks</span></span>

<span data-ttu-id="1843c-119">Das Argument für `nameof` muss ein einfacher Name, qualifizierter Name, Memberzugriff, Basiszugriff mit angegebenem Member oder dieser Zugriff mit angegebenem Member sein.</span><span class="sxs-lookup"><span data-stu-id="1843c-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="1843c-120">Der Argumentausdruck identifiziert eine Codedefinition, wird jedoch niemals ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1843c-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>

<span data-ttu-id="1843c-121">Da das Argument syntaktisch ein Ausdruck sein muss, ist vieles unzulässig; eine Auflistung wäre jedoch nicht sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="1843c-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="1843c-122">Fehler werden bspw. erzeugt durch: vordefinierte Typen (z. B. `int` oder `void`), auf NULL festlegbare Typen (`Point?`), Arraytypen (`Customer[,]`), Zeigertypen (`Buffer*`), qualifizierte Aliase (`A::B`), ungebundene generische Typen (`Dictionary<,>`), Vorverarbeitungssymbole (`DEBUG`) und Bezeichnungen (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="1843c-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>

<span data-ttu-id="1843c-123">Wenn Sie den vollqualifizierten Namen abrufen müssen, können Sie den `typeof`-Ausdruck zusammen mit `nameof` verwenden.</span><span class="sxs-lookup"><span data-stu-id="1843c-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="1843c-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1843c-124">For example:</span></span>

```csharp
class C {
    void f(int i) {
        Log($"{typeof(C)}.{nameof(f)}", "method entry");
    }
}
```

<span data-ttu-id="1843c-125">Leider ist `typeof` kein konstanter Ausdruck wie `nameof`, sodass `typeof` nicht zusammen mit `nameof` an den gleichen Orten wie `nameof` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1843c-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="1843c-126">Beispielsweise würde Folgendes einen Kompilierungsfehler CS0182 erzeugen:</span><span class="sxs-lookup"><span data-stu-id="1843c-126">For example, the following would cause a CS0182 compile error:</span></span>

```csharp
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

<span data-ttu-id="1843c-127">In den Beispielen sehen Sie, dass Sie einen Typnamen verwenden und auf den Namen einer Instanzmethode zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1843c-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="1843c-128">Sie müssen nicht über eine Instanz des Typs verfügen, wie es in ausgewerteten Ausdrücken erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1843c-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="1843c-129">Die Verwendung des Typnamens kann in einigen Situationen sehr praktisch sein, und da Sie nur auf den Namen verweisen und keine Instanzdaten verwenden, müssen Sie keine Instanzvariable und keinen Ausdruck erfinden.</span><span class="sxs-lookup"><span data-stu-id="1843c-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>

<span data-ttu-id="1843c-130">Sie können auf die Member einer Klasse in Attributausdrücken in der Klasse verweisen.</span><span class="sxs-lookup"><span data-stu-id="1843c-130">You can reference the members of a class in attribute expressions on the class.</span></span>

<span data-ttu-id="1843c-131">Es gibt keine Möglichkeit, Signaturinformationen wie z. B. „`Method1 (str, str)`“ abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1843c-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="1843c-132">Dazu müssen Sie z. B. einen Ausdruck (`Expression e = () => A.B.Method1("s1", "s2")`) verwenden und die MemberInfo aus der resultierenden Ausdrucksbaumstruktur abrufen.</span><span class="sxs-lookup"><span data-stu-id="1843c-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="1843c-133">Sprachspezifikationen</span><span class="sxs-lookup"><span data-stu-id="1843c-133">Language Specifications</span></span>

<span data-ttu-id="1843c-134">Weitere Informationen finden Sie unter [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1843c-134">For more information, see [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="1843c-135">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="1843c-135">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1843c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1843c-136">See also</span></span>

- [<span data-ttu-id="1843c-137">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1843c-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="1843c-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1843c-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1843c-139">typeof</span><span class="sxs-lookup"><span data-stu-id="1843c-139">typeof</span></span>](../operators/type-testing-and-conversion-operators.md#typeof-operator)
