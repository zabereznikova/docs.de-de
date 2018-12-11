---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: b577f42c98cb56fb367cb57a550cb094a8ef105e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145240"
---
# <a name="dependency-properties"></a><span data-ttu-id="d12f3-102">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="d12f3-102">Dependency Properties</span></span>
<span data-ttu-id="d12f3-103">Eine Abhängigkeitseigenschaft (DP) handelt es sich um eine reguläre Eigenschaft, die den Wert in einen Eigenschaftenspeicher, z. B. in einer Variablen vom Typ (Feld), speichern, statt speichert.</span><span class="sxs-lookup"><span data-stu-id="d12f3-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="d12f3-104">Eine angefügte Abhängigkeitseigenschaft ist eine Art von Abhängigkeitseigenschaft modelliert, die als statische Get- und Set-Methoden, die "Eigenschaften" Beschreiben von Beziehungen zwischen Objekten und ihren Containern darstellt (z. B. die Position des ein `Button` -Objekt ein `Panel` Container).</span><span class="sxs-lookup"><span data-stu-id="d12f3-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="d12f3-105">**✓ DO** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d12f3-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="d12f3-106">Eigenschaftenentwurf Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="d12f3-106">Dependency Property Design</span></span>  
 <span data-ttu-id="d12f3-107">**✓ DO** Vererben <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, bei der Implementierung von Abhängigkeitseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d12f3-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="d12f3-108">Der Typ stellt eine sehr effiziente Implementierung der einen Eigenschaftenspeicher und WPF-Datenbindung automatisch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d12f3-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="d12f3-109">**✓ DO** Geben Sie einen regulären CLR-Eigenschaft und eine öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d12f3-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="d12f3-110">**✓ DO** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d12f3-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d12f3-111">**✓ DO** benennen statische Abhängigkeit Eigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".</span><span class="sxs-lookup"><span data-stu-id="d12f3-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="d12f3-112">**X DO NOT** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.</span><span class="sxs-lookup"><span data-stu-id="d12f3-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="d12f3-113">Wenn Sie den Standardwert der Eigenschaft explizit festlegen, können Sie verhindern, dass die Eigenschaft einige implizite Art und Weise, wie z. B. ein Stil festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d12f3-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="d12f3-114">**X DO NOT** fügen Sie Code in den Eigenschaftenaccessoren als standard Code auf das statische Feld zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d12f3-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="d12f3-115">Dass Code ausgeführt wird nicht, wenn impliziter Art und Weise, wie z. B. eine Formatierung, die die Eigenschaft festgelegt ist, da Stile wird das statische Feld direkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="d12f3-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="d12f3-116">**X DO NOT** Abhängigkeitseigenschaften verwenden, um sichere Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d12f3-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="d12f3-117">Auch private Abhängigkeitseigenschaften können öffentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d12f3-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="d12f3-118">Angefügte Abhängigkeitseigenschaft Eigenschaftenentwurf</span><span class="sxs-lookup"><span data-stu-id="d12f3-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="d12f3-119">Abhängigkeitseigenschaften, die im vorherigen Abschnitt beschriebenen stellen die systeminterne Eigenschaften des deklarierenden Typs dar. z. B. die `Text` Eigenschaft ist eine Eigenschaft des `TextButton`, die es deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d12f3-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="d12f3-120">Eine besondere Art von Abhängigkeitseigenschaft ist das angefügte Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d12f3-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="d12f3-121">Ein klassisches Beispiel für eine angefügte Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d12f3-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d12f3-122">Die Eigenschaft darstellt, der Schaltfläche (nicht des Rasters) Spaltenposition, aber dies ist nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, weshalb er "Schaltflächen von Rastern angefügt ist".</span><span class="sxs-lookup"><span data-stu-id="d12f3-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="d12f3-123">Die Definition einer angefügten Eigenschaft sieht sich größtenteils wie eine reguläre Abhängigkeit-Eigenschaft, mit dem Unterschied, dass die Accessoren durch statische Get- und Set-Methoden dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="d12f3-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="d12f3-124">Abhängigkeitsüberprüfung-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d12f3-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="d12f3-125">Eigenschaften implementieren häufig, welche die Validierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d12f3-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="d12f3-126">Validierungslogik ausgeführt wird, wenn versucht wird, den Wert einer Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="d12f3-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="d12f3-127">Leider können keine Abhängigkeit von Eigenschaftenaccessoren beliebige Validierungscode enthalten.</span><span class="sxs-lookup"><span data-stu-id="d12f3-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="d12f3-128">Stattdessen muss Logik zur Überprüfung von Dependency-Eigenschaft während der Registrierung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d12f3-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="d12f3-129">**X DO NOT** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt.</span><span class="sxs-lookup"><span data-stu-id="d12f3-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="d12f3-130">Übergeben Sie stattdessen einen Validierungsrückruf zu `DependencyProperty.Register` Methode.</span><span class="sxs-lookup"><span data-stu-id="d12f3-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="d12f3-131">Benachrichtigungen über Eigenschaftsänderungen Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="d12f3-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="d12f3-132">**X DO NOT** Change Notification Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="d12f3-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="d12f3-133">Abhängigkeitseigenschaften verfügen über eine integrierte Change Benachrichtigungen-Funktion, die verwendet werden muss, durch Angabe der Rückruf einer änderungsbenachrichtigung auf dem <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="d12f3-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="d12f3-134">Koersion des Eigenschaftswerts Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="d12f3-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="d12f3-135">Eigenschaft Koersion findet statt, wenn der angegebene Wert auf einen Eigenschaften-Setter vom Setter geändert wird, bevor der Eigenschaftenspeicher tatsächlich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d12f3-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="d12f3-136">**X DO NOT** Umwandlung Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="d12f3-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="d12f3-137">Abhängigkeitseigenschaften verfügen über eine integrierte Koersion-Funktion und kann verwendet werden, durch Angabe eines Umwandlung-Rückrufs, der die `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="d12f3-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="d12f3-138">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d12f3-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d12f3-139">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="d12f3-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12f3-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d12f3-140">See also</span></span>

- [<span data-ttu-id="d12f3-141">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d12f3-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="d12f3-142">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="d12f3-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
