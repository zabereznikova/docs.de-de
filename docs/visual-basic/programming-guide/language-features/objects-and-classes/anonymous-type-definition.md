---
title: "Anonymous Type Definition (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], type definition"
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Anonymous Type Definition (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Als Reaktion auf die Deklaration einer Instanz eines anonymen Typs erzeugt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften für diesen Typ enthält.  
  
## Vom Compiler generierter Code  
 Für die folgende Definition von `product` erzeugt der Compiler eine neue Klassendefinition, die die Eigenschaften `Name`, `Price` und `OnHand` enthält.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 Die Klassendefinition enthält Eigenschaftendefinitionen, die den folgenden ähneln.  Beachten Sie, dass keine `Set`\-Methode für die Schlüsseleigenschaften vorhanden ist.  Die Werte von Schlüsseleigenschaften sind schreibgeschützt.  
  
```vb#  
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
  
 Weiterhin enthalten Definitionen von anonymen Typen Standardkonstruktoren.  Konstruktoren, die Parameter benötigen, sind nicht zulässig.  
  
 Wenn die Deklaration eines anonymen Typs mindestens eine Schlüsseleigenschaft enthält, überschreibt die Typdefinition drei von <xref:System.Object> geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A>.  Wenn keine Schlüsseleigenschaften deklariert werden, wird nur <xref:System.Object.ToString%2A> überschrieben.  Die Überschreibungen stellen die folgenden Funktionen bereit:  
  
-   `Equals` gibt `True` zurück, wenn zwei Instanzen von anonymen Typen gleich sind oder die folgenden Bedingungen erfüllen:  
  
    -   Sie haben die gleiche Anzahl von Eigenschaften.  
  
    -   Die Eigenschaften werden in der gleichen Reihenfolge mit denselben Namen und denselben abgeleiteten Typen deklariert.  Beim Vergleichen von Namen wird die Groß\- und Kleinschreibung nicht berücksichtigt.  
  
    -   Mindestens eine der Eigenschaften ist eine Schlüsseleigenschaft, und dieselben Eigenschaften sind durch das `Key`\-Schlüsselwort ausgezeichnet.  
  
    -   Der Vergleich jedes Paars von Schlüsseleigenschaften gibt `True` zurück.  
  
     In den folgenden Beispielen gibt `Equals` nur für `employee01` und `employee08` den Wert `True` zurück.  Der Kommentar vor jeder Zeile gibt den Grund an, aus dem die neue Instanz nicht gleich `employee01` ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` stellt einen ausreichend eindeutigen GetHashCode\-Algorithmus bereit.  Der Algorithmus verwendet zur Berechnung des Hashcodes nur die Schlüsseleigenschaften.  
  
-   Wie im folgenden Beispiel gezeigt, gibt `ToString` eine Zeichenfolge verketteter Eigenschaftswerte zurück.  Sie enthält sowohl Schlüsseleigenschaften als auch Nicht\-Schlüsseleigenschaften.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Explizit benannte Eigenschaften eines anonymen Typs dürfen keine Konflikte mit diesen erzeugten Methoden hervorrufen.  Das heißt, Sie können `.Equals`, `.GetHashCode` oder `.ToString` nicht verwenden, um eine Eigenschaft zu benennen.  
  
 Anonyme Typdefinitionen, die mindestens eine Schlüsseleigenschaft enthalten, implementieren auch die <xref:System.IEquatable%601?displayProperty=fullName>\-Schnittstelle, wobei `T` der Typ des anonymen Typs ist.  
  
> [!NOTE]
>  Deklarationen von anonymen Typen erstellen nur dann denselben anonymen Typ, wenn sie sich in derselben Assembly befinden, ihre Eigenschaften dieselben Namen und dieselben abgeleiteten Typen haben, die Eigenschaften in derselben Reihenfolge deklariert werden und dieselben Eigenschaften als Schlüsseleigenschaften gekennzeichnet sind.  
  
## Siehe auch  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)