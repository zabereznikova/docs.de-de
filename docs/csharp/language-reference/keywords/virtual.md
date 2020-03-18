---
title: virtual – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 883e0a7f833c15d2c1cce6b3d52d16aad01a5cd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173457"
---
# <a name="virtual-c-reference"></a>virtual (C#-Referenz)

Das Schlüsselwort `virtual` wird zum Ändern einer Methoden-, Eigenschaften-, Indexer- oder Ereignisdeklaration verwendet, und lässt zu, dass sie in einer abgeleiteten Klasse außer Kraft gesetzt werden. Diese Methode kann z.B. von jeder Klasse, die sie erbt, überschrieben werden:

```csharp
public virtual double Area()
{
    return x * y;
}
```

Die Implementierung eines virtuellen Members kann durch einen [overriding member](override.md) (überschreibenden Member) in einer abgeleiteten Klasse geändert werden. Weitere Informationen zur Verwendung des `virtual`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="remarks"></a>Hinweise

Wenn eine virtuelle Methode aufgerufen wird, wird der Laufzeittyp des Objekts auf einen überschreibenden Member überprüft. Der überschreibende Member in der abgeleitetsten Klasse (bei dem es sich um den ursprünglichen Member handeln könnte) wird aufgerufen, wenn keine abgeleitete Klasse den Member außer Kraft gesetzt hat.

Standardmäßig sind Methoden nicht virtuell. Sie können keine nicht virtuelle Methode überschreiben.

Sie können den Modifizierer `virtual` nicht mit den Modifizierern `static`, `abstract`, `private` oder `override` verwenden. Im folgenden Beispiel wird eine virtuelle Methode gezeigt:

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Virtuelle Eigenschaften verhalten sich wie virtuelle Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.

- Es ist ein unzulässig, den `virtual`-Modifizierer für eine statische Eigenschaft zu verwenden.

- Eine virtuelle vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer `override` verwendet, außer Kraft gesetzt werden.

## <a name="example"></a>Beispiel

In diesem Beispiel enthält die Klasse `Shape` die zwei Koordinaten `x` und `y` und die virtuelle Methode `Area()`. Andere Formklassen, z.B. `Circle`, `Cylinder` und `Sphere` erben die Klasse `Shape`. Die Oberfläche wird für jede Abbildung berechnet. Jede abgeleitete Klasse verfügt über ihre eigene Überschreibungsimplementierung von `Area()`.

Beachten Sie, dass die geerbten Klassen `Circle`, `Sphere` und `Cylinder` alle Konstruktoren verwenden, die die Basisklasse initialisieren, wie in der folgenden Deklaration gezeigt.

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

Das folgende Programm berechnet und zeigt den entsprechenden Bereich für jede Abbildung durch Aufruf der entsprechenden Implementierung der `Area()`-Methode gemäß dem Objekt, das der Methode zugeordnet ist.

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [Polymorphismus](../../programming-guide/classes-and-structs/polymorphism.md)
- [abstract](abstract.md)
- [override](override.md)
- [new (Modifizierer)](new-modifier.md)
