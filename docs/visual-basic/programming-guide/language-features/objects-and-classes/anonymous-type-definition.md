---
title: Definition von anonymen Typen
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: f8ac26577a7fbef865605a7ecf643fa733b2c2c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344918"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definition von anonymen Typen (Visual Basic)

Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für den Typ enthält.

## <a name="compiler-generated-code"></a>Vom Compiler generierter Code

Für die folgende Definition von `product`erstellt der Compiler eine neue Klassendefinition, die Eigenschaften `Name`, `Price`und `OnHand`enthält.

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

Die Klassendefinition enthält Eigenschafts Definitionen ähnlich der folgenden. Beachten Sie, dass es keine `Set` Methode für die Schlüsseleigenschaften gibt. Die Werte der Schlüsseleigenschaften sind schreibgeschützt.

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

Außerdem enthalten anonyme Typdefinitionen einen Parameter losen Konstruktor. Konstruktoren, die Parameter erfordern, sind nicht zulässig.

Wenn eine Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von <xref:System.Object>geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>und <xref:System.Object.ToString%2A>. Wenn keine Schlüsseleigenschaften deklariert werden, wird nur <xref:System.Object.ToString%2A> überschrieben. Die außer Kraft setzungen bieten die folgenden Funktionen:

- `Equals` gibt `True` zurück, wenn zwei Instanzen des anonymen Typs dieselbe Instanz sind oder wenn Sie die folgenden Bedingungen erfüllen:

  - Sie verfügen über die gleiche Anzahl von Eigenschaften.

  - Die Eigenschaften werden in derselben Reihenfolge deklariert, mit denselben Namen und denselben abhergenten Typen. Bei namens vergleichen wird die Groß-/Kleinschreibung nicht beachtet

  - Mindestens eine der Eigenschaften ist eine Schlüsseleigenschaft, und das `Key`-Schlüsselwort wird auf die gleichen Eigenschaften angewendet.

  - Beim Vergleich der einzelnen entsprechenden paar Schlüsseleigenschaften wird `True`zurückgegeben.

    In den folgenden Beispielen gibt `Equals` z. b. nur für `employee01` und `employee08``True` zurück. Der Kommentar vor jeder Zeile gibt den Grund an, warum die neue Instanz nicht mit `employee01`übereinstimmt.

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` stellt einen entsprechend eindeutigen GetHashCode-Algorithmus bereit. Der Algorithmus verwendet nur die Schlüsseleigenschaften, um den Hashcode zu berechnen.

- `ToString` gibt eine Zeichenfolge mit verketteten Eigenschafts Werten zurück, wie im folgenden Beispiel gezeigt. Es sind sowohl Schlüssel-als auch nicht Schlüsseleigenschaften enthalten.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Explizit benannte Eigenschaften eines anonymen Typs können nicht mit diesen generierten Methoden in Konflikt stehen. Das heißt, Sie können `.Equals`, `.GetHashCode`oder `.ToString` nicht verwenden, um eine Eigenschaft zu benennen.

Anonyme Typdefinitionen, die mindestens eine Schlüsseleigenschaft enthalten, implementieren auch die <xref:System.IEquatable%601?displayProperty=nameWithType>-Schnittstelle, wobei `T` der Typ des anonymen Typs ist.

> [!NOTE]
> Deklarationen anonymer Typen erstellen nur dann denselben anonymen Typ, wenn Sie in derselben Assembly auftreten, deren Eigenschaften dieselben Namen und die gleichen abhergenten Typen aufweisen, die Eigenschaften in der gleichen Reihenfolge deklariert werden und dieselben Eigenschaften als Schlüsseleigenschaften gekennzeichnet sind.

## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
