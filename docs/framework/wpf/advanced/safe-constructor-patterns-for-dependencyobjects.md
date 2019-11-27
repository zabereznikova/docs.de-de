---
title: Sichere Konstruktormuster für DependencyObjects
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 66e380a9428395c772d0dcfe45a995374774aec6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283834"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="1aad6-102">Sichere Konstruktormuster für DependencyObjects</span><span class="sxs-lookup"><span data-stu-id="1aad6-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="1aad6-103">Im Allgemeinen sollten Klassenkonstruktoren Rückrufe wie virtuelle Methoden oder Delegaten nicht aufrufen, da Konstruktoren als Basisinitialisierung von Konstruktoren für eine abgeleitete Klasse aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="1aad6-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="1aad6-104">Eintritt in das Virtuelle kann möglicherweise bei einem unvollständigen Initialisierungszustand eines Objekts erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="1aad6-105">Allerdings ruft das Eigenschaftensystem Rückrufe intern als Teil des Abhängigkeitseigenschaftensystem selbst auf und macht diese verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1aad6-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="1aad6-106">Ein Vorgang, bei dem ein Abhängigkeits Eigenschafts Wert mit <xref:System.Windows.DependencyObject.SetValue%2A>-Aufrufs festgelegt wird, beinhaltet möglicherweise einen Rückruf an einer beliebigen Stelle</span><span class="sxs-lookup"><span data-stu-id="1aad6-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="1aad6-107">Aus diesem Grund sollten Sie beim Einstellen der Eigenschaftswerte innerhalb des Texts eines Konstruktors vorsichtig sein, da dies problematisch werden kann, wenn Ihr Typ als Basisklasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1aad6-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="1aad6-108">Es gibt ein bestimmtes Muster für die Implementierung von <xref:System.Windows.DependencyObject> Konstruktoren, die bestimmte Probleme mit Abhängigkeits Eigenschafts Zuständen und den inhärenten Rückrufen, die hier dokumentiert sind, vermeidet.</span><span class="sxs-lookup"><span data-stu-id="1aad6-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a><span data-ttu-id="1aad6-109">Eigenschaftensystem – Virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="1aad6-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="1aad6-110">Die folgenden virtuellen Methoden oder Rückrufe werden möglicherweise während der Berechnungen des <xref:System.Windows.DependencyObject.SetValue%2A>-Aufrufs aufgerufen, der einen Wert für die Abhängigkeits Eigenschaft festlegt: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback><xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="1aad6-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="1aad6-111">Diese virtuellen Methoden oder Rückrufe haben jeweils einen bestimmten Zweck bei der Erweiterung der Vielseitigkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems und der Abhängigkeitseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1aad6-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="1aad6-112">Weitere Informationen zur Verwendung dieser virtuellen Methoden, um Eigenschaftswertbestimmungen anzupassen, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="1aad6-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="1aad6-113">Durchsetzung der FxCop-Regel im Vergleich zu Eigenschaften System-Virtuals</span><span class="sxs-lookup"><span data-stu-id="1aad6-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="1aad6-114">Wenn Sie das Microsoft-Tool FXCop als Teil des Buildprozesses verwenden und Sie entweder von bestimmten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Frameworkklassen ableiten, die den Basiskonstruktor aufrufen oder Ihre eigenen Abhängigkeitseigenschaften in abgeleiteten Klassen implementieren, treten möglicherweise bestimmte FXCop-Regelverstöße auf.</span><span class="sxs-lookup"><span data-stu-id="1aad6-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="1aad6-115">Der Name für diesen Verstoß ist:</span><span class="sxs-lookup"><span data-stu-id="1aad6-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="1aad6-116">Dies ist eine Regel, die Teil der öffentlich festgelegten Standardregel für FXCop ist.</span><span class="sxs-lookup"><span data-stu-id="1aad6-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="1aad6-117">Was diese Regel möglicherweise meldet, ist eine Verfolgung durch das Abhängigkeitseigenschaftensystem, das schließlich ein Abhängigkeitseigenschaftensystem der virtuellen Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="1aad6-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="1aad6-118">Dieser Regelverstoß wird möglicherweise auch nach dem Befolgen der empfohlenen Konstruktormuster weiterhin angezeigt, die in diesem Thema dokumentiert werden, deshalb könnte es sein, dass Sie diese Regel in der FXCop-Regelsatzkonfiguration deaktivieren oder unterdrücken müssen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="1aad6-119">Die meisten Probleme, die von abgeleiteten Klassen stammen, die keine vorhandenen Klassen verwenden</span><span class="sxs-lookup"><span data-stu-id="1aad6-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="1aad6-120">Die von dieser Regel gemeldeten Probleme treten auf, wenn eine Klasse, die Sie mit virtuellen Methoden in der Konstruktionsreihenfolge implementieren, anschließend abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1aad6-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="1aad6-121">Wenn Sie die Klasse versiegeln oder sonst erkennen oder erzwingen, dass die Klasse nicht abgeleitet wird, werden die hier erläuterten Aspekte und die Probleme, die die FXCop-Regel begründen, nicht für Sie gelten.</span><span class="sxs-lookup"><span data-stu-id="1aad6-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="1aad6-122">Wenn Sie Klassen jedoch so entwickeln, dass sie dazu bestimmt sind, als Basisklassen verwendet zu werden, z.B. wenn Sie Vorlagen oder einen erweiterbaren Steuerelementbibliotheksatz erstellen, sollten Sie die hier empfohlenen Muster für Konstruktoren befolgen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="1aad6-123">Standardkonstruktoren, die alle von Rückrufen angeforderten Werte initialisieren müssen</span><span class="sxs-lookup"><span data-stu-id="1aad6-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="1aad6-124">Alle Instanzmember, die von der-Klasse verwendet werden, überschreiben oder Rückrufe (die Rückrufe aus der Liste im Abschnitt "Eigenschaften System-Virtuals") müssen in dem Parameter losen Konstruktor der Klasse initialisiert werden, auch wenn einige dieser Werte durch "Real"-Werte ausgefüllt werden. Parameter der nicht parameterlosen Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="1aad6-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="1aad6-125">Der folgende Beispielcode (und die nachfolgenden Beispiele), ist ein Pseudo-C#-Beispiel, das gegen diese Regel verstößt und das Problem erläutert:</span><span class="sxs-lookup"><span data-stu-id="1aad6-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="1aad6-126">Wenn der Anwendungscode `new MyClass(objectvalue)`aufruft, werden dadurch der Parameter lose Konstruktor und die Basisklassenkonstruktoren aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="1aad6-127">Anschließend wird `Property1 = object1`festgelegt, mit dem die virtuelle Methode `OnPropertyChanged` auf dem besitzenden `MyClass` <xref:System.Windows.DependencyObject>aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1aad6-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="1aad6-128">Die Überschreibung verweist auf `_myList`, was noch nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1aad6-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="1aad6-129">Eine Möglichkeit zur Vermeidung dieser Probleme, ist es sicherzustellen, dass Rückrufe nur andere Abhängigkeitseigenschaften verwenden, und dass jede dieser Abhängigkeitseigenschaften über einen festgelegten Standardwert als Teil ihrer registrierten Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="1aad6-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a><span data-ttu-id="1aad6-130">Sichere Konstruktormuster</span><span class="sxs-lookup"><span data-stu-id="1aad6-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="1aad6-131">Führen Sie diese Muster aus, um das Risiko einer unvollständigen Initialisierung zu vermeiden, wenn die Klasse als Basisklasse verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1aad6-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="1aad6-132">Parameter lose Konstruktoren, die die Basis Initialisierung aufrufen</span><span class="sxs-lookup"><span data-stu-id="1aad6-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="1aad6-133">Implementieren Sie diese Konstruktoren, in dem Sie den Basisstandardwert aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1aad6-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="1aad6-134">Nicht-standardmäßige (Komfort) Konstruktoren, die nicht den Basissignaturen entsprechen</span><span class="sxs-lookup"><span data-stu-id="1aad6-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="1aad6-135">Wenn diese Konstruktoren die-Parameter verwenden, um Abhängigkeits Eigenschaften in der Initialisierung festzulegen, müssen Sie zuerst Ihren eigenen Klassen Parameter losen Konstruktor für die Initialisierung aufzurufen und dann die-Parameter verwenden, um Abhängigkeits Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="1aad6-136">Dies können entweder von Ihrer Klasse definierte Abhängigkeitseigenschaften oder Abhängigkeitseigenschaften von Klassen sein, die von Basisklassen abstammen, verwenden Sie jedoch in beiden Fällen das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="1aad6-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="1aad6-137">Nicht-standardmäßige (Komfort) Konstruktoren, die mit den Basissignaturen übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="1aad6-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="1aad6-138">Anstatt den Basiskonstruktor mit derselben Parametrisierung aufzurufen, rufen Sie erneut den Parameter losen Konstruktor Ihrer eigenen Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="1aad6-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="1aad6-139">Rufen Sie die Basisinitialisierung nicht auf. Rufen Sie stattdessen `this()` auf.</span><span class="sxs-lookup"><span data-stu-id="1aad6-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="1aad6-140">Reproduzieren Sie anschließend das Verhalten des ursprünglichen Konstruktors, indem Sie die übergebenen Parameter als Werte zum Festlegen der entsprechenden Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="1aad6-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="1aad6-141">Verwenden Sie die Dokumentation zur ursprünglichen Basisklasse als Hilfestellung bei der Ermittlung der Eigenschaften, die die einzelnen Parameter festlegen sollen:</span><span class="sxs-lookup"><span data-stu-id="1aad6-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="1aad6-142">Alle Signaturen müssen übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="1aad6-142">Must match all signatures</span></span>  
 <span data-ttu-id="1aad6-143">In Fällen, in denen der Basistyp über mehrere Signaturen verfügt, müssen Sie absichtlich alle möglichen Signaturen mit einer Konstruktorimplementierung ihrer eigenen zuordnen, die das empfohlene Muster zum Aufrufen des Parametern für die Klassen Parameter losen Konstruktor vor der weiteren Festlegung verwendet. Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1aad6-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="1aad6-144">Festlegen von Abhängigkeitseigenschaften mit SetValue</span><span class="sxs-lookup"><span data-stu-id="1aad6-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="1aad6-145">Diese Muster gelten auch, wenn Sie eine Eigenschaft festlegen, die keinen Wrapper für die Einstellung der Eigenschafts Einstellung hat, und Werte mit <xref:System.Windows.DependencyObject.SetValue%2A>festlegen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="1aad6-146">Die Aufrufe von <xref:System.Windows.DependencyObject.SetValue%2A>, die Konstruktorparameter durchlaufen, sollten auch den Parameter losen Konstruktor für die Initialisierung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1aad6-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aad6-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aad6-147">See also</span></span>

- [<span data-ttu-id="1aad6-148">Benutzerdefinierte Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="1aad6-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="1aad6-149">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="1aad6-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="1aad6-150">Sicherheit von Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="1aad6-150">Dependency Property Security</span></span>](dependency-property-security.md)
