---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: 476ef1bb1ac5ec1f551979c64a41cbae55c554bc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280256"
---
# <a name="dependency-properties"></a><span data-ttu-id="0542d-102">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="0542d-102">Dependency Properties</span></span>
<span data-ttu-id="0542d-103">Eine Abhängigkeits Eigenschaft (DP) ist eine reguläre Eigenschaft, die ihren Wert in einem Eigenschafts Speicher speichert, anstatt Sie in einer Typvariablen (Feld) zu speichern, z. b..</span><span class="sxs-lookup"><span data-stu-id="0542d-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>

 <span data-ttu-id="0542d-104">Eine angefügte Abhängigkeits Eigenschaft ist eine Art von Abhängigkeits Eigenschaft, die als statische Get-und Set-Methoden modelliert ist, die "Properties" darstellen, die Beziehungen zwischen Objekten und ihren Containern beschreiben (z.b. die Position eines- `Button` Objekts in einem `Panel` Container).</span><span class="sxs-lookup"><span data-stu-id="0542d-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>

 <span data-ttu-id="0542d-105">✔️ die Abhängigkeits Eigenschaften bereitstellen, wenn Sie die Eigenschaften benötigen, um WPF-Funktionen wie formatieren, Trigger, Daten Bindungen, Animationen, dynamische Ressourcen und Vererbung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0542d-105">✔️ DO provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>

## <a name="dependency-property-design"></a><span data-ttu-id="0542d-106">Design der Abhängigkeits Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0542d-106">Dependency Property Design</span></span>
 <span data-ttu-id="0542d-107">✔️ <xref:System.Windows.DependencyObject> bei der Implementierung von Abhängigkeits Eigenschaften von oder einem seiner Untertypen erben.</span><span class="sxs-lookup"><span data-stu-id="0542d-107">✔️ DO inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="0542d-108">Der-Typ stellt eine sehr effiziente Implementierung eines Eigenschaften Stores bereit und unterstützt automatisch die WPF-Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="0542d-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>

 <span data-ttu-id="0542d-109">✔️ stellen eine reguläre CLR-Eigenschaft und ein öffentliches statisches Schreib geschütztes Feld bereit, das eine Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeits Eigenschaft speichert.</span><span class="sxs-lookup"><span data-stu-id="0542d-109">✔️ DO provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>

 <span data-ttu-id="0542d-110">✔️ Implementieren Sie Abhängigkeits Eigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0542d-110">✔️ DO implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="0542d-111">✔️ dem statischen Feld der Abhängigkeits Eigenschaft einen Namen, indem Sie den Namen der Eigenschaft mit "Property" versehen.</span><span class="sxs-lookup"><span data-stu-id="0542d-111">✔️ DO name the dependency property static field by suffixing the name of the property with "Property."</span></span>

 <span data-ttu-id="0542d-112">❌Legen Sie Standardwerte von Abhängigkeits Eigenschaften nicht explizit im Code fest. Legen Sie Sie stattdessen in den Metadaten fest.</span><span class="sxs-lookup"><span data-stu-id="0542d-112">❌ DO NOT set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>

 <span data-ttu-id="0542d-113">Wenn Sie einen Standardwert für die Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft auf implizite Weise festgelegt wird, z. b. in Form einer Formatierung.</span><span class="sxs-lookup"><span data-stu-id="0542d-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>

 <span data-ttu-id="0542d-114">❌Fügen Sie keinen Code in den Eigenschaftenaccessoren außer dem Standard Code ein, um auf das statische Feld zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0542d-114">❌ DO NOT put code in the property accessors other than the standard code to access the static field.</span></span>

 <span data-ttu-id="0542d-115">Dieser Code wird nicht ausgeführt, wenn die Eigenschaft durch implizites Mittel (z. b. eine Formatierung) festgelegt wird, da die Formatierung das statische Feld direkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="0542d-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>

 <span data-ttu-id="0542d-116">❌Verwenden Sie keine Abhängigkeits Eigenschaften, um sichere Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0542d-116">❌ DO NOT use dependency properties to store secure data.</span></span> <span data-ttu-id="0542d-117">Auch private Abhängigkeits Eigenschaften können öffentlich aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0542d-117">Even private dependency properties can be accessed publicly.</span></span>

## <a name="attached-dependency-property-design"></a><span data-ttu-id="0542d-118">Design der angefügten Abhängigkeits Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0542d-118">Attached Dependency Property Design</span></span>
 <span data-ttu-id="0542d-119">Abhängigkeits Eigenschaften, die im vorangehenden Abschnitt beschrieben werden, stellen intrinsische Eigenschaften des deklarierenden Typs dar. Beispielsweise ist die- `Text` Eigenschaft eine Eigenschaft von `TextButton` , die Sie deklariert.</span><span class="sxs-lookup"><span data-stu-id="0542d-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="0542d-120">Eine besondere Art von Abhängigkeits Eigenschaft ist die angefügte Abhängigkeits Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0542d-120">A special kind of dependency property is the attached dependency property.</span></span>

 <span data-ttu-id="0542d-121">Ein klassisches Beispiel für eine angefügte Eigenschaft ist die- <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0542d-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0542d-122">Die-Eigenschaft stellt die Spaltenposition der Schaltfläche (nicht des Rasters) dar, ist aber nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, sodass Sie an Schaltflächen durch Raster angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0542d-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>

```xaml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>

    <Button Grid.Column="0">Click</Button>
    <Button Grid.Column="1">Clack</Button>
</Grid>
```

 <span data-ttu-id="0542d-123">Die Definition einer angefügten Eigenschaft sieht in der Regel wie eine reguläre Abhängigkeits Eigenschaft aus, mit dem Unterschied, dass die Accessoren durch statische Get-und Set-Methoden dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="0542d-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>

```csharp
public class Grid {

    public static int GetColumn(DependencyObject obj) {
        return (int)obj.GetValue(ColumnProperty);
    }

    public static void SetColumn(DependencyObject obj, int value) {
        obj.SetValue(ColumnProperty,value);
    }

    public static readonly DependencyProperty ColumnProperty =
        DependencyProperty.RegisterAttached(
            "Column",
            typeof(int),
            typeof(Grid)
    );
}
```

## <a name="dependency-property-validation"></a><span data-ttu-id="0542d-124">Validierung der Abhängigkeits Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0542d-124">Dependency Property Validation</span></span>
 <span data-ttu-id="0542d-125">Eigenschaften implementieren häufig, was als Validierung bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="0542d-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="0542d-126">Die Validierungs Logik wird ausgeführt, wenn versucht wird, den Wert einer Eigenschaft zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0542d-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>

 <span data-ttu-id="0542d-127">Leider können Abhängigkeits Eigenschaftenaccessoren keinen beliebigen Validierungscode enthalten.</span><span class="sxs-lookup"><span data-stu-id="0542d-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="0542d-128">Stattdessen muss bei der Eigenschaften Registrierung eine Validierungs Logik für die Abhängigkeits Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0542d-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>

 <span data-ttu-id="0542d-129">❌Fügen Sie die Validierungs Logik für die Abhängigkeits Eigenschaft nicht in die Accessoren der Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="0542d-129">❌ DO NOT put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="0542d-130">Übergeben Sie stattdessen einen Validierungs Rückruf an die- `DependencyProperty.Register` Methode.</span><span class="sxs-lookup"><span data-stu-id="0542d-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>

## <a name="dependency-property-change-notifications"></a><span data-ttu-id="0542d-131">Änderungs Benachrichtigungen für Abhängigkeits Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0542d-131">Dependency Property Change Notifications</span></span>
 <span data-ttu-id="0542d-132">❌Implementieren Sie keine Änderungs Benachrichtigungs Logik in Accessoren für Abhängigkeits Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0542d-132">❌ DO NOT implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="0542d-133">Abhängigkeits Eigenschaften verfügen über eine integrierte Änderungs Benachrichtigungsfunktion, die verwendet werden muss, wenn ein Änderungs Benachrichtigungs Rückruf an den übergeben wird <xref:System.Windows.PropertyMetadata> .</span><span class="sxs-lookup"><span data-stu-id="0542d-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>

## <a name="dependency-property-value-coercion"></a><span data-ttu-id="0542d-134">Umwandlung von Abhängigkeits Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="0542d-134">Dependency Property Value Coercion</span></span>
 <span data-ttu-id="0542d-135">Die Eigenschafts Umwandlung erfolgt, wenn der Wert, der an einen Eigenschaften Setter übergeben wird, vom Setter geändert wird, bevor der Eigenschaften Speicher tatsächlich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0542d-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>

 <span data-ttu-id="0542d-136">❌Implementieren Sie keine Umwandlungs Logik in Abhängigkeits Eigenschaften Accessoren.</span><span class="sxs-lookup"><span data-stu-id="0542d-136">❌ DO NOT implement coercion logic in dependency property accessors.</span></span>

 <span data-ttu-id="0542d-137">Abhängigkeits Eigenschaften verfügen über eine integrierte Umwandlungs Funktion und können verwendet werden, indem ein Umwandlungs Rückruf an den übergeben wird `PropertyMetadata` .</span><span class="sxs-lookup"><span data-stu-id="0542d-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>

 <span data-ttu-id="0542d-138">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0542d-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="0542d-139">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0542d-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0542d-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0542d-140">See also</span></span>

- [<span data-ttu-id="0542d-141">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0542d-141">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="0542d-142">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="0542d-142">Common Design Patterns</span></span>](common-design-patterns.md)
