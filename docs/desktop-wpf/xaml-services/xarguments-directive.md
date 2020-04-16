---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432833"
---
# <a name="xarguments-directive"></a>x:Arguments-Anweisung

Verpackt Konstruktionsargumente für eine nicht parametrlose Konstruktorobjektelementdeklaration in XAML oder für eine Factory-Methodenobjektdeklaration.

## <a name="xaml-element-usage-nonparameterless-constructor"></a>XAML-Elementverwendung (nicht parameterloser Konstruktor)

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a>XAML-Elementverwendung (Werksmethode)

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
|`oneOrMoreObjectElements`|Mindestens ein Objektelement, das Argumente angibt, die an den nicht parameterlosen Konstruktor oder die Factorymethode übergeben werden sollen.<br /><br /> Typische Verwendung besteht darin, Initialisierungstext innerhalb der Objektelemente zu verwenden, um die tatsächlichen Argumentwerte anzugeben. Siehe Abschnitt Beispiele.<br /><br /> Die Reihenfolge der Elemente ist signifikant. Die XAML-Typen müssen in der Reihenfolge mit den Typen und der Typreihenfolge des Sicherungskonstruktors oder der Werksmethode überlasten.|
|`methodName`|Der Name der Factorymethode, `x:Arguments` die alle Argumente verarbeiten soll.|

## <a name="dependencies"></a>Abhängigkeiten

`x:FactoryMethod`kann den Bereich und `x:Arguments` das Verhalten ändern, wo dies angewendet wird.

Wenn `x:FactoryMethod` nein `x:Arguments` angegeben ist, gilt für alternative (nicht standardmäßige) Signaturen der Sicherungskonstruktoren.

Wenn `x:FactoryMethod` angegeben, `x:Arguments` gilt für eine Überladung der benannten Methode.

## <a name="remarks"></a>Bemerkungen

XAML 2006 kann die nicht standardmäßige Initialisierung durch Initialisierungstext unterstützen. Die praktische Anwendung einer Initialisierungstextkonstruktionstechnik ist jedoch begrenzt. Initialisierungstext wird als einzelne Textzeichenfolge behandelt. Daher wird nur die Funktion für eine einzelne Parameterinitialisierung hinzugefügt, es sei denn, für das Konstruktionsverhalten wird ein Typkonverter definiert, der benutzerdefinierte Informationselemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren kann. Außerdem ist die Textzeichenfolge für die Objektlogik potenziell der systemeigene Standardtypkonverter eines bestimmten XAML-Parsers für die Behandlung anderer Primitive randals als eine echte Zeichenfolge.

Die `x:Arguments` XAML-Verwendung ist keine Eigenschaftselementverwendung im typischen Sinne, da das Direktivenmarkup nicht auf den Typ des enthaltenden Objektelements verweist. Sie ähnelt eher anderen Direktiven, z. `x:Code` B. wenn das Element einen Bereich markiert, in dem das Markup als andere als die Standardeinstellung für untergeordnete Inhalte interpretiert werden soll. In diesem Fall übermittelt der XAML-Typ jedes Objektelements Informationen über die Argumenttypen, die von XAML-Parsern verwendet werden, um zu bestimmen, auf welche bestimmte Konstruktorfactory-Factory-Methodensignatur eine `x:Arguments` Verwendung zu verweisen versucht.

`x:Arguments`Denn ein Objektelement, das erstellt wird, muss allen anderen Eigenschaftselementen, Inhalten, inneninneren Text- oder Initialisierungszeichenfolgen des Objektelements vorangestellt werden. Die darin `x:Arguments` enthaltenden Objektelemente können Attribute und Initialisierungszeichenfolgen enthalten, wie von diesem XAML-Typ und seiner Sicherungskonstruktor- oder Factorymethode zugelassen. Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML-Typen oder XAML-Typen angeben, die sich ansonsten außerhalb des standardmäßigen XAML-Namespace befinden, indem Sie auf etablierte Präfixzuordnungen verweisen.

XAML-Prozessoren verwenden die folgenden Richtlinien, `x:Arguments` um zu bestimmen, wie die in angegebenen Argumente zum Erstellen eines Objekts verwendet werden sollen. Wenn `x:FactoryMethod` angegeben, werden Informationen mit `x:FactoryMethod` den angegebenen verglichen `x:FactoryMethod` (beachten Sie, dass der Wert des Methodennamens ist und die benannte Methode Überladungen aufweisen kann. Wenn `x:FactoryMethod` nicht angegeben, werden Informationen mit dem Satz aller öffentlichen Konstruktorüberladungen des Objekts verglichen. Die XAML-Verarbeitungslogik vergleicht dann die Anzahl der Parameter und wählt die Überlast mit der übereinstimmenden Arity aus. Wenn mehr als eine Übereinstimmung vorhanden ist, sollte der XAML-Prozessor die Typen der Parameter basierend auf den XAML-Typen der bereitgestellten Objektelemente vergleichen. Wenn immer noch mehr als eine Übereinstimmung vorhanden ist, ist das XAML-Prozessorverhalten nicht definiert. Wenn `x:FactoryMethod` a angegeben ist, die Methode jedoch nicht aufgelöst werden kann, sollte ein XAML-Prozessor eine Ausnahme auslösen.

Eine XAML-Attributverwendung `<x:Arguments>string</x:Arguments>` ist technisch möglich. Dies bietet jedoch keine Funktionen, die über das hinausgehen, was andernfalls durch Initialisierung von Text- und Typkonvertern getan werden könnte, und die Verwendung dieser Syntax ist nicht die Entwurfsabsicht der XAML 2009-Factory-Methodenfeatures.

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt eine nicht parameterlose Konstruktorsignatur, `x:Arguments` und dann greift die XAML-Verwendung dieser Signatur auf diese Signatur zu.

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

Das folgende Beispiel zeigt eine Zielfactory-Methodensignatur und `x:Arguments` dann die XAML-Verwendung dieser Signatur.

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

## <a name="see-also"></a>Weitere Informationen

- [Definieren benutzerdefinierter Typen für die Verwendung in .NET-XAML-Diensten](define-custom-types.md)
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
