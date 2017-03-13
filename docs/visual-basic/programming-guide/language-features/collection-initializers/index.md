---
title: "Collection Initializers (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CollectionInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Collection Initializers (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Auflistungsinitialisierer* stellen eine Kurzsyntax bereit, mit der Sie eine Auflistung erstellen und mit einer Reihe von Anfangswerten auffüllen können.  Auflistungsinitialisierer sind hilfreich, wenn Sie eine Auflistung aus einer Reihe von bekannten Werten erstellen, beispielsweise einer Liste von Menüoptionen oder Kategorien, einem Anfangssatz von numerischen Werten, einer statischen Liste von Zeichenfolgen wie Tages\- oder Monatsnamen oder geografischer Positionen wie einer Liste von Staaten, die zur Validierung verwendet wird.  
  
 Weitere Informationen über Auflistungen finden Sie unter [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Ein Auflistungsinitialisierer wird mit dem `From`\-Schlüsselwort gefolgt von geschweiften Klammern \(`{}`\) bezeichnet.  Dies ähnelt der Arrayliteralsyntax, die in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) beschrieben wird.  In den folgenden Beispielen werden verschiedene Möglichkeiten der Verwendung von Auflistungsinitialisierern zum Erstellen von Auflistungen gezeigt.  
  
 [!code-vb[VbVbalrCollectionInitializers#1](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Auch in C\# werden Auflistungsinitialisierer bereitgestellt.  C\#\-Auflistungsinitialisierer stellen dieselben Funktionen wie Visual Basic\-Auflistungsinitialisierer bereit.  Weitere Informationen über C\#\-Auflistungsinitialisierer finden Sie unter [Objekt\- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Syntax  
 Ein Auflistungsinitialisierer besteht aus einer Liste von durch Trennzeichen getrennten Werten, die in geschweifte Klammern \(`{}`\) eingeschlossen werden, wobei das `From`\-Schlüsselwort vorangestellt wird, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbVbalrCollectionInitializers#2](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_2.vb)]  
  
 Wenn Sie eine Auflistung wie <xref:System.Collections.Generic.List%601> oder <xref:System.Collections.Generic.Dictionary%602> erstellen, müssen Sie den Auflistungstyp vor dem Auflistungsinitialisierer angeben, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbVbalrCollectionInitializers#13](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_3.vb)]  
  
> [!NOTE]
>  Sie können zum Initialisieren des gleichen Auflistungsobjekts nicht beides kombinieren, einen Auflistungsinitialisierer und einen Objektinitialisierer.  Mit Objektinitialisierern können Sie Objekte in einem Auflistungsinitialisierer initialisieren.  
  
## Erstellen einer Auflistung mit einem Auflistungsinitialisierer  
 Wenn Sie eine Auflistung mit einem Auflistungsinitialisierer erstellen, wird jeder im Auflistungsinitialisierer angegebene Wert an die entsprechende `Add`\-Methode der Auflistung übergeben.  Wenn Sie z. B. eine <xref:System.Collections.Generic.List%601> mit einem Auflistungsinitialisierer erstellen, wird jeder Zeichenfolgenwert im Auflistungsinitialisierer an die <xref:System.Collections.Generic.List%601.Add%2A>\-Methode übergeben.  Wenn Sie eine Auflistung mit einem Auflistungsinitialisierer erstellen möchten, muss der angegebene Typ ein gültiger Auflistungstyp sein.  Zu den Beispielen für gültige Auflistungstypen gehören Klassen, die die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle implementieren oder die <xref:System.Collections.CollectionBase>\-Klasse erben.  Der angegebene Typ muss außerdem eine `Add`\-Methode verfügbar machen, die die folgenden Kriterien erfüllt.  
  
-   Die `Add`\-Methode muss in dem Bereich verfügbar sein, in dem der Auflistungsinitialisierer aufgerufen wird.  Wenn Sie den Auflistungsinitialisierer in einem Szenario verwenden, in dem auf nicht öffentliche Methoden der Auflistung zugegriffen werden kann, muss die `Add`\-Methode nicht öffentlich sein.  
  
-   Die `Add`\-Methode muss ein Instanzmember oder `Shared`\-Member der Auflistungsklasse oder eine Erweiterungsmethode sein.  
  
-   Es muss eine `Add`\-Methode vorhanden sein, die auf Grundlage von Überladungsauflösungsregeln den Typen zugeordnet werden kann, die im Auflistungsinitialisierer angegeben werden.  
  
 Im folgenden Codebeispiel wird gezeigt, wie eine `List(Of Customer)`\-Auflistung mit einem Auflistungsinitialisierer erstellt wird.  Bei Ausführung des Codes wird jedes `Customer`\-Objekt an die `Add(Customer)`\-Methode der generischen Liste übergeben.  
  
 [!code-vb[VbVbalrCollectionInitializers#9](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_4.vb)]  
  
 Im folgenden Codebeispiel wird entsprechender Code gezeigt, in dem kein Auflistungsinitialisierer verwendet wird.  
  
 [!code-vb[VbVbalrCollectionInitializers#10](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_5.vb)]  
  
 Wenn die Auflistung über eine `Add`\-Methode mit Parametern verfügt, die dem Konstruktor für das `Customer`\-Objekt entsprechen, können Sie Parameterwerte für die `Add`\-Methode innerhalb der Auflistungsinitialisierer schachteln, wie im nächsten Abschnitt erläutert.  Enthält die Auflistung keine derartige `Add`\-Methode, können Sie diese als Erweiterungsmethode erstellen.  Ein Beispiel für das Erstellen einer `Add`\-Methode als Erweiterungsmethode für eine Auflistung finden Sie unter [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md).  Ein Beispiel für das Erstellen einer benutzerdefinierten Auflistung, die mit einem Auflistungsinitialisierer verwendet werden kann, finden Sie unter [How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md).  
  
## Schachteln von Auflistungsinitialisierern  
 Sie können Werte innerhalb eines Auflistungsinitialisierers schachteln, um eine bestimmte Überladung einer `Add`\-Methode für die Auflistung, die erstellt wird, zu identifizieren.  Die an die `Add`\-Methode übergebenen Werte müssen durch Trennzeichen getrennt und in geschweifte Klammern \(`{}`\) eingeschlossen sein, ebenso wie in einem Arrayliteral oder einem Auflistungsinitialisierer.  
  
 Wenn Sie eine Auflistung mit geschachtelten Werten erstellen, wird jedes Element der geschachtelten Werteliste als Argument an die `Add`\-Methode übergeben, die den Elementtypen entspricht.  Im folgenden Codebeispiel wird z. B. ein <xref:System.Collections.Generic.Dictionary%602> mit Schlüsseln des Typs `Integer` und Werten des Typs `String` erstellt.  Jede der geschachtelten Wertelisten wird der <xref:System.Collections.Generic.Dictionary%602.Add%2A>\-Methode für das `Dictionary` zugeordnet.  
  
 [!code-vb[VbVbalrCollectionInitializers#5](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_6.vb)]  
  
 Das vorangegangene Codebeispiel entspricht folgendem Code.  
  
 [!code-vb[VbVbalrCollectionInitializers#6](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_7.vb)]  
  
 Nur geschachtelte Wertelisten der ersten Schachtelungsebene werden an die `Add`\-Methode für den Auflistungstyp gesendet.  Tiefere Schachtelungsebenen werden wie Arrayliterale behandelt, und die geschachtelten Wertelisten werden nicht der `Add`\-Methode einer Auflistung zugeordnet.  
  
## Verwandte Themen  
  
|||  
|-|-|  
|Titel|Beschreibung|  
|[How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Es wird gezeigt, wie eine Erweiterungsmethode erstellt, die `Add` aufgerufen wird, das verwendet werden kann, um eine Auflistung mit Werten aus einem Auflistungsinitialisierers aufzufüllen.|  
|[How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Zeigt, wie Verwendung eines Auflistungsinitialisierers durch Einschließen einer `Add`\-Methode in einer Auflistungsklasse ermöglicht, die `IEnumerable`implementiert.|  
  
## Siehe auch  
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Auto\-Implemented Properties](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)