---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458657"
---
# <a name="xarguments-directive"></a>x:Arguments-Anweisung
Pakete erstellen Argumente für eine nicht parameterlose konstruktorobjektelement-Deklaration in XAML oder für eine Factorymethoden-Objekt Deklaration.  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a>Verwendung von XAML-Elementen (nicht parameterloser Konstruktor)  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Verwendung von XAML-Elementen (Factory-Methode)  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Ein oder mehrere Objekt Elemente, die Argumente angeben, die an den zugrunde liegenden nicht parameterlosen Konstruktor oder die Factorymethode übergeben werden sollen.<br /><br /> Die typische Verwendung besteht darin, den Initialisierungs Text innerhalb der Objekt Elemente zu verwenden, um die eigentlichen Argument Werte anzugeben. Siehe den Abschnitt "Beispiele".<br /><br /> Die Reihenfolge der Elemente ist von Bedeutung. Die XAML-Typen müssen mit den Typen und der Typreihenfolge der Überladung des Unterstützungs Konstruktors oder der Factorymethode identisch sein.|  
|`methodName`|Der Name der Factorymethode, die alle `x:Arguments` Argumente verarbeiten soll.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 `x:FactoryMethod` können den Bereich und das Verhalten ändern, wenn `x:Arguments` gilt.  
  
 Wenn keine `x:FactoryMethod` angegeben ist, gilt `x:Arguments` für Alternative (nicht standardmäßige) Signaturen der Unterstützungs Konstruktoren.  
  
 Wenn `x:FactoryMethod` angegeben wird, gilt `x:Arguments` für eine Überladung der benannten Methode.  
  
## <a name="remarks"></a>Hinweise  
 XAML 2006 kann die nicht standardmäßige Initialisierung durch Initialisierungs Text unterstützen. Die praktische Anwendung einer Initialisierungs Methode für die Erstellung von Text ist jedoch begrenzt. Der Initialisierungs Text wird als eine einzelne Text Zeichenfolge behandelt. Daher wird nur die Funktion für eine einzelne Parameter Initialisierung hinzugefügt, es sei denn, es ist ein Typkonverter für das Konstruktions Verhalten definiert, mit dem benutzerdefinierte Informationselemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysiert werden können. Außerdem ist die Text Zeichenfolge für die Objekt Logik möglicherweise ein angegebener Standard Typkonverter eines XAML-Parsers für die Verarbeitung primitiver Elemente, die keine echte Zeichenfolge sind.  
  
 Die `x:Arguments` XAML-Verwendung ist im typischen Sinn nicht die Verwendung von Eigenschafts Elementen, da das direktivenmarkup nicht auf den Typ des enthaltenden Objekt Elements verweist. Es ähnelt eher anderen Direktiven, wie z. b. `x:Code`, wobei das Element einen Bereich, in dem das Markup interpretiert werden soll, als den Standardwert für den untergeordneten Inhalt demarkiert. In diesem Fall kommuniziert der XAML-Typ jedes Objekt Elements mit Informationen zu den Argument Typen, die von XAML-Parser verwendet werden, um zu bestimmen, welche spezifische konstruktorfactorymethodensignatur eine `x:Arguments` Verwendung versucht, auf zu verweisen.  
  
 `x:Arguments` für ein Objekt Element, das erstellt wird, muss allen anderen Eigenschaften Elementen, Inhalten, inneren Text oder Initialisierungs Zeichenfolgen des Object-Elements vorangestellt sein. Die Objekt Elemente in `x:Arguments` können Attribute und Initialisierungs Zeichenfolgen enthalten, die von diesem XAML-Typ und dessen unterstützungskonstruktor oder Factorymethode zugelassen werden. Für das-Objekt oder das-Argument können Sie benutzerdefinierte XAML-Typen oder XAML-Typen angeben, die sich anderweitig außerhalb des standardmäßigen XAML-Namespace befinden, indem Sie auf festgelegte Präfix Zuordnungen verweisen.  
  
 XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die in `x:Arguments` angegebenen Argumente zum Erstellen eines Objekts verwendet werden sollen. Wenn `x:FactoryMethod` angegeben wird, werden die Informationen mit dem angegebenen `x:FactoryMethod` verglichen (Beachten Sie, dass der Wert von `x:FactoryMethod` der Methodenname ist und die benannte Methode über Ladungen aufweisen kann. Wenn `x:FactoryMethod` nicht angegeben wird, werden die Informationen mit dem Satz aller öffentlichen Konstruktorüberladungen des-Objekts verglichen. Die XAML-Verarbeitungslogik vergleicht dann die Anzahl von Parametern und wählt die Überladung mit passender Stelligkeit aus. Wenn mehrere Übereinstimmungen vorhanden sind, sollte der XAML-Prozessor die Typen der Parameter basierend auf den XAML-Typen der bereitgestellten Objekt Elemente vergleichen. Wenn noch mehr als eine Entsprechung vorhanden ist, ist das XAML-Prozessor Verhalten nicht definiert. Wenn ein `x:FactoryMethod` angegeben, aber die Methode nicht aufgelöst werden kann, sollte ein XAML-Prozessor eine Ausnahme auslösen.  
  
 Eine `<x:Arguments>string</x:Arguments>` für die Verwendung von XAML-Attributen ist technisch möglich. Dies stellt jedoch keine Funktionen bereit, die über das, was andernfalls durch Initialisierungs Text und Typkonverter möglich ist, hinausgehen kann, und die Verwendung dieser Syntax ist nicht die Entwurfs Absicht der Funktionen der XAML 2009-Factorymethode.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt eine nicht parameterlose Konstruktorsignatur, dann die XAML-Verwendung von `x:Arguments`, die auf diese Signatur zugreift.  
  
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
  
 Das folgende Beispiel zeigt die Signatur einer zielfactorymethode, die XAML-Verwendung von `x:Arguments`, die auf diese Signatur zugreift.  
  
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

- [Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
