---
title: virtual (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dce3333646bca6f558e3760849b6cffdb34a6c0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-c-reference"></a>virtual (C#-Referenz)
Das Schlüsselwort `virtual` wird zum Ändern einer Methoden-, Eigenschaften-, Indexer- oder Ereignisdeklaration verwendet, und lässt zu, dass sie in einer abgeleiteten Klasse außer Kraft gesetzt werden. Diese Methode kann z.B. von jeder Klasse, die sie erbt, überschrieben werden:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 Die Implementierung eines virtuellen Members kann durch einen [overriding member](../../../csharp/language-reference/keywords/override.md) (überschreibender Member) in einer abgeleiteten Klasse geändert werden. Weitere Informationen zur Verwendung des `virtual`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine virtuelle Methode aufgerufen wird, wird der Laufzeittyp des Objekts auf einen überschreibenden Member überprüft. Der überschreibende Member in der abgeleitetsten Klasse (bei dem es sich um den ursprünglichen Member handeln könnte) wird aufgerufen, wenn keine abgeleitete Klasse den Member außer Kraft gesetzt hat.  
  
 Standardmäßig sind Methoden nicht virtuell. Sie können keine nicht virtuelle Methode überschreiben.  
  
 Sie können keine der `virtual` Modifizierer mit der `static`, `abstract`, `private`, oder `override` Modifizierer. Im folgenden Beispiel wird eine virtuelle Methode gezeigt:  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Virtuelle Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.  
  
-   Es ist unzulässig, den `virtual`-Modifizierer für eine statische Eigenschaft zu verwenden.  
  
-   Eine virtuelle vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer `override` verwendet, außer Kraft gesetzt werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel enthält die Klasse `Shape` die zwei Koordinaten `x` und `y` und die virtuelle Methode `Area()`. Andere Formklassen, z.B. `Circle`, `Cylinder` und `Sphere` erben die Klasse `Shape`. Die Oberfläche wird für jede Abbildung berechnet. Jede abgeleitete Klasse verfügt über Ihre eigene Überschreibungsimplementierung von `Area()`.  
  
 Beachten Sie, dass die geerbten Klassen `Circle`, `Sphere` und `Cylinder` alle Konstruktoren verwenden, die die Basisklasse initialisieren, wie in der folgenden Deklaration gezeigt.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 Das folgende Programm berechnet und zeigt den entsprechenden Bereich für jede Abbildung durch Aufruf der entsprechenden Implementierung der `Area()`-Methode gemäß dem Objekt, das der Methode zugeordnet ist.  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)  
 [override](../../../csharp/language-reference/keywords/override.md)  
 [new](../../../csharp/language-reference/keywords/new.md)
