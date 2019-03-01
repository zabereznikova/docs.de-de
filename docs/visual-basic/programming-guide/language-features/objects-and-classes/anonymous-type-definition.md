---
title: Definition von anonymen Typen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: e74b4c7298a80f724031cc4ac1feb49ebae8f7cb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975614"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definition von anonymen Typen (Visual Basic)
Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für den Typ enthält.  
  
## <a name="compiler-generated-code"></a>Vom Compiler generierter Code  
 Für die folgende Definition `product`, erstellt der Compiler eine neue Klassendefinition, die Eigenschaften enthält `Name`, `Price`, und `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]  
  
 Die Definition der Klasse enthält die Eigenschaftsdefinitionen, die etwa wie folgt. Beachten Sie, dass es keine `Set` -Methode für die wichtigsten Eigenschaften. Die Werte der Eigenschaften sind schreibgeschützt.  
  
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
  
 Darüber hinaus enthalten die Definitionen von anonymen Typen einen standardmäßigen Konstruktor. Konstruktoren, die Parameter erfordern, sind nicht zulässig.  
  
 Wenn die Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von geerbte Member <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>. Wenn keine Eigenschaften, nur deklariert werden <xref:System.Object.ToString%2A> überschrieben wird. Die Außerkraftsetzungen werden die folgenden Funktionen enthalten:  
  
-   `Equals` Gibt `True` Wenn zwei Instanzen eines anonymen Typs dieselbe Instanz sind oder wenn sie die folgenden Bedingungen erfüllen:  
  
    -   Sie haben die gleiche Anzahl von Eigenschaften.  
  
    -   Die Eigenschaften werden deklariert, in der gleichen Reihenfolge, mit dem gleichen Namen und denselben abgeleiteten Typen. Beim Vergleichen wird nicht beachtet werden.  
  
    -   Mindestens eine der Eigenschaften ist eine wichtige Eigenschaft, und die `Key` -Schlüsselwort auf die gleichen Eigenschaften angewendet wird.  
  
    -   Vergleich der einzelnen entsprechenden Schlüsseleigenschaften gibt `True`.  
  
     In den folgenden Beispielen wird z. B. `Equals` gibt `True` nur für `employee01` und `employee08`. Der Kommentar vor jeder Zeile gibt den Grund an, warum die neue Instanz stimmt nicht überein `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]  
  
-   `GetHashcode` Stellt einen entsprechend eindeutigen GetHashCode-Algorithmus bereit. Der Algorithmus verwendet nur die wichtigsten Eigenschaften, um den Hash zu berechnen.  
  
-   `ToString` Gibt eine Zeichenfolge mit verketteten Eigenschaftswerte zurück, wie im folgenden Beispiel gezeigt. Sowohl Schlüssel als auch nicht schlüsselbezogene Eigenschaften sind enthalten.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]  
  
 Explizit benannte Eigenschaften eines anonymen Typs können nicht in Konflikt mit diesen generierten Methoden stehen. D. h. Sie können keine `.Equals`, `.GetHashCode`, oder `.ToString` um eine Eigenschaft zu nennen.  
  
 Definitionen von anonymen Typen, die über mindestens einen Schlüsseleigenschaft auch implementieren die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle, in denen `T` ist der Typ des anonymen Typs.  
  
> [!NOTE]
>  Deklarationen von anonymen Typen erstellen desselben anonymen Typs nur dann, wenn die Zeitpunkte in der gleichen Assembly, deren Eigenschaften die gleichen Namen haben und denselben Typen abgeleiteten, die Eigenschaften in der gleichen Reihenfolge deklariert werden und die gleichen Eigenschaften werden als Schlüsseleigenschaften gekennzeichnet.  
  
## <a name="see-also"></a>Siehe auch
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
