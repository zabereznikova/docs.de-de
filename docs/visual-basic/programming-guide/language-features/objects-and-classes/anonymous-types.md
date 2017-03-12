---
title: "Anonymous Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AnonymousType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], about anonymous types"
  - "anonymous types [Visual Basic]"
  - "types [Visual Basic], anonymous"
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: 46
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 46
---
# Anonymous Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Visual Basic untersützt anonyme Typen, mit denen Objekte erzeugt werden können, ohne eine Klassendefinition für den Datentyp zu schreiben.  Stattdessen erzeugt der Compiler eine Klasse.  Die Klasse hat keinen verwendbaren Namen, erbt direkt von <xref:System.Object> und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.  Da der Name des Datentyps nicht angegeben wird, wird er als *anonymer Typ* bezeichnet.  
  
 Im folgenden Beispiel wird die Variable `product` als Instanz eines anonymen Typs mit den beiden Eigenschaften `Name` und `Price` deklariert und erzeugt.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_1.vb)]  
  
 Ein *Abfrageausdruck* verwendet anonyme Typen, um Spalten mit Daten, die durch eine Abfrage ausgewählt wurden, zusammenzustellen.  Der Typ des Ergebnisses kann nicht im Voraus definiert werden, da die Spalten, die von einer bestimmten Abfrage ausgewählt werden, nicht vorausgesehen werden können.  Anonyme Typen ermöglichen das Schreiben einer Abfrage, die eine beliebige Anzahl von Spalten in beliebiger Reihenfolge auswählt.  Der Compiler erstellt einen Datentyp, der zu den angegebenen Eigenschaften und der angegebenen Reihenfolge passt.  
  
 In den folgenden Beispielen ist `products` eine Liste von Product\-Objekten, von denen jedes eine Reihe von Eigenschaften hat.  Die Variable `namePriceQuery` enthält die Definition einer Abfrage, die bei ihrer Ausführung eine Auflistung von Instanzen eines anonymen Typs zurückgibt, der die beiden Eigenschaften `Name` und `Price` hat.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_2.vb)]  
  
 Die Variable `nameQuantityQuery` enthält die Definition einer Abfrage, die bei ihrer Ausführung eine Auflistung von Instanzen eines anonymen Typs zurückgibt, der die beiden Eigenschaften `Name` und `OnHand` hat.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_3.vb)]  
  
 Weitere Informationen über den Code, der vom Compiler für einen anonymen Typ erstellt wird, finden Sie unter [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  Der Name des anonymen Typs wird vom Compiler erzeugt und kann von Kompilierung zu Kompilierung variieren.  Sie sollten im Code den Namen eines anonymen Typs nicht verwenden oder sich darauf verlassen, da er sich bei einer Neukompilierung des Projekts ändern könnte.  
  
## Deklarieren eines anonymen Typs  
 Die Deklaration einer Instanz eines anonymen Typs verwendet eine Initialisiererliste zur Angabe der Eigenschaften des Typs.  Bei der Deklaration eines anonymen Typs können nur Eigenschaften angegeben werden, keine anderen Klassenelemente wie Methoden oder Ereignisse.  Im folgenden Beispiel ist `product1` eine Instanz eines anonymen Typs mit zwei Eigenschaften: `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_4.vb)]  
  
 Wenn Sie Eigenschaften als Haupteigenschaften festlegen, können Sie sie verwenden, um zwei Instanzen eines anonymen Typs auf Gleichheit zu testen.  Die Werte von Haupteigenschaften können jedoch nicht geändert werden.  Weitere Informationen finden Sie weiter unten in diesem Thema im Abschnitt "Haupteigenschaften".  
  
 Beachten Sie, dass die Deklaration einer Instanz eines anonymen Typs der Deklaration eines benannten Typs mithilfe eines Objektinitialisierers entspricht:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_5.vb)]  
  
 Weitere Informationen über andere Möglichkeiten, Eigenschaften von anonymen Typen anzugeben, finden Sie unter [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## Haupteigenschaften  
 Haupteigenschaften unterscheiden sich von Eigenschaften, die keine Haupteigenschaften sind, in mehreren grundlegenden Punkten:  
  
-   Nur die Werte von Haupteigenschaften werden verglichen, um zu ermitteln, ob zwei Instanzen gleich sind.  
  
-   Die Werte von Haupteigenschaften sind schreibgeschützt und können nicht geändert werden.  
  
-   Nur Werte von Haupteigenschaften sind in dem vom Compiler generierten Hashcodealgorithmus für den anonymen Typ enthalten.  
  
### Gleichheit  
 Instanzen anonymer Typen können nur gleich sein, wenn sie Instanzen des gleichen anonymen Typs sind.  Der Compiler behandelt zwei Instanzen als Instanzen des gleichen Typs, wenn sie die folgenden Bedingungen erfüllen:  
  
-   Sie werden in der gleichen Assembly deklariert.  
  
-   Ihre Eigenschaften haben die gleichen Namen, die gleichen abgeleiteten Typen und werden in der gleichen Reihenfolge deklariert.  Beim Vergleichen von Namen wird die Groß\- und Kleinschreibung nicht berücksichtigt.  
  
-   In beiden sind die gleichen Eigenschaften als Haupteigenschaften gekennzeichnet.  
  
-   Mindestens eine Eigenschaft in jeder Deklaration ist eine Haupteigenschaft.  
  
 Eine Instanz eines anonymen Typs, der keine Haupteigenschaften hat, gleicht nur sich selbst.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_6.vb)]  
  
 Zwei Instanzen desselben anonymen Typs sind gleich, wenn die Werte ihrer Haupteigenschaften übereinstimmen.  In den folgenden Beispielen wird veranschaulicht, wie auf Gleichheit getestet wird.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_7.vb)]  
  
### Schreibgeschützte Werte  
 Die Werte von Haupteigenschaften können nicht geändert werden.  In `prod8` aus dem vorhergehenden Beispiel sind die Felder `Name` und `Price` `read-only`, `OnHand` kann jedoch geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_8.vb)]  
  
## Anonyme Typen aus Abfrageausdrücken  
 Abfrageausdrücke erfordern nicht immer die Erstellung anonymer Typen.  Wenn möglich wird ein vorhandener Typ für die Spaltendaten verwendet.  Dies ist der Fall, wenn die Abfrage entweder ganze Datensätze aus der Datenquelle oder nur ein Feld jedes Datensatzes zurückgibt.  In den folgenden Codebeispielen ist `customers` eine Auflistung von Objekten einer `Customer`\-Klasse.  Die Klasse hat eine Reihe von Eigenschaften, von denen eine oder mehrere in beliebiger Reihenfolge dem Abfrageergebnis hinzugefügt werden können.  In den ersten beiden Beispielen werden keine anonymen Typen benötigt, da die Abfragen Elemente von benannten Typen auswählen:  
  
-   `custs1` enthält eine Auflistung von Zeichenfolgen, da `cust.Name` eine Zeichenfolge ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_9.vb)]  
  
-   `custs2` enthält eine Auflistung von `Customer`\-Objekten, da jedes Element von `customers` ein `Customer`\-Objekt ist und das ganze Element von der Abfrage ausgewählt wird.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_10.vb)]  
  
 Passende benannte Typen sind jedoch nicht immer verfügbar.  Möglicherweise möchten Sie Kundennamen und \-adressen zu einem bestimmten Zweck, Kunden\-ID\-Nummern und Standorte zu einem anderen Zweck und Kundennamen, \-adressen und Bestellhistorien zu einem dritten Zweck auswählen.  Anonyme Typen ermöglichen die Auswahl beliebiger Kombinationen von Eigenschaften in beliebiger Reihenfolge, ohne dass die Deklaration eines benannten Typs für das Ergebnis notwendig ist.  Stattdessen erstellt der Compiler einen anonymen Typ für jede Zusammenstellung von Eigenschaften.  Die folgende Abfrage wählt nur den Namen des Kunden und die ID\-Nummer von jedem `Customer`\-Objekt in `customers` aus.  Daher erstellt der Compiler einen anonymen Typ, der nur diese beiden Eigenschaften enthält.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_11.vb)]  
  
 Sowohl die Namen als auch die Datentypen der Eigenschaften des anonymen Typs werden von den Argumenten von `Select` übernommen: `cust.Name` und `cust.ID`.  Die Eigenschaften in einem anonymen Typ, der von einer Abfrage erstellt wird, sind immer Haupteigenschaften.  Wenn `custs3` in der folgenden `For Each`\-Schleife ausgeführt wird, ist das Ergebnis eine Auflistung von Instanzen eines anonymen Typs mit den beiden Haupteigenschaften `Name` und `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_12.vb)]  
  
 Die von `custs3` dargestellten Elemente in der Auflistung sind stark typisiert. Sie können IntelliSense verwenden, um durch die verfügbaren Eigenschaften zu navigieren und deren Typen zu überprüfen.  
  
 Weitere Informationen hierzu finden Sie unter [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## Entscheiden, ob anonyme Typen verwendet werden sollen  
 Bevor Sie ein Objekt als Instanz einer anonymen Klasse erzeugen, überlegen Sie sich, ob dies die beste Wahl ist.  Wenn Sie beispielsweise ein temporäres Objekt erstellen möchten, das verknüpfte Daten enthalten soll, und Sie keine weiteren Felder und Methoden benötigen, die in einer vollständigen Klasse normalerweise enthalten sind, ist ein anonymer Typ eine angemessene Lösung.  Anonyme Typen sind auch nützlich, wenn jede Deklaration eine andere Auswahl von Eigenschaften enthalten soll oder die Reihenfolge der Eigenschaften geändert werden soll.  Wenn Ihr Projekt jedoch mehrere Objekte mit den gleichen Eigenschaften in festgelegter Reihenfolge enthält, können sie unter Verwendung eines benannten Typs mit einem Klassenkonstruktor einfacher deklariert werden.  Beispielsweise ist es einfacher, mehrere Instanzen einer `Product`\-Klasse mit einem geeigneten Konstruktor zu deklarieren als mehrere Instanzen eines anonymen Typs.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_13.vb)]  
  
 Ein weiterer Vorteil benannter Typen besteht darin, dass der Compiler versehentliche Schreibfehler bei einem Eigenschaftennamen erkennen kann.  Im vorhergehenden Beispiel sollen `firstProd2`, `secondProd2` und `thirdProd2` Instanzen desselben anonymen Typs sein.  Wenn Sie jedoch versehentlich `thirdProd2` auf eine der folgenden Weisen deklariert hätten, würde sich sein Typ von dem von `firstProd2` und `secondProd2` unterscheiden.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-types_14.vb)]  
  
 Bedeutender ist jedoch die Tatsache, dass es Beschränkungen bei der Verwendung von anonymen Typen gibt, die für Instanzen von benannten Typen nicht gelten.  `firstProd2`, `secondProd2` und `thirdProd2` sind Instanzen desselben anonymen Typs.  Der Name des gemeinsamen anonymen Typs ist jedoch nicht verfügbar und kann im Code an den Stellen, an denen ein Typname erwartet wird, nicht verwendet werden.  Beispielsweise kann ein anonymer Typ nicht zur Definition einer Methodensignatur oder zur Deklaration einer anderen Variablen, eines anderen Felds oder eines Typs verwendet werden.  Folglich sind anonyme Typen nicht geeignet, wenn Informationen von mehreren Methoden gemeinsam verwendet werden müssen.  
  
## Definition eines anonymen Typs  
 Als Reaktion auf die Deklaration einer Instanz eines anonymen Typs erzeugt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften enthält.  
  
 Wenn der anonyme Typ mindestens eine Haupteigenschaft enthält, überschreibt die Definition drei von <xref:System.Object> geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A>.  Der Code, der für das Testen auf Gleichheit und für die Ermittlung des Hashcodewerts erzeugt wird, berücksichtigt nur die Haupteigenschaften.  Wenn der anonyme Typ keine Haupteigenschaften enthält, wird nur <xref:System.Object.ToString%2A> überschrieben.  Explizit benannte Eigenschaften eines anonymen Typs dürfen keine Konflikte mit diesen erzeugten Methoden hervorrufen.  Das heißt, Sie können `.Equals`, `.GetHashCode` oder `.ToString` nicht verwenden, um eine Eigenschaft zu benennen.  
  
 Anonyme Typdefinitionen, die mindestens eine Haupteigenschaft enthalten, implementieren auch die <xref:System.IEquatable%601?displayProperty=fullName>\-Schnittstelle, wobei `T` der Typ des anonymen Typs ist.  
  
 Weitere Informationen über den compilergenerierten Code und die Funktionalität der überschriebenen Methoden finden Sie unter [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## Siehe auch  
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)