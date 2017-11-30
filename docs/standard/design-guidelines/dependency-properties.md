---
title: "Abhängigkeitseigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21e2026e7ce0f2dcf1ffc9a328b1bb9630cd8fbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-properties"></a><span data-ttu-id="bed47-102">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="bed47-102">Dependency Properties</span></span>
<span data-ttu-id="bed47-103">Eine Abhängigkeitseigenschaft (DP) ist eine reguläre Eigenschaft, die den Wert in einen Eigenschaftenspeicher, z. B. in einer Variablen des Typs (Feld), speichern, statt speichert.</span><span class="sxs-lookup"><span data-stu-id="bed47-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="bed47-104">Eine angehängte Abhängigkeitseigenschaft ist eine Art von Abhängigkeitseigenschaft modelliert als statische Get- und Set-Methoden, die "Eigenschaften" Beschreiben von Beziehungen zwischen Objekten und deren Container darstellen (z. B. die Position des eine `Button` -Objekt, auf eine `Panel` Container).</span><span class="sxs-lookup"><span data-stu-id="bed47-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="bed47-105">**Führen Sie ✓** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bed47-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="bed47-106">Entwerfen der Abhängigkeit-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bed47-106">Dependency Property Design</span></span>  
 <span data-ttu-id="bed47-107">**Führen Sie ✓** Vererben <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, bei der Implementierung von Abhängigkeitseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bed47-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="bed47-108">Der Typ bietet eine äußerst effiziente Implementierung des einen Eigenschaftenspeicher und WPF-Datenbindung automatisch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bed47-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="bed47-109">**Führen Sie ✓** Geben Sie einen regulären CLR-Eigenschaft und eine öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bed47-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="bed47-110">**Führen Sie ✓** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bed47-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="bed47-111">**Führen Sie ✓** benennen statische Abhängigkeit Eigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".</span><span class="sxs-lookup"><span data-stu-id="bed47-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="bed47-112">**X nicht** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.</span><span class="sxs-lookup"><span data-stu-id="bed47-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="bed47-113">Wenn Sie den Standardwert der Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft implizite Weise, wie z. B. eine Formatvorlage festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="bed47-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="bed47-114">**X nicht** fügen Sie Code in den Eigenschaftenaccessoren als standard Code auf das statische Feld zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bed47-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="bed47-115">Code ausgeführt wird nicht, wenn implizite Wege, wie z. B. eine Formatvorlage, die Eigenschaft festgelegt ist, da Formatierung verwendet das statische Feld direkt.</span><span class="sxs-lookup"><span data-stu-id="bed47-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="bed47-116">**X nicht** Abhängigkeitseigenschaften verwenden, um sichere Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bed47-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="bed47-117">Selbst bei privaten Abhängigkeitseigenschaften können öffentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="bed47-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="bed47-118">Abhängigkeit angefügte Eigenschaftenentwurf</span><span class="sxs-lookup"><span data-stu-id="bed47-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="bed47-119">Im vorherigen Abschnitt beschriebene Abhängigkeitseigenschaften darstellen systeminterne Eigenschaften des deklarierenden Typs; z. B. die `Text` Eigenschaft ist eine Eigenschaft des `TextButton`, die es deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="bed47-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="bed47-120">Eine spezielle Art von Abhängigkeitseigenschaft ist das angehängte Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bed47-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="bed47-121">Ein klassisches Beispiel einer angefügten Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bed47-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bed47-122">Die Eigenschaft darstellt, Spaltenposition Schaltfläche (nicht des Datenblatts), aber es ist nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, weshalb es "Schaltflächen von Rastern angefügt ist".</span><span class="sxs-lookup"><span data-stu-id="bed47-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="bed47-123">Die Definition einer angefügten Eigenschaft sieht größtenteils wie eine reguläre Abhängigkeit-Eigenschaft, mit dem Unterschied, dass die Accessoren durch statische Get- und Set-Methoden dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="bed47-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="bed47-124">Abhängigkeitsüberprüfung-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bed47-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="bed47-125">Eigenschaften implementieren häufig auf, was die Validierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bed47-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="bed47-126">Validierungslogik ausgeführt wird, wenn versucht wird, den Wert einer Eigenschaft zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bed47-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="bed47-127">Leider können keine Abhängigkeit Eigenschaftenaccessoren beliebige Validierungscode enthalten.</span><span class="sxs-lookup"><span data-stu-id="bed47-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="bed47-128">Stattdessen muss die Abhängigkeit Eigenschaft Validierungslogik während der Registrierung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bed47-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="bed47-129">**X nicht** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt.</span><span class="sxs-lookup"><span data-stu-id="bed47-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="bed47-130">Stattdessen übergeben, um einen Validierungsrückruf `DependencyProperty.Register` Methode.</span><span class="sxs-lookup"><span data-stu-id="bed47-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="bed47-131">Abhängigkeit Eigenschaft Änderungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="bed47-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="bed47-132">**X nicht** Change Notification Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="bed47-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="bed47-133">Abhängigkeitseigenschaften verfügen über eine integrierte Änderung Benachrichtigungen-Funktion, die verwendet werden muss, durch Angabe eines Rückrufs zum Ändern der <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="bed47-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="bed47-134">Abhängigkeit Eigenschaft-Wert-Umwandlung</span><span class="sxs-lookup"><span data-stu-id="bed47-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="bed47-135">Eigenschaft Umwandlung findet statt, wenn der angegebene Wert auf einen Eigenschaften-Setter von Setter-Methode geändert wird, bevor der Eigenschaftenspeicher tatsächlich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="bed47-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="bed47-136">**X nicht** Umwandlung Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="bed47-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="bed47-137">Abhängigkeitseigenschaften verfügen über eine integrierte Koersion-Funktion und kann verwendet werden, durch einen Rückruf Umwandlung zur Angabe der `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="bed47-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="bed47-138">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="bed47-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bed47-139">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="bed47-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed47-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed47-140">See Also</span></span>  
 [<span data-ttu-id="bed47-141">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bed47-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="bed47-142">Allgemeiner Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="bed47-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
