---
title: Eigenschaften
description: Erfahren Sie mehr über C#-Eigenschaften, die Funktionen für die Validierung, berechnete Werte, die verzögerte Auswertung und Benachrichtigungen für Eigenschaftsänderungen umfassen.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 04/03/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 6950d25a-bba1-4744-b7c7-a3cc90438c55
ms.openlocfilehash: 2a25919048f94211b1696ac8c8471a14ce6e15c5
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="properties"></a><span data-ttu-id="8b5b1-104">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b5b1-104">Properties</span></span>

<span data-ttu-id="8b5b1-105">Eigenschaften sind Bürger erster Klasse in C#.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-105">Properties are first class citizens in C#.</span></span> <span data-ttu-id="8b5b1-106">Die Sprache definiert die Syntax, mit der Entwickler Code schreiben können, der genau ihre Entwurfsabsicht ausdrückt.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-106">The language defines syntax that enables developers to write code that accurately expresses their design intent.</span></span>

<span data-ttu-id="8b5b1-107">Eigenschaften verhalten sich wie Felder, wenn darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-107">Properties behave like fields when they are accessed.</span></span>
<span data-ttu-id="8b5b1-108">Jedoch sind Eigenschaften im Gegensatz zu Feldern mit Accessoren implementiert, die die ausgeführten Anweisungen definieren, wenn auf eine Eigenschaft zugegriffen oder sie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-108">However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.</span></span>

## <a name="property-syntax"></a><span data-ttu-id="8b5b1-109">Eigenschaftssyntax</span><span class="sxs-lookup"><span data-stu-id="8b5b1-109">Property Syntax</span></span>

<span data-ttu-id="8b5b1-110">Die Syntax für Eigenschaften ist eine natürliche Erweiterung von Feldern.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-110">The syntax for properties is a natural extension to fields.</span></span> <span data-ttu-id="8b5b1-111">Ein Feld definiert einen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-111">A field defines a storage location:</span></span>

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-112">Eine Eigenschaftendefinition enthält Deklarationen für einen `get`- und `set`-Accessor, der den Wert dieser Eigenschaft abruft oder zuweist:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-112">A property definition contains declarations for a `get` and `set` accessor that retrieves and assigns the value of that property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-113">Die oben dargestellte Syntax ist die *Auto-Eigenschaft*-Syntax.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-113">The syntax shown above is the *auto property* syntax.</span></span> <span data-ttu-id="8b5b1-114">Der Compiler generiert den Speicherort für das Feld, das die Eigenschaft sichert.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-114">The compiler generates the storage location for the field that backs up the property.</span></span> <span data-ttu-id="8b5b1-115">Der Compiler implementiert außerdem den Text der `get`- und `set`-Accessoren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-115">The compiler also implements the body of the `get` and `set` accessors.</span></span>

<span data-ttu-id="8b5b1-116">In einigen Fällen müssen Sie eine Eigenschaft auf einen anderen Wert als den Standardwert für seinen Datentyp initialisieren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-116">Sometimes, you need to initialize a property to a value other than the default for its type.</span></span>  <span data-ttu-id="8b5b1-117">C# ermöglicht dies, indem nach der schließenden Klammer für die Eigenschaft ein Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-117">C# enables that by setting a value after the closing brace for the property.</span></span> <span data-ttu-id="8b5b1-118">Möglicherweise bevorzugen Sie den Anfangswert für die Eigenschaft `FirstName` als leere Zeichenfolge und nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-118">You may prefer the initial value for the `FirstName` property to be the empty string rather than `null`.</span></span> <span data-ttu-id="8b5b1-119">Sie würden dies wie unten dargestellt angeben:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-119">You would specify that as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; } = string.Empty;

    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-120">Dies eignet sich am besten für schreibgeschützte Eigenschaften, wie Sie später in diesem Artikel sehen werden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-120">This is most useful for read-only properties, as you'll see later in this topic.</span></span>

<span data-ttu-id="8b5b1-121">Sie können den Speicher auch selbst definieren, wie unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-121">You can also define the storage yourself, as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set { firstName = value; }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-122">Wenn die Implementierung einer Eigenschaft ein einzelner Ausdruck ist, können Sie *Ausdruckskörpermember* für die Getter oder Setter verwenden:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-122">When a property implementation is a single expression, you can use *expression-bodied members* for the getter or setter:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set => firstName = value;
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-123">Diese vereinfachte Syntax wird gegebenenfalls in diesem Thema verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-123">This simplified syntax will be used where applicable throughout this topic.</span></span>

<span data-ttu-id="8b5b1-124">Die oben gezeigte Eigenschaftendefinition ist eine Schreib-Lese-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-124">The property definition shown above is a read-write property.</span></span> <span data-ttu-id="8b5b1-125">Beachten Sie das Schlüsselwort `value` im set-Accessor.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-125">Notice the keyword `value` in the set accessor.</span></span> <span data-ttu-id="8b5b1-126">Der `set`-Accessor verfügt immer über einen einzelnen Parameter namens `value`.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-126">The `set` accessor always has a single parameter named `value`.</span></span> <span data-ttu-id="8b5b1-127">Der `get`-Accessor muss einen Wert zurückgeben, der in den Typ der Eigenschaft konvertiert werden kann (`string` in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="8b5b1-127">The `get` accessor must return a value that is convertible to the type of the property (`string` in this example).</span></span>
 
<span data-ttu-id="8b5b1-128">Das sind die Grundlagen der Syntax.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-128">That's the basics of the syntax.</span></span> <span data-ttu-id="8b5b1-129">Es gibt viele verschiedene Varianten, die eine Vielzahl von verschiedenen Entwürfen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-129">There are many different variations that support a variety of different design idioms.</span></span> <span data-ttu-id="8b5b1-130">Lassen Sie uns diese erforschen, und lernen Sie die Syntaxoptionen für jede kennen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-130">Let's explore those, and learn the syntax options for each.</span></span>

## <a name="scenarios"></a><span data-ttu-id="8b5b1-131">Szenarien</span><span class="sxs-lookup"><span data-stu-id="8b5b1-131">Scenarios</span></span>

<span data-ttu-id="8b5b1-132">In den Beispielen oben wurde eine der einfachsten Fälle von Eigenschaftendefinition gezeigt: eine Schreib-Lese-Eigenschaft ohne Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-132">The examples above showed one of the simplest cases of property definition: a read-write property with no validation.</span></span> <span data-ttu-id="8b5b1-133">Durch das Schreiben des Codes, den Sie in den `get`- und `set`-Accessoren möchten, können Sie viele verschiedene Szenarios erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-133">By writing the code you want in the `get` and `set` accessors, you can create many different scenarios.</span></span>

### <a name="validation"></a><span data-ttu-id="8b5b1-134">Validierung</span><span class="sxs-lookup"><span data-stu-id="8b5b1-134">Validation</span></span>

<span data-ttu-id="8b5b1-135">Sie können Code im `set`-Accessor schreiben, um sicherzustellen, dass die durch eine Eigenschaft dargestellten Werte immer gültig sind.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-135">You can write code in the `set` accessor to ensure that the values represented by a property are always valid.</span></span> <span data-ttu-id="8b5b1-136">Angenommen, eine Regel für die `Person`-Klasse ist z.B., dass der Name nicht leer oder kein Leerzeichen sein kann.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-136">For example, suppose one rule for the `Person` class is that the name cannot be blank, or whitespace.</span></span> <span data-ttu-id="8b5b1-137">Sie würden das wie folgt schreiben:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-137">You would write that as follows:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            firstName = value;
        }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-138">Das obige Beispiel erzwingt die Regel, dass der erste Name nicht leer oder kein Leerzeichen sein darf.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-138">The example above enforces the rule that the first name must not be blank, or whitespace.</span></span> <span data-ttu-id="8b5b1-139">Wenn ein Entwickler schreibt</span><span class="sxs-lookup"><span data-stu-id="8b5b1-139">If a developer writes</span></span>

```csharp
hero.FirstName = "";
```

<span data-ttu-id="8b5b1-140">Die Zuweisung löst eine `ArgumentException` aus.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-140">That assignment throws an `ArgumentException`.</span></span> <span data-ttu-id="8b5b1-141">Da der set-Accessor einen void-Rückgabetyp aufweisen muss, melden Sie Fehler im set-Accessor durch Auslösen einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-141">Because a property set accessor must have a void return type, you report errors in the set accessor by throwing an exception.</span></span>

<span data-ttu-id="8b5b1-142">Das ist ein einfacher Fall der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-142">That is a simple case of validation.</span></span> <span data-ttu-id="8b5b1-143">Sie können die gleiche Syntax auf alles andere in Ihrem Szenario erweitern, was benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-143">You can extend this same syntax to anything needed in your scenario.</span></span> <span data-ttu-id="8b5b1-144">Sie können die Beziehungen zwischen unterschiedlichen Eigenschaften oder gegen externe Bedingungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-144">You can check the relationships between different properties, or validate against any external conditions.</span></span> <span data-ttu-id="8b5b1-145">Gültige C#-Anweisungen sind in einem Eigenschaftenaccessor gültig.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-145">Any valid C# statements are valid in a property accessor.</span></span>

### <a name="read-only"></a><span data-ttu-id="8b5b1-146">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8b5b1-146">Read-only</span></span>

<span data-ttu-id="8b5b1-147">Bis zu diesem Zeitpunkt sind alle Eigenschaftsdefinitionen, die Sie gesehen haben Lese-/Schreibeigenschaften mit öffentlichen Accessoren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-147">Up to this point, all the property definitions you have seen are read/write properties with public accessors.</span></span> <span data-ttu-id="8b5b1-148">Dies sind nicht die einzige gültigen Eingabehilfen für Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-148">That's not the only valid accessibility for properties.</span></span>
<span data-ttu-id="8b5b1-149">Sie können schreibgeschützte Eigenschaften erstellen, oder den set- und get-Accessoren verschiedene Eingabehilfen geben.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-149">You can create read-only properties, or give different accessibility to the set and get accessors.</span></span> <span data-ttu-id="8b5b1-150">Angenommen, Ihre `Person`-Klasse sollte nur die Änderung des Werts der `FirstName`-Eigenschaft von anderen Methoden in dieser Klasse ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-150">Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class.</span></span> <span data-ttu-id="8b5b1-151">Sie konnten dem set-Accessor `private`-Eingabehilfen anstelle von `public` geben:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-151">You could give the set accessor `private` accessibility instead of `public`:</span></span>

```csharp
public class Person
{
    public string FirstName { get; private set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-152">Nun, kann auf die `FirstName`-Eigenschaft von einem beliebigen Code zugegriffen werden, aber es kann nur von einem anderem Code in der `Person`-Klasse zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-152">Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.</span></span>

<span data-ttu-id="8b5b1-153">Sie können einen restriktiven Zugriffsmodifizierer zum set- oder get-Accessor hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-153">You can add any restrictive access modifier to either the set or get accessors.</span></span> <span data-ttu-id="8b5b1-154">Jeder Zugriffsmodifizierer, den Sie auf den einzelnen Accessor platzieren, muss eingeschränkter sein als der Zugriffsmodifizierer für die Eigenschaftsdefinition.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-154">Any access modifier you place on the individual accessor must be more limited than the access modifier on the property definition.</span></span> <span data-ttu-id="8b5b1-155">Das Obige ist zulässig, da die `FirstName`-Eigenschaft `public` ist, aber der set-Accessor ist `private`.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-155">The above is legal because the `FirstName` property is `public`, but the set accessor is `private`.</span></span> <span data-ttu-id="8b5b1-156">Sie können keine `private`-Eigenschaft mit einem `public`-Accessor deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-156">You could not declare a `private` property with a `public` accessor.</span></span> <span data-ttu-id="8b5b1-157">Eigenschaftendeklarationen können ebenfalls als `protected`, `internal`, `protected internal`, `private protected` oder sogar `private` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-157">Property declarations can also be declared `protected`, `internal`, `protected internal`, `private protected` or even `private`.</span></span>   

<span data-ttu-id="8b5b1-158">Es ist auch zulässig, den restriktiveren Modifizierer auf dem `get`-Accessor zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-158">It is also legal to place the more restrictive modifier on the `get` accessor.</span></span> <span data-ttu-id="8b5b1-159">Sie verfügen z.B. über eine `public`-Eigenschaft, schränken jedoch den `get`-Accessor auf `private` ein.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-159">For example, you could have a `public` property, but restrict the `get` accessor to `private`.</span></span> <span data-ttu-id="8b5b1-160">Dieses Szenario wird in der Praxis nur selten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-160">That scenario is rarely done in practice.</span></span>

<span data-ttu-id="8b5b1-161">Sie können auch Änderungen an einer Eigenschaft beschränken, sodass sie nur in einem Konstruktor oder einem Eigenschafteninitialisierer festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-161">You can also restrict modifications to a property so that it can only be set in a constructor or a property initializer.</span></span> <span data-ttu-id="8b5b1-162">Sie können die `Person`-Klasse daher wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-162">You can modify the `Person` class so as follows:</span></span>

```csharp
public class Person
{
    public Person(string firstName)
    {
        this.FirstName = firstName;
    }

    public string FirstName { get; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-163">Diese Funktion wird am häufigsten für die Initialisierung von Auflistungen verwendet, die als schreibgeschützte Eigenschaften verfügbar gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-163">This feature is most commonly used for initializing collections that are exposed as read-only properties:</span></span>

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a><span data-ttu-id="8b5b1-164">Berechnete Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b5b1-164">Computed Properties</span></span>

<span data-ttu-id="8b5b1-165">Eine Eigenschaft muss nicht einfach den Wert eines Memberfelds zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-165">A property does not need to simply return the value of a member field.</span></span> <span data-ttu-id="8b5b1-166">Sie können Eigenschaften erstellen, die einen berechneten Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-166">You can create properties that return a computed value.</span></span> <span data-ttu-id="8b5b1-167">Lassen Sie uns das `Person`-Objekt so erweitern, dass es den vollständigen Namen zurückgibt, berechnet durch die Verkettung des ersten und letzten Namens:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-167">Let's expand the `Person` object to return the full name, computed by concatenating the first and last names:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName { get { return $"{FirstName} {LastName}"; } }
}
```

<span data-ttu-id="8b5b1-168">Im Beispiel oben wird das Feature [Zeichenfolgeninterpolation](../csharp/language-reference/tokens/interpolated.md) verwendet, um die formatierte Zeichenfolge für den vollständigen Namen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-168">The example above uses the [string interpolation](../csharp/language-reference/tokens/interpolated.md) feature to create the formatted string for the full name.</span></span>

<span data-ttu-id="8b5b1-169">Sie können auch *Ausdruckskörpermember* verwenden, was eine kompaktere Möglichkeit zum Erstellen der berechneten `FullName`-Eigenschaft darstellt:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-169">You can also use *expression-bodied members*, which provides a more succinct way to create the computed `FullName` property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
<span data-ttu-id="8b5b1-170">*Ausdruckskörpermember* verwenden die Syntax von *Lambdaausdrücken* zum Definieren einer Methode, die einen einzelnen Ausdruck enthält.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-170">*Expression-bodied members* use the *lambda expression* syntax to define a method that contain a single expression.</span></span> <span data-ttu-id="8b5b1-171">Hier gibt dieser Ausdruck den vollständigen Namen für das Person-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-171">Here, that expression returns the full name for the person object.</span></span>

### <a name="lazy-evaluated-properties"></a><span data-ttu-id="8b5b1-172">Verzögert ausgewertete Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b5b1-172">Lazy Evaluated Properties</span></span>

<span data-ttu-id="8b5b1-173">Sie können das Konzept einer berechneten Eigenschaft mit dem Speicher mischen und eine *verzögert ausgewertete Eigenschaft* erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-173">You can mix the concept of a computed property with storage and create a *lazy evaluated property*.</span></span>  <span data-ttu-id="8b5b1-174">Sie können z.B. die `FullName`-Eigenschaft so aktualisieren, dass die Zeichenfolgenformatierung nur beim ersten Zugriff umgesetzt wird:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-174">For example, you could update the `FullName` property so that the string formatting only happened the first time it was accessed:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="8b5b1-175">Der obige Code enthält jedoch einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-175">The above code contains a bug though.</span></span> <span data-ttu-id="8b5b1-176">Wenn der Code den Wert der `FirstName`- oder `LastName`-Eigenschaft aktualisiert, ist das zuvor ausgewertete `fullName`-Feld ungültig.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-176">If code updates the value of either the `FirstName` or `LastName` property, the previously evaluated `fullName` field is invalid.</span></span> <span data-ttu-id="8b5b1-177">Sie müssen die `set`-Accessoren der `FirstName`- und `LastName`-Eigenschaft aktualisieren, damit das `fullName`-Feld erneut berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="8b5b1-177">You need to update the `set` accessors of the `FirstName` and `LastName` property so that the `fullName` field is calculated again:</span></span>

```csharp
public class Person
{
    private string firstName;
    public string FirstName
    {
        get => firstName;
        set
        {
            firstName = value;
            fullName = null;
        }
    }

    private string lastName;
    public string LastName
    {
        get => lastName;
        set
        {
            lastName = value;
            fullName = null;
        }
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="8b5b1-178">Diese endgültige Version wertet die `FullName`-Eigenschaft nur bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-178">This final version evaluates the `FullName` property only when needed.</span></span>
<span data-ttu-id="8b5b1-179">Wenn die zuvor berechnete Version gültig ist, wird sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-179">If the previously calculated version is valid, it's used.</span></span> <span data-ttu-id="8b5b1-180">Wenn eine andere Änderung des Zustands die zuvor berechnete Version ungültig macht, wird sie neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-180">If another state change invalidates the previously calculated version, it will be recalculated.</span></span> <span data-ttu-id="8b5b1-181">Entwickler, die diese Klasse verwenden, müssen die Details der Implementierung nicht kennen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-181">Developers that use this class do not need to know the details of the implementation.</span></span> <span data-ttu-id="8b5b1-182">Keine dieser interne Änderungen hat Einfluss auf die Verwendung des Person-Objekts.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-182">None of these internal changes affect the use of the Person object.</span></span> <span data-ttu-id="8b5b1-183">Das ist der Hauptgrund für die Verwendung von Eigenschaften, um Datenmember eines Objekts verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-183">That's the key reason for using Properties to expose data members of an object.</span></span>
 
### <a name="inotifypropertychanged"></a><span data-ttu-id="8b5b1-184">INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="8b5b1-184">INotifyPropertyChanged</span></span>

<span data-ttu-id="8b5b1-185">Ein abschließendes Szenario, in dem Sie Code in einem Eigenschaftenaccessor schreiben müssen, ist zur Unterstützung der `INotifyPropertyChanged`-Schnittstelle, die verwendet wird, um Clients mit Datenbindung zu benachrichtigen, dass ein Wert geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-185">A final scenario where you need to write code in a property accessor is to support the `INotifyPropertyChanged` interface used to notify data binding clients that a value has changed.</span></span> <span data-ttu-id="8b5b1-186">Wenn sich der Wert einer Eigenschaft ändert, löst das Objekt das `PropertyChanged`-Ereignis aus, um die Änderung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-186">When the value of a property changes, the object raises the `PropertyChanged` event to indicate the change.</span></span> <span data-ttu-id="8b5b1-187">Die Bibliotheken mit Datenbindung wiederum aktualisieren die auf dieser Änderung basierenden Anzeigeelemente.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-187">The data binding libraries, in turn, update display elements based on that change.</span></span> <span data-ttu-id="8b5b1-188">Der folgende Code zeigt, wie Sie `INotifyPropertyChanged` für die `FirstName`-Eigenschaft dieser Person-Klasse implementieren würden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-188">The code below shows how you would implement `INotifyPropertyChanged` for the `FirstName` property of this person class.</span></span>

```csharp
public class Person : INotifyPropertyChanged
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            if (value != firstName)
            {
                PropertyChanged?.Invoke(this, 
                    new PropertyChangedEventArgs(nameof(FirstName)));
            }
            firstName = value;
        }
    }
    private string firstName;

    public event PropertyChangedEventHandler PropertyChanged;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="8b5b1-189">Der Operator `?.` wird *bedingter NULL-Operator* genannt.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-189">The `?.` operator is called the *null conditional operator*.</span></span> <span data-ttu-id="8b5b1-190">Es sucht vor der Auswertung der rechten Seite des Operators nach einem NULL-Verweis.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-190">It checks for a null reference before evaluating the right side of the operator.</span></span> <span data-ttu-id="8b5b1-191">Das Endergebnis bedeutet, dass, wenn sich keine Abonnenten im `PropertyChanged`-Ereignis befinden, der Code zum Auslösen des Ereignisses nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-191">The end result is that if there are no subscribers to the `PropertyChanged` event, the code to raise the event doesn't execute.</span></span> <span data-ttu-id="8b5b1-192">Er würde eine `NullReferenceException` auslösen, ohne diese in diesem Fall zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-192">It would throw a `NullReferenceException` without this check in that case.</span></span> <span data-ttu-id="8b5b1-193">Weitere Informationen finden Sie auf der Seite [`events`](delegates-events.md).</span><span class="sxs-lookup"><span data-stu-id="8b5b1-193">See the page on [`events`](delegates-events.md) for more details.</span></span> <span data-ttu-id="8b5b1-194">In diesem Beispiel wird auch der neue `nameof`-Operator verwendet, um vom Symbol des Eigenschaftennamen in die Textdarstellung zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-194">This example also uses the new `nameof` operator to convert from the property name symbol to its text representation.</span></span>
<span data-ttu-id="8b5b1-195">Mithilfe von `nameof` können Fehler reduziert werden, bei denen Sie den Namen der Eigenschaft falsch eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-195">Using `nameof` can reduce errors where you have mistyped the name of the property.</span></span>

<span data-ttu-id="8b5b1-196">Erneut ist dies ein Beispiel für einen Fall, in dem Sie Code in Ihren Accessoren schreiben können, um die benötigten Szenarios zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-196">Again, this is an example of a case where you can write code in your accessors to support the scenarios you need.</span></span>

## <a name="summing-up"></a><span data-ttu-id="8b5b1-197">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="8b5b1-197">Summing up</span></span>

<span data-ttu-id="8b5b1-198">Eigenschaften sind eine Form intelligenter Felder in einer Klasse oder einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-198">Properties are a form of smart fields in a class or object.</span></span> <span data-ttu-id="8b5b1-199">Außerhalb des Objekts wirken diese wie Felder in dem Objekt.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-199">From outside the object, they appear like fields in the object.</span></span> <span data-ttu-id="8b5b1-200">Eigenschaften können jedoch mithilfe der vollständigen Palette der C#-Funktionalität implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-200">However, properties can be implemented using the full palette of C# functionality.</span></span>
<span data-ttu-id="8b5b1-201">Sie können Überprüfung, verschiedene Eingabehilfen, verzögerte Auswertung oder alle Anforderungen, die Ihre Szenarios benötigen, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8b5b1-201">You can provide validation, different accessibility, lazy evaluation, or any requirements your scenarios need.</span></span>
