---
title: Sichere Konstruktormuster für DependencyObjects
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 6d6ff444b99ca893e687731c56a48ea3ac072dd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187229"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>Sichere Konstruktormuster für DependencyObjects
Im Allgemeinen sollten Klassenkonstruktoren Rückrufe wie virtuelle Methoden oder Delegaten nicht aufrufen, da Konstruktoren als Basisinitialisierung von Konstruktoren für eine abgeleitete Klasse aufgerufen werden können. Eintritt in das Virtuelle kann möglicherweise bei einem unvollständigen Initialisierungszustand eines Objekts erfolgen. Allerdings ruft das Eigenschaftensystem Rückrufe intern als Teil des Abhängigkeitseigenschaftensystem selbst auf und macht diese verfügbar. Ein so einfacher Vorgang wie das <xref:System.Windows.DependencyObject.SetValue%2A> Festlegen eines Abhängigkeitseigenschaftswerts mit Aufruf enthält möglicherweise einen Rückruf irgendwo in der Bestimmung. Aus diesem Grund sollten Sie beim Einstellen der Eigenschaftswerte innerhalb des Texts eines Konstruktors vorsichtig sein, da dies problematisch werden kann, wenn Ihr Typ als Basisklasse verwendet wird. Es gibt ein bestimmtes <xref:System.Windows.DependencyObject> Muster für die Implementierung von Konstruktoren, das spezifische Probleme mit Abhängigkeitseigenschaftszuständen und den inhärenten Rückrufen vermeidet, die hier dokumentiert sind.  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a>Eigenschaftensystem – Virtuelle Methoden  
 Die folgenden virtuellen Methoden oder Rückrufe werden möglicherweise <xref:System.Windows.DependencyObject.SetValue%2A> während der Berechnungen des <xref:System.Windows.ValidateValueCallback>Aufrufs aufgerufen, der einen Abhängigkeitseigenschaftswert festlegt: , <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>. Diese virtuellen Methoden oder Rückrufe haben jeweils einen bestimmten Zweck bei der Erweiterung der Vielseitigkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems und der Abhängigkeitseigenschaften. Weitere Informationen zur Verwendung dieser virtuellen Methoden, um Eigenschaftswertbestimmungen anzupassen, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md).  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>FXCop Rule Enforcement vs. Property System Virtuals  
 Wenn Sie das Microsoft-Tool FXCop als Teil des Buildprozesses verwenden und Sie entweder von bestimmten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Frameworkklassen ableiten, die den Basiskonstruktor aufrufen oder Ihre eigenen Abhängigkeitseigenschaften in abgeleiteten Klassen implementieren, treten möglicherweise bestimmte FXCop-Regelverstöße auf. Der Name für diesen Verstoß ist:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Dies ist eine Regel, die Teil der öffentlich festgelegten Standardregel für FXCop ist. Was diese Regel möglicherweise meldet, ist eine Verfolgung durch das Abhängigkeitseigenschaftensystem, das schließlich ein Abhängigkeitseigenschaftensystem der virtuellen Methode aufruft. Dieser Regelverstoß wird möglicherweise auch nach dem Befolgen der empfohlenen Konstruktormuster weiterhin angezeigt, die in diesem Thema dokumentiert werden, deshalb könnte es sein, dass Sie diese Regel in der FXCop-Regelsatzkonfiguration deaktivieren oder unterdrücken müssen.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>Die meisten Probleme, die von abgeleiteten Klassen stammen, die keine vorhandenen Klassen verwenden  
 Die von dieser Regel gemeldeten Probleme treten auf, wenn eine Klasse, die Sie mit virtuellen Methoden in der Konstruktionsreihenfolge implementieren, anschließend abgeleitet wird. Wenn Sie die Klasse versiegeln oder sonst erkennen oder erzwingen, dass die Klasse nicht abgeleitet wird, werden die hier erläuterten Aspekte und die Probleme, die die FXCop-Regel begründen, nicht für Sie gelten. Wenn Sie Klassen jedoch so entwickeln, dass sie dazu bestimmt sind, als Basisklassen verwendet zu werden, z.B. wenn Sie Vorlagen oder einen erweiterbaren Steuerelementbibliotheksatz erstellen, sollten Sie die hier empfohlenen Muster für Konstruktoren befolgen.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>Standardkonstruktoren, die alle von Rückrufen angeforderten Werte initialisieren müssen  
 Alle Instanzmember, die von Ihren Klassenüberschreibungen oder Rückrufen (die Rückrufe aus der Liste im Abschnitt Property System Virtuals) verwendet werden, müssen in Ihrem klassenparameterlosen Konstruktor initialisiert werden, auch wenn einige dieser Werte durch "echte" Werte über Parameter der nicht parameterlosen Konstruktoren.  
  
 Der folgende Beispielcode (und die nachfolgenden Beispiele), ist ein Pseudo-C#-Beispiel, das gegen diese Regel verstößt und das Problem erläutert:  
  
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
  
 Beim Aufrufen `new MyClass(objectvalue)`von Anwendungscode ruft dies den parameterlosen Konstruktor und die Basisklassenkonstruktoren auf. Anschließend wird `Property1 = object1`festgelegt, , `OnPropertyChanged` die die `MyClass` <xref:System.Windows.DependencyObject>virtuelle Methode auf dem besitzenden aufruft.  Die Überschreibung verweist auf `_myList`, was noch nicht initialisiert wurde.  
  
 Eine Möglichkeit zur Vermeidung dieser Probleme, ist es sicherzustellen, dass Rückrufe nur andere Abhängigkeitseigenschaften verwenden, und dass jede dieser Abhängigkeitseigenschaften über einen festgelegten Standardwert als Teil ihrer registrierten Metadaten verfügt.  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a>Sichere Konstruktormuster  
 Führen Sie diese Muster aus, um das Risiko einer unvollständigen Initialisierung zu vermeiden, wenn die Klasse als Basisklasse verwendet wird:  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a>Parameterlose Konstruktoren, die die Basisinitialisierung aufrufen  
 Implementieren Sie diese Konstruktoren, in dem Sie den Basisstandardwert aufrufen:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>Nicht-standardmäßige (Komfort) Konstruktoren, die nicht den Basissignaturen entsprechen  
 Wenn diese Konstruktoren die Parameter verwenden, um Abhängigkeitseigenschaften in der Initialisierung festzulegen, rufen Sie zuerst Ihren eigenen klassenparameterlosen Konstruktor für die Initialisierung auf, und verwenden Sie dann die Parameter, um Abhängigkeitseigenschaften festzulegen. Dies können entweder von Ihrer Klasse definierte Abhängigkeitseigenschaften oder Abhängigkeitseigenschaften von Klassen sein, die von Basisklassen abstammen, verwenden Sie jedoch in beiden Fällen das folgende Muster:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>Nicht-standardmäßige (Komfort) Konstruktoren, die mit den Basissignaturen übereinstimmen  
 Anstatt den Basiskonstruktor mit der gleichen Parametrierung aufzurufen, rufen Sie erneut den parameterlosen Konstruktor Ihrer eigenen Klasse auf. Rufen Sie die Basisinitialisierung nicht auf. Rufen Sie stattdessen `this()` auf. Reproduzieren Sie anschließend das Verhalten des ursprünglichen Konstruktors, indem Sie die übergebenen Parameter als Werte zum Festlegen der entsprechenden Eigenschaften verwenden. Verwenden Sie die Dokumentation zur ursprünglichen Basisklasse als Hilfestellung bei der Ermittlung der Eigenschaften, die die einzelnen Parameter festlegen sollen:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>Alle Signaturen müssen übereinstimmen  
 Für Fälle, in denen der Basistyp über mehrere Signaturen verfügt, müssen Sie alle möglichen Signaturen absichtlich mit einer eigenen Konstruktorimplementierung abgleichen, die das empfohlene Muster zum Aufrufen des klassenparameterlosen Konstruktors verwendet, bevor Sie weitere Festlegen. Eigenschaften.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>Festlegen von Abhängigkeitseigenschaften mit SetValue  
 Dieselben Muster gelten, wenn Sie eine Eigenschaft festlegen, die keinen Wrapper für <xref:System.Windows.DependencyObject.SetValue%2A>die Eigenschafteneinstellungsfreundlichkeit hat, und Werte mit festlegen. Ihre Aufrufe <xref:System.Windows.DependencyObject.SetValue%2A> an diesen Durchgangs-Durchlaufkonstruktorparameter sollten auch den parameterlosen Konstruktor der Klasse zur Initialisierung aufrufen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
