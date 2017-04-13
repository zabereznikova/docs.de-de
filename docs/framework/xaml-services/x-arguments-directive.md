---
title: "x:Arguments Directive | Microsoft Docs"
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
  - "x:Arguments directive [XAML Services]"
  - "Arguments directive in XAML [XAML Services]"
  - "XAML [XAML Services], x:Arguments directive"
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Arguments Directive
Packt Konstruktionsargumente für eine nicht standardmäßige Konstruktor\-Objektelementdeklaration in XAML oder für eine Factorymethoden\-Objektdeklaration.  
  
## Verwendung von XAML\-Elementen \(nicht standardmäßiger Konstruktor\)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## Verwendung von XAML\-Elementen \(Factorymethode\)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Mindestens ein Objektelement, das Argumente angibt, die an den nicht standardmäßigen Unterstützungskonstruktor oder die Factorymethode übergeben werden sollen.<br /><br /> Typische Verwendung ist die Nutzung von Initialisierungstext in Objektelementen, um die tatsächlichen Argumentwerte anzugeben.  Weitere Informationen finden Sie im Beispielabschnitt.<br /><br /> Die Reihenfolge der Elemente ist von Bedeutung.  Die geordneten XAML\-Typen müssen mit den Typen und der Typreihenfolge des Unterstützungskonstruktors oder der Factorymethodenüberladung übereinstimmen.|  
|`methodName`|Der Name der Factory\-Methode, die alle `x:Arguments`\-Argumente verarbeiten soll.|  
  
## Abhängigkeiten  
 `x:FactoryMethod` kann den Bereich und das Verhalten, in dem `x:Arguments` gültig ist, ändern.  
  
 Wenn kein `x:FactoryMethod`\-Element angegeben wird, gilt `x:Arguments` für alternative \(nicht standardmäßig\) Signaturen der Unterstützungskonstruktoren.  
  
 Wenn `x:FactoryMethod` angegeben wird, gilt `x:Arguments` für eine Überlastung der benannten Methode.  
  
## Hinweise  
 XAML 2006 kann nicht standardmäßige Initialisierung durch Initialisierungstext unterstützen.  Die praktische Anwendung einer Initialisierungstextkonstruktionstechnik ist jedoch beschränkt.  Initialisierungstext wird als einzelne Textzeichenfolge behandelt. Er fügt daher nur die Möglichkeit für eine einzelne Parameterinitialisierung hinzu, es sei denn, ein Typkonverter ist für das Konstruktionsverhalten definiert, das benutzerdefinierte Informationselemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren kann.  Außerdem ist die Textzeichenfolge\-zu\-Objekt\-Logik potenziell der systemeigene Standardtypkonverter eines angegebenen XAML\-Parsers zur Behandlung anderer Primitive als eine wahre Zeichenfolge.  
  
 Die Verwendung von `x:Arguments`\-XAML ist keine Eigenschaftenelementverwendung im typischen Sinn, da das Direktivenmarkup nicht auf den Objekttyp des enthaltenen Elements verweist.  Es ist anderen Direktiven, z. B. `x:Code`, ähnlicher, wo das Element einen Bereich ausweist, in dem das Markup als vom standardmäßigen Inhalt für untergeordnete Elemente abweichend interpretiert werden soll.  In diesem Fall übermittelt der XAML\-Typ jedes Objektelements Informationen über die Argumenttypen, mit denen XAML\-Parser bestimmen, auf welche spezifische Konstruktor\-\/Factory\-Methodensignatur eine `x:Arguments`\-Verwendung zu verweisen versucht.  
  
 `x:Arguments` für ein Objektelement, das erstellt wird, muss anderen Eigenschaftenelementen, Inhalt, innerem Text oder Initialisierungszeichenfolgen des Objektelements vorangestellt werden.  Die Objektelemente in `x:Arguments` können Attribute und Initialisierungszeichenfolgen enthalten, wie durch diesen XAML\-Typ und seinen Unterstützungskonstruktor oder die Factory\-Methode zulässig.  Entweder für das Objekt oder die Argumente können Sie benutzerdefinierte XAML\-Typen oder XAML\-Typen angeben, die andernfalls außerhalb des XAML\-Standardnamespace sind, indem auf eingerichtete Präfixzuordnungen verwiesen wird.  
  
 XAML\-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die Argumente, die in `x:Arguments` angegeben sind, verwendet werden sollen, um ein Objekt zu erstellen.  Wenn `x:FactoryMethod` angegeben wird, werden Informationen mit der angegebenen `x:FactoryMethod` verglichen. Beachten Sie, dass der Wert von `x:FactoryMethod` der Methodenname ist und die benannte Methode Überladungen besitzen kann.  Wenn `x:FactoryMethod` nicht angegeben wird, werden Informationen mit der Menge aller öffentlichen Konstruktorüberladungen des Objekts verglichen.  XAML\-Verarbeitungslogik vergleicht dann die Anzahl der Parameter und wählt die Überladung mit entsprechender Stelligkeit aus.  Wenn es mehr als eine Übereinstimmung gibt, sollte der XAML\-Prozessor Typen der Parameter auf Grundlage des XAML\-Typen der bereitgestellten Objektelemente vergleichen.  Wenn es noch immer mehr als eine Übereinstimmung gibt, ist das Verhalten des XAML\-Prozessors nicht definiert.  Wenn `x:FactoryMethod` angegeben ist, aber die Methode nicht aufgelöst werden kann, sollte ein XAML\-Prozessor eine Ausnahme auslösen.  
  
 Eine XAML\-Attributverwendung `<x:Arguments>string</x:Arguments>` ist technisch möglich.  Dies bietet jedoch keine Funktionen über das hinaus, was über Initialisierungstext und Typkonverter durchgeführt werden könnte, und die Verwendung dieser Syntax ist nicht der Zweck der Funktionen der XAML 2009\-Factorymethode.  
  
## Beispiele  
 Im folgenden Beispiel werden eine nicht standardmäßige Konstruktorsignatur und dann die XAML\-Verwendung von `x:Arguments` veranschaulicht, die auf diese Signatur zugreift.  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 Im folgenden Beispiel werden eine Signatur einer Ziel\-Factory\-Methode und dann die XAML\-Verwendung von `x:Arguments` veranschaulicht, die auf diese Signatur zugreift.  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## Siehe auch  
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)   
 [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)