---
title: Sichere Konstruktormuster für DependencyObjects
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 8e9e2f83e15e4e1703ed42dfb479efb8feed3bb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661281"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>Sichere Konstruktormuster für DependencyObjects
Im Allgemeinen sollten Klassenkonstruktoren Rückrufe wie virtuelle Methoden oder Delegaten nicht aufrufen, da Konstruktoren als Basisinitialisierung von Konstruktoren für eine abgeleitete Klasse aufgerufen werden können. Eintritt in das Virtuelle kann möglicherweise bei einem unvollständigen Initialisierungszustand eines Objekts erfolgen. Allerdings ruft das Eigenschaftensystem Rückrufe intern als Teil des Abhängigkeitseigenschaftensystem selbst auf und macht diese verfügbar. So einfach Vorgang der Einstellung eines Abhängigkeitseigenschaftswerts mit <xref:System.Windows.DependencyObject.SetValue%2A> Aufruf möglicherweise umfasst einen Rückruf an einer beliebigen Stelle in der Bestimmung. Aus diesem Grund sollten Sie beim Einstellen der Eigenschaftswerte innerhalb des Texts eines Konstruktors vorsichtig sein, da dies problematisch werden kann, wenn Ihr Typ als Basisklasse verwendet wird. Es gibt ein bestimmtes Muster zum Implementieren von <xref:System.Windows.DependencyObject> Konstruktoren, die bestimmte Probleme mit abhängigkeitseigenschaftszuständen und den inhärenten Rückrufen, vermieden werden können, die hier dokumentiert ist.  
  
 
  
<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a>Eigenschaftensystem – Virtuelle Methoden  
 Die folgenden virtuellen Methoden oder Rückrufe werden möglicherweise bei der Berechnung des Namens der <xref:System.Windows.DependencyObject.SetValue%2A> Aufruf, der einen Abhängigkeitseigenschaftenwert festlegt: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>. Diese virtuellen Methoden oder Rückrufe haben jeweils einen bestimmten Zweck bei der Erweiterung der Vielseitigkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems und der Abhängigkeitseigenschaften. Weitere Informationen zur Verwendung dieser virtuellen Methoden, um Eigenschaftswertbestimmungen anzupassen, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>Erzwingung der FXCop-Regel vs. Virtuelle Methoden des Eigenschaftensystems  
 Wenn Sie das Microsoft-Tool FXCop als Teil des Buildprozesses verwenden und Sie entweder von bestimmten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Frameworkklassen ableiten, die den Basiskonstruktor aufrufen oder Ihre eigenen Abhängigkeitseigenschaften in abgeleiteten Klassen implementieren, treten möglicherweise bestimmte FXCop-Regelverstöße auf. Der Name für diesen Verstoß ist:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Dies ist eine Regel, die Teil der öffentlich festgelegten Standardregel für FXCop ist. Was diese Regel möglicherweise meldet, ist eine Verfolgung durch das Abhängigkeitseigenschaftensystem, das schließlich ein Abhängigkeitseigenschaftensystem der virtuellen Methode aufruft. Dieser Regelverstoß wird möglicherweise auch nach dem Befolgen der empfohlenen Konstruktormuster weiterhin angezeigt, die in diesem Thema dokumentiert werden, deshalb könnte es sein, dass Sie diese Regel in der FXCop-Regelsatzkonfiguration deaktivieren oder unterdrücken müssen.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>Die meisten Probleme, die von abgeleiteten Klassen stammen, die keine vorhandenen Klassen verwenden  
 Die von dieser Regel gemeldeten Probleme treten auf, wenn eine Klasse, die Sie mit virtuellen Methoden in der Konstruktionsreihenfolge implementieren, anschließend abgeleitet wird. Wenn Sie die Klasse versiegeln oder sonst erkennen oder erzwingen, dass die Klasse nicht abgeleitet wird, werden die hier erläuterten Aspekte und die Probleme, die die FXCop-Regel begründen, nicht für Sie gelten. Wenn Sie Klassen jedoch so entwickeln, dass sie dazu bestimmt sind, als Basisklassen verwendet zu werden, z.B. wenn Sie Vorlagen oder einen erweiterbaren Steuerelementbibliotheksatz erstellen, sollten Sie die hier empfohlenen Muster für Konstruktoren befolgen.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>Standardkonstruktoren, die alle von Rückrufen angeforderten Werte initialisieren müssen  
 Alle Instanzmember, die von Ihrer Klasse überschrieben werden oder von Rückrufen (die Rückrufe aus der Liste im Abschnitt Eigenschaftensystemmethoden) verwendet werden, müssen in Ihrem Standardkonstruktor der Klasse initialisiert werden, auch wenn einige dieser Werte durch „echte“ Werte über Parameter, die nicht standardmäßige Konstruktoren sind, ausgefüllt werden.  
  
 Der folgende Beispielcode (und die nachfolgenden Beispiele), ist ein Pseudo-C#-Beispiel, das gegen diese Regel verstößt und das Problem erläutert:  
  
```  
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
  
 Wenn der Anwendungscode `new MyClass(objectvalue)` aufruft, ruft dies den Standardkonstruktor und die Basisklassenkonstruktoren auf. Dann legt `Property1 = object1`, ruft die virtuelle Methode `OnPropertyChanged` für die besitzende `MyClass` <xref:System.Windows.DependencyObject>.  Die Überschreibung verweist auf `_myList`, was noch nicht initialisiert wurde.  
  
 Eine Möglichkeit zur Vermeidung dieser Probleme, ist es sicherzustellen, dass Rückrufe nur andere Abhängigkeitseigenschaften verwenden, und dass jede dieser Abhängigkeitseigenschaften über einen festgelegten Standardwert als Teil ihrer registrierten Metadaten verfügt.  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a>Sichere Konstruktormuster  
 Führen Sie diese Muster aus, um das Risiko einer unvollständigen Initialisierung zu vermeiden, wenn die Klasse als Basisklasse verwendet wird:  
  
#### <a name="default-constructors-calling-base-initialization"></a>Standardkonstruktoren rufen Basisinitialisierung auf  
 Implementieren Sie diese Konstruktoren, in dem Sie den Basisstandardwert aufrufen:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>Nicht-standardmäßige (Komfort) Konstruktoren, die nicht den Basissignaturen entsprechen  
 Wenn diese Konstruktoren Parameter verwenden, um Abhängigkeitseigenschaften in der Initialisierung festzulegen, rufen Sie zuerst Ihren eigenen Standardkonstruktor der Klasse für die Initialisierung auf, und verwenden Sie anschließend die Parameter zum Festlegen von Abhängigkeitseigenschaften. Dies können entweder von Ihrer Klasse definierte Abhängigkeitseigenschaften oder Abhängigkeitseigenschaften von Klassen sein, die von Basisklassen abstammen, verwenden Sie jedoch in beiden Fällen das folgende Muster:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>Nicht-standardmäßige (Komfort) Konstruktoren, die mit den Basissignaturen übereinstimmen  
 Anstatt den Basiskonstruktor mit der gleichen Parametrisierung aufzurufen, rufen Sie erneut den Standardkonstruktor Ihrer eigenen Klasse auf. Rufen Sie die Basisinitialisierung nicht auf. Rufen Sie stattdessen `this()` auf. Reproduzieren Sie anschließend das Verhalten des ursprünglichen Konstruktors, indem Sie die übergebenen Parameter als Werte zum Festlegen der entsprechenden Eigenschaften verwenden. Verwenden Sie die Dokumentation zur ursprünglichen Basisklasse als Hilfestellung bei der Ermittlung der Eigenschaften, die die einzelnen Parameter festlegen sollen:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>Alle Signaturen müssen übereinstimmen  
 Für Fälle, in denen der Basistyp über mehrere Signaturen verfügt, müssen Sie absichtlich alle möglichen Signaturen Ihrer eigenen Konstruktorimplementierung zuordnen, die das empfohlene Muster vom Aufrufen der Standardkonstruktoren der Klasse verwenden, bevor Sie weitere Eigenschaften festlegen.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>Festlegen von Abhängigkeitseigenschaften mit SetValue  
 Diese gleichen Muster gelten, wenn Sie eine Eigenschaft, die nicht über einen Wrapper zum einfacheren Festlegen von Eigenschaften festlegen, und legen Sie Werte mit <xref:System.Windows.DependencyObject.SetValue%2A>. Ihre Aufrufe von <xref:System.Windows.DependencyObject.SetValue%2A> , Pass-through-Konstruktorparameter sollten auch den Standardkonstruktor der Klasse für die Initialisierung aufrufen.  
  
## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)
