---
title: Definition von anonymen Typen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a>Definition von anonymen Typen (Visual Basic)
Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für den Typ enthält.  
  
## <a name="compiler-generated-code"></a>Vom Compiler generierter Code  
 Für die folgende Definition `product`, erstellt der Compiler eine neue Klassendefinition, die Eigenschaften enthält `Name`, `Price`, und `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 Definition der Klasse enthält die Eigenschaftsdefinitionen, die etwa wie folgt. Beachten Sie, dass es keine `Set` Methode für die Schlüsseleigenschaften. Die Werte der Eigenschaften sind schreibgeschützt.  
  
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
  
 Darüber hinaus enthalten Definitionen von anonymen Typ einen Standardkonstruktor. Konstruktoren, die Parameter erforderlich sind, sind nicht zulässig.  
  
 Wenn die Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von geerbte Membern <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>. Wenn keine Schlüsseleigenschaften, nur deklariert werden <xref:System.Object.ToString%2A> überschrieben wird. Die Außerkraftsetzungen bieten die folgenden Funktionen:  
  
-   `Equals`Gibt `True` Wenn zwei Instanzen eines anonymen Typs dieselbe Instanz sind oder wenn sie die folgenden Bedingungen erfüllen:  
  
    -   Sie haben die gleiche Anzahl von Eigenschaften.  
  
    -   Die Eigenschaften werden deklariert, in der gleichen Reihenfolge mit den gleichen Namen und denselben abgeleiteten Typen. Vergleichen des wird die Groß-und Kleinschreibung nicht berücksichtigt.  
  
    -   Mindestens eine der Eigenschaften ist eine wichtige Eigenschaft und die `Key` -Schlüsselwort auf die gleichen Eigenschaften angewendet wird.  
  
    -   Vergleich von jedes Paars von Schlüsseleigenschaften gibt `True`.  
  
     Beispielsweise ist in den folgenden Beispielen wird `Equals` gibt `True` nur für `employee01` und `employee08`. Der Kommentar vor jeder Zeile gibt den Grund an, warum die neue Instanz stimmt nicht überein `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode`Stellt einen entsprechend eindeutigen GetHashCode-Algorithmus bereit. Der Algorithmus verwendet nur die wichtigsten Eigenschaften den Hashcode berechnet.  
  
-   `ToString`Gibt eine Zeichenfolge von verketteten Eigenschaftswerte zurück, wie im folgenden Beispiel gezeigt. Schlüssel und nicht schlüsselbezogene Eigenschaften sind enthalten.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Explizit benannte Eigenschaften eines anonymen Typs können nicht mit diesen generierten Methoden in Konflikt stehen. D. h., Sie können keine `.Equals`, `.GetHashCode`, oder `.ToString` um eine Eigenschaft zu benennen.  
  
 Anonyme Typdefinitionen, die mindestens einen Schlüsseleigenschaft auch implementieren die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle, wobei `T` ist der Typ des anonymen Typs.  
  
> [!NOTE]
>  Deklarationen von anonymen Typen erstellen desselben anonymen Typs nur dann, wenn die Zeitpunkte in der gleichen Assembly, deren Eigenschaften, die denselben Namen haben und dieselben Typen abgeleiteten, die Eigenschaften in der gleichen Reihenfolge deklariert werden und die gleichen Eigenschaften als Schlüsseleigenschaften gekennzeichnet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
