---
title: x:Arguments-Direktive
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 00f605bba709f0ce5f3238ccc3c6ac6cd962f0a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xarguments-directive"></a>x:Arguments-Direktive
Pakete Konstruktionsargumente für einen nicht standardmäßigen Konstruktor Element Objektdeklaration in XAML oder eine Objektdeklaration der Factory-Methode.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>XAML-Elementverwendung (nicht standardmäßigen Konstruktor)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>XAML-Elementverwendung (Factory-Methode)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objektelemente, die Argumente angeben, die an die dahinter liegende nicht standardmäßiger Konstruktor oder eine Factory-Methode übergeben werden.<br /><br /> Typische Verwendung ist, Initialisierungstext innerhalb der Objektelemente zu verwenden, um die tatsächliche Argumentwerte anzugeben. Siehe Abschnitt "Beispiele".<br /><br /> Die Reihenfolge der Elemente ist wichtig. Die Verwendung von XAML-Typen in der Reihenfolge müssen den Typen entsprechen und geben Sie die Reihenfolge der methodenüberladung für das dahinter liegende Konstruktor oder eine Factory.|  
|`methodName`|Der Name der Factorymethode, die alle verarbeiten soll `x:Arguments` Argumente.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 `x:FactoryMethod`der Bereich und das Verhalten ändern können, in denen `x:Arguments` gilt.  
  
 Wenn kein `x:FactoryMethod` angegeben wird, `x:Arguments` alternativen (nicht standardmäßige) Signaturen der dahinter liegende Konstruktoren betrifft.  
  
 Wenn `x:FactoryMethod` angegeben wird, `x:Arguments` an eine Überladung der Methode mit dem Namen gilt.  
  
## <a name="remarks"></a>Hinweise  
 XAML 2006 können nicht standardmäßigen Initialisierung durch Initialisierungstext unterstützen. Die praktische Anwendung eine Initialisierung Text Konstruktion Technik ist jedoch beschränkt. Initialisierungstext wird als eine einzelne Zeichenfolge behandelt; Daher fügt er nur-Funktion für die Initialisierung eines einzelnen Parameter, wenn ein Typkonverter für das Konstruktionsverhalten definiert ist, die benutzerdefinierte Informationselementen und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren können. Darüber hinaus ist die Textzeichenfolge, Objekt-Logik potenziell einen angegebenen XAML-Parser systemeigene Typkonverter für das Behandeln von primitiven als eine Zeichenfolge mit "true".  
  
 Die `x:Arguments` XAML-Verwendung ist nicht Eigenschaftenelementen insofern typisch, da die Richtlinie Markup nicht des enthaltenden Objektelements Typ verweist. Es ist z. B. andere Direktiven, die eher `x:Code` , in dem das Element ein Bereichs, in dem das Markup interpretiert werden soll, wie der Standardnummer Inhalt für untergeordnete, demarks. In diesem Fall der Verwendung von XAML-Typ jedes Elements des Objekts Informationen zu den Typen, die XAML-Parser verwendet wird, um zu bestimmen, welche bestimmten Konstruktor Factory-Methodensignatur kommuniziert ein `x:Arguments` Verwendung verweisen möchten.  
  
 `x:Arguments`für ein Object-Element muss zu erstellenden alle anderen Eigenschaftenelemente, Inhalte, innere Text oder Initialisierungszeichenfolgen des Object-Element vorangestellt sein. Die Objektelemente in `x:Arguments` zählen Attribute und Initialisierungszeichenfolgen, gemäß diesem XAML-Typ und die dahinter liegende Konstruktor oder eine Factory-Methode. Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML- oder XAML-Typen, die andernfalls außerhalb der Verwendung von XAML-Standardnamespace sind durch Verweisen auf die eingerichtete/Präfix-Zuordnungen angeben.  
  
 Verwendung von XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die Argumente in angegeben `x:Arguments` sollte verwendet werden, um ein Objekt zu erstellen. Wenn `x:FactoryMethod` angegeben ist, werden die Informationen werden verglichen mit dem angegebenen `x:FactoryMethod` (Beachten Sie, dass der Wert des `x:FactoryMethod` ist der Name der Methode, und die benannte Methode kann Überladungen. Wenn `x:FactoryMethod` nicht angegeben ist, werden die Informationen auf den Satz von Überladungen, die alle öffentlichen Konstruktor des Objekts verglichen wird. Verwendung von XAML-Verarbeitungslogik vergleicht die Anzahl von Parametern und wählt die Überladung ohne übereinstimmende Stelligkeit. Wenn mehr als eine Übereinstimmung vorhanden ist, sollte der XAML-Prozessor die Typen der Parameter auf Grundlage der Verwendung von XAML-Typen der bereitgestellten Objektelemente vergleichen. Wenn noch mehr als eine Übereinstimmung vorhanden ist, ist die Verwendung von XAML-Prozessor-Verhalten nicht definiert. Wenn eine `x:FactoryMethod` angegeben ist, aber die Methode kann nicht aufgelöst werden, sollte ein XAML-Prozessor eine Ausnahme auslösen.  
  
 Eine Verwendung von XAML-Attributen `<x:Arguments>string</x:Arguments>` technisch möglich ist. Allerdings Dies bietet keine Funktionen über hinaus, was andernfalls durch Initialisierung und -Typkonverter erzielt werden kann, und mithilfe dieser Syntax ist nicht die Absicht Entwurf der XAML 2009-Funktionen für die Factory-Methode.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt einen Standardkonstruktor, Signatur, und klicken Sie dann auf die Verwendung von XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.  
  
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
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 Das folgende Beispiel zeigt die Signatur einer Ziel-Factory-Methode, und klicken Sie dann auf die Verwendung von XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.  
  
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
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
