---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 351974786b9f4748499279d29202e2051d9268fd
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58043328"
---
# <a name="xarguments-directive"></a>x:Arguments-Anweisung
Pakete Konstruktionsargumente für eine Elementdeklaration für nicht-Standardkonstruktors Objekt in XAML oder für eine Factory Methodendeklaration-Objekt.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>XAML-Elementverwendung (nicht standardmäßigen Konstruktor)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>XAML-Elementverwendung (Factorymethode)  
  
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
|`oneOrMoreObjectElements`|Eine oder mehrere Object-Elemente, die angeben, um die dahinter liegende nicht standardmäßigen Konstruktor oder auf die werkseinstellungen-Methode zu übergebenden Argumente.<br /><br /> Typischerweise werden Initialisierungstext in Object-Elemente zu verwenden, um die Werte des tatsächlichen Arguments angeben. Siehe Abschnitt "Beispiele".<br /><br /> Die Reihenfolge der Elemente ist wichtig. Die XAML-Typen in der Reihenfolge müssen den Typen entsprechen, und geben Sie die Reihenfolge der Sicherung oder die Factorymethode Überladung der.|  
|`methodName`|Der Name der Factory-Methode, die alle verarbeiten soll `x:Arguments` Argumente.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 `x:FactoryMethod` können den Bereich und das Verhalten ändern, in denen `x:Arguments` gilt.  
  
 Wenn kein `x:FactoryMethod` angegeben wird, `x:Arguments` gilt für den alternativen (nicht standardmäßige) Signaturen der dahinter liegende Konstruktoren.  
  
 Wenn `x:FactoryMethod` angegeben wird, `x:Arguments` an eine Überladung der die benannte Methode angewendet wird.  
  
## <a name="remarks"></a>Hinweise  
 XAML 2006 können nicht standardmäßigen Initialisierung durch Initialisierungstext unterstützen. Die praktische Anwendung für die eine Initialisierung Text Konstruktion-Methode ist jedoch beschränkt. Initialisierungstext wird als eine einzelne Zeichenfolge behandelt. aus diesem Grund wird nur Funktionen für die Initialisierung eines einzelnen Parameter, wenn ein Typkonverter für das Verhalten der Erstellung definiert ist, die benutzerdefinierten Informationen-Elemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren können. Darüber hinaus ist die Textzeichenfolge, Objekt-Logik möglicherweise einen angegebenen XAML-Parser native Standardtypkonverter für die Behandlung von primitiven als eine Zeichenfolge "true".  
  
 Die `x:Arguments` XAML-Verwendung ist nicht Eigenschaftselementverwendung im typischen Sinn, da das Markup-Direktive nicht der enthaltenden Objekt Typ des Elements verwiesen wird. Es ist z. B. anderen Direktiven `x:Code` , in dem das Element einen Bereich, in denen das Markup interpretiert werden soll, wie Sie sich als den Standardwert für den untergeordneten Inhalt, demarks. In diesem Fall der XAML-Typ, der jedes Objektelement Informationen zu den Argumenttypen, die vom XAML-Parser verwendet wird, um zu bestimmen, welche bestimmten Konstruktor Factory-Methodensignatur kommuniziert eine `x:Arguments` Nutzung zu verweisen versucht.  
  
 `x:Arguments` für ein Objektelement muss erstellt werden alle anderen Eigenschaftenelemente, Inhalte, inneren Text oder Initialisierungszeichenfolgen des Objektelements vorangestellt sein. Die Objektelemente in `x:Arguments` können einschließen, Attribute und Initialisierungszeichenfolgen, gemäß diesen XAML-Typ und die Sicherung oder die Factorymethode-Methode. Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML-Typen oder XAML-Typen, die andernfalls außerhalb des Standard-XAML-Namespaces sind durch Verweisen auf etablierten Präfix-Zuordnungen angeben.  
  
 XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die Argumente in angegeben `x:Arguments` sollte zum Erstellen eines Objekts verwendet werden. Wenn `x:FactoryMethod` angegeben ist, werden Informationen verglichen mit dem angegebenen `x:FactoryMethod` (Beachten Sie, dass der Wert des `x:FactoryMethod` ist der Name der Methode, und die benannte Methode kann Überladungen. Wenn `x:FactoryMethod` nicht angegeben ist, Informationen auf den Satz aller Überladungen suchen öffentlicher Konstruktor des Objekts verglichen. XAML-Verarbeitungslogik vergleicht die Anzahl von Parametern und die Überladung mit übereinstimmenden Stelligkeit auswählt. Wenn mehr als eine Übereinstimmung vorliegt, sollten der XAML-Prozessor die Typen der Parameter auf Grundlage der XAML-Typen, Elemente der bereitgestellten Objekt vergleichen. Wenn Sie noch mehr als eine Übereinstimmung vorliegt, ist das XAML-Prozessor-Verhalten nicht definiert. Wenn eine `x:FactoryMethod` angegeben ist, aber die Methode kann nicht aufgelöst werden, ein XAML-Prozessor sollte eine Ausnahme auslösen.  
  
 Ein XAML-Attributverwendung `<x:Arguments>string</x:Arguments>` ist es technisch möglich ist. Allerdings dadurch, dass keine Funktionen über was andernfalls über Initialisierung und -Typkonverter durchgeführt werden konnte, und mit dieser Syntax ist nicht der Zweck der XAML 2009-Funktionen für die Factory-Methode.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt einen nicht standardmäßigen Konstruktor Signatur, und klicken Sie dann auf die XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.  
  
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
  
 Das folgende Beispiel zeigt die Signatur einer Ziel-Factory-Methode, und klicken Sie dann auf die XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.  
  
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
- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
