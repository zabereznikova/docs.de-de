---
title: "Sichere Konstruktormuster f&#252;r DependencyObjects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Konstruktormuster für Abhängigkeitsobjekte"
  - "Abhängigkeitsobjekte, Konstruktormuster"
  - "FXCop-Tool"
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Sichere Konstruktormuster f&#252;r DependencyObjects
Im Allgemeinen sollten Klassenkonstruktoren keine Rückrufe wie virtuelle Methoden oder Delegate aufrufen, da Konstruktoren als Basisinitialisierung von Konstruktoren für eine abgeleitete Klasse aufgerufen werden können.  Der Eintritt in das Virtuelle findet dann möglicherweise zu einem unvollständigen Initialisierungszustand eines Objekts statt.  Das Eigenschaftensystem selbst ruft jedoch Rückrufe als Teil des Systems von Abhängigkeitseigenschaften intern auf und stellt sie bereit.  Ein einfacher Vorgang wie das Festlegen eines Abhängigkeitseigenschaftswerts mit dem <xref:System.Windows.DependencyObject.SetValue%2A>\-Aufruf umfasst potenziell einen Rückruf in der Bestimmung.  Aus diesem Grund sollten Sie beim Festlegen von Abhängigkeitseigenschaftswerten im Text eines Konstruktors vorsichtig vorgehen, da dies zu Problemen führen kann, wenn der Typ als Basisklasse verwendet wird.  Es gibt ein bestimmtes Muster zum Implementieren von <xref:System.Windows.DependencyObject>\-Konstruktoren, mit dem gewisse Probleme mit Abhängigkeitseigenschaftenzuständen und den inhärenten Rückrufen vermieden werden können, wie hier aufgeführt.  
  
   
  
<a name="Property_System_Virtual_Methods"></a>   
## Virtuelle Methoden des Eigenschaftensystems  
 Die folgenden virtuellen Methoden oder Rückrufe werden bei der Berechnung des <xref:System.Windows.DependencyObject.SetValue%2A>\-Aufrufs, der einen Abhängigkeitseigenschaftswert festlegt, möglicherweise aufgerufen: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.  Dieser virtuellen Methoden oder Rückrufe haben jeweils einen bestimmten Zweck bei der Erweiterung der Vielseitigkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Eigenschaftensystems und der Abhängigkeitseigenschaften.  Weitere Informationen zur Verwendung dieser virtuellen Methoden zum Anpassen der Eigenschaftswertbestimmung finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
### FXCop\-Regeldurchsetzung im Vergleich zuvirtuellen Eigenschaftensystemmethoden  
 Wenn Sie das FXCop\-Tool von Microsoft als Teil des Buildprozesses verwenden und Sie entweder von bestimmten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Frameworkklassen ableiten, die den Basiskonstruktor aufrufen, oder eigene Abhängigkeitseigenschaften für abgeleitete Klassen implementieren, kommt es möglicherweise zu einer bestimmten FXCop\-Regelverletzung.  Die Namenszeichenfolge für diese Verletzung lautet wie folgt:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Diese Regel ist Teil des öffentlichen Standardregelsatzes für FXCop.  Sie protokolliert die Ablaufverfolgung durch das System der Abhängigkeitseigenschaften, die schließlich eine virtuelle Methode des Abhängigkeitseigenschaftensystems aufruft.  Diese Regelverletzung kann auch dann auftreten, wenn die in diesem Thema aufgeführten empfohlenen Konstruktormuster angewendet wurden, sodass Sie diese Regel in der FXCop\-Regelsatzkonfiguration möglicherweise deaktivieren oder unterdrücken müssen.  
  
### Die meisten Probleme werden durch das Ableiten von Klassen, nicht durch das Verwenden vorhandener Klassen verursacht  
 Die meisten von dieser Regel protokollierten Fehler treten auf, wenn von einer Klasse, die Sie mit virtuellen Methoden in der Konstruktionsreihenfolge implementieren, anschließend abgeleitet wird.  Wenn Sie die Klasse versiegeln oder auf andere Weise wissen bzw. erzwingen, dass von der Klasse nicht abgeleitet wird, finden die hier erläuterten Überlegungen und die Probleme, die zur Entwicklung der FXCop\-Regel geführt haben, für Sie keine Anwendung.  Wenn Sie jedoch Klassen erstellen, die als Basisklassen verwendet werden sollen \(falls Sie beispielsweise Vorlagen oder eine Bibliothek erweiterbarer Steuerelemente erstellen\), sollten Sie den hier empfohlenen Mustern für Konstruktoren folgen.  
  
### Standardkonstruktoren müssen alle von Rückrufen angeforderten Werte initialisieren  
 Instanzmember, die von Ihren Klassenüberschreibungen oder Rückrufen \(Rückrufe aus der Liste im Abschnitt Virtuelle Methoden des Eigenschaftensystems\) verwendet werden, müssen im Standardkonstruktor der Klasse initialisiert werden, auch wenn einige dieser Werte über Parameter nicht standardmäßiger Konstruktoren mit "echten" Werten ausgefüllt werden.  
  
 Das folgende Codebeispiel \(und die nachfolgenden Beispiele\) ist ein C\#\-Pseudobeispiel, das diese Regel verletzt und das Problem veranschaulicht:  
  
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
  
 Wenn der Anwendungscode `new MyClass(objectvalue)` aufruft, werden hierdurch der Standardkonstruktor und die Basisklassenkonstruktoren aufgerufen.  Der Code legt dann `Property1 = object1` fest, wodurch die virtuelle `OnPropertyChanged`\-Methode für das besitzende `MyClass` <xref:System.Windows.DependencyObject> aufgerufen wird.  Die Überschreibung verweist auf `_myList`, die noch nicht initialisiert wurde.  
  
 Eine Möglichkeit, diese Probleme zu vermeiden, besteht darin, sicherzustellen, dass Rückrufe nur andere Abhängigkeitseigenschaften verwenden und dass jede dieser Abhängigkeitseigenschaften über einen festgelegten Standardwert als Teil ihrer registrierten Metadaten verfügt.  
  
<a name="Safe_Constructor_Patterns"></a>   
## Sichere Konstruktormuster  
 Verwenden Sie das folgende Muster, um das Risiko einer unvollständigen Initialisierung zu vermeiden, wenn die Klasse als Basisklasse verwendet wird:  
  
#### Standardkonstruktoren, die die Basisinitialisierung aufrufen  
 Implementieren Sie diese Konstruktoren, die den Basisstandard aufrufen:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### Nicht standardmäßige Konstruktoren, die keinen Basissignaturen entsprechen  
 Wenn diese Konstruktoren Parameter zum Festlegen der Abhängigkeitseigenschaften in der Initialisierung verwenden, rufen Sie zuerst den Standardkonstruktor Ihrer eigenen Klasse für die Initialisierung auf, und verwenden Sie dann die Parameter zum Festlegen der Abhängigkeitseigenschaften.  Hierbei kann es sich entweder um von Ihrer Klasse definierte Abhängigkeitseigenschaften oder um Abhängigkeitseigenschaften handeln, die von den Basisklassen geerbt wurden; verwenden Sie in beiden Fällen das folgende Muster:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### Nicht standardmäßige Konstruktoren, die den Basissignaturen entsprechen  
 Statt den Basiskonstruktor mit der gleichen Parametrisierung aufzurufen, rufen Sie erneut den Standardkonstruktor Ihrer eigenen Klasse auf.  Rufen Sie nicht den Basisinitialisierer auf, sondern stattdessen `this()`.  Reproduzieren Sie dann das Verhalten des ursprünglichen Konstruktors, indem Sie die übergebenen Parameter als Werte zum Festlegen der entsprechenden Eigenschaften verwenden.  Verwenden Sie die Dokumentation zur ursprünglichen Basisklasse als Richtlinie, um die Eigenschaften zu ermitteln, die von den bestimmten Parametern festgelegt werden sollen:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### Muss allen Signaturen entsprechen  
 In Fällen, in denen der Basistyp über mehrere Signaturen verfügt, müssen Sie absichtlich alle möglichen Signaturen mit Ihrer eigenen Konstruktorimplementierung abgleichen, die das empfohlene Muster zum Aufrufen des Standardkonstruktors der Klasse verwendet, bevor Sie weitere Eigenschaften festlegen können.  
  
#### Festlegen von Abhängigkeitseigenschaften mit SetValue  
 Die gleichen Muster finden auch dann Anwendung, wenn Sie eine Eigenschaft festlegen, die nicht über einen Wrapper zum einfacheren Festlegen von Eigenschaften verfügt, und Werte mit <xref:System.Windows.DependencyObject.SetValue%2A> festlegen.  Die Aufrufe von <xref:System.Windows.DependencyObject.SetValue%2A>, die Konstruktorparameter durchlaufen, sollten außerdem den Standardkonstruktor der Klasse zur Initialisierung aufrufen.  
  
## Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)