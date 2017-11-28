---
title: Anonyme Typen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 530e21e1595f9bbc3436280418287413e2a48111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-types-visual-basic"></a>Anonyme Typen (Visual Basic)
Visual Basic unterstützt anonyme Typen, die Ihnen ermöglichen, Objekte zu erstellen, ohne eine Klassendefinition für den Datentyp zu schreiben. Stattdessen erzeugt der Compiler eine Klasse. Die Klasse hat keinen verwendbaren Namen, erbt direkt von <xref:System.Object>, und enthält die Eigenschaften, die Sie in der Deklaration des Objekts angeben. Da der Name des Datentyps nicht angegeben ist, wird bezeichnet als ein *anonymen Typ*.  
  
 Im folgende Beispiel Variable deklariert und erstellt `product` als eine Instanz eines anonymen Typs, das zwei Eigenschaften `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 Ein *-Abfrageausdruck* anonyme Typen verwendet, um Spalten mit Daten ausgewählt, die von einer Abfrage zu kombinieren. Den Typ des Ergebnisses kann nicht im Voraus definiert werden, da die Spalten jedoch nicht vorhersehbar ist, die eine bestimmte Abfrage auswählen kann. Anonyme Typen können Sie eine Abfrage schreiben, die eine beliebige Anzahl von Spalten, in beliebiger Reihenfolge auswählt. Der Compiler erstellt einen Datentyp, der die angegebenen Eigenschaften und der angegebenen Reihenfolge entspricht.  
  
 In den folgenden Beispielen `products` ist eine Liste von Product-Objekte, von denen jedes über viele Eigenschaften verfügt. Variable `namePriceQuery` enthält die Definition einer Abfrage, die bei der Ausführung, eine Auflistung von Instanzen eines anonymen Typs zurückgibt, das zwei Eigenschaften `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 Variable `nameQuantityQuery` enthält die Definition einer Abfrage, die bei der Ausführung, eine Auflistung von Instanzen eines anonymen Typs zurückgibt, das zwei Eigenschaften `Name` und `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 Weitere Informationen zu den Code, der vom Compiler für einen anonymen Typ erstellt wird, finden Sie unter [anonymen Typdefinition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  Der Name des anonymen Typs ist Compiler generiert und kann von Kompilierungen variieren. Der Code sollte nicht verwenden oder basieren auf den Namen eines anonymen Typs, da Sie der Namen ändern kann, wenn ein Projekt erneut kompiliert wird.  
  
## <a name="declaring-an-anonymous-type"></a>Deklaration eines anonymen Typs  
 Die Deklaration einer Instanz eines anonymen Typs wird mit einer Initialisiererliste die Eigenschaften des Typs angegeben. Sie können nur Eigenschaften angeben, wenn Sie einen anonymen Typ, der keine anderen Klassenelemente wie Methoden oder Ereignisse deklarieren. Im folgenden Beispiel `product1` ist eine Instanz eines anonymen Typs, die über zwei Eigenschaften verfügt: `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 Wenn Sie Eigenschaften als Schlüsseleigenschaften festlegen, können sie Sie zwei anonymen Typs-Instanzen auf Gleichheit verglichen werden soll. Allerdings können die Werte der Eigenschaften geändert werden. Siehe Abschnitt Schlüsseleigenschaften weiter unten in diesem Thema für Weitere Informationen.  
  
 Beachten Sie, dass eine Instanz eines anonymen Typs deklarieren z. B. eine Instanz eines benannten Typs mithilfe eines Objektinitialisierers deklarieren:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 Weitere Informationen zu anderen Möglichkeiten zum Angeben von Eigenschaften des anonymen Typs, finden Sie unter [wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Wichtige Eigenschaften unterscheiden sich einige grundlegende Arten von nicht schlüsselbezogene Eigenschaften:  
  
-   Um zu bestimmen, ob zwei Instanzen gleich sind, werden nur die Werte von Schlüsseleigenschaften verglichen.  
  
-   Die Werte der Eigenschaften sind schreibgeschützt und können nicht geändert werden.  
  
-   Eigenschaftenwerte sind nur in der vom Compiler generierte Code Hashalgorithmus für einen anonymen Typ enthalten.  
  
### <a name="equality"></a>Gleichheit  
 Instanzen von anonymen Typen können nur dann, wenn sie Instanzen desselben anonymen Typs sind gleich sein. Der Compiler behandelt zwei Instanzen als Instanzen desselben Typs, wenn sie die folgenden Bedingungen erfüllen:  
  
-   In der gleichen Assembly deklariert werden.  
  
-   Ihre Eigenschaften haben die gleichen Namen, die gleichen hergeleiteten Typen, und in der gleichen Reihenfolge deklariert werden. Vergleichen des wird die Groß-und Kleinschreibung nicht berücksichtigt.  
  
-   Die gleichen Eigenschaften in den einzelnen sind als Schlüsseleigenschaften gekennzeichnet.  
  
-   Mindestens eine Eigenschaft in jeder Deklaration ist eine Schlüsseleigenschaft.  
  
 Eine Instanz eines anonymen Typs, die keine Schlüsseleigenschaften verfügt ist ungleich sich selbst.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 Zwei Instanzen desselben anonymen Typs sind gleich, wenn die Werte ihrer Schlüssel Eigenschaften gleich sind. Die folgenden Beispiele veranschaulichen, wie auf Gleichheit getestet wird.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### <a name="read-only-values"></a>Schreibgeschützte Werte  
 Die Werte von Schlüsseleigenschaften können nicht geändert werden. Beispielsweise ist in `prod8` im vorherigen Beispiel der `Name` und `Price` Felder sind `read-only`, aber `OnHand` kann geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Anonyme Typen von Abfrageausdrücken  
 Abfrageausdrücke müssen nicht immer die Erstellung von anonymen Typen aufweisen. Wenn möglich, verwenden sie einen vorhandenen Typ zum Speichern der Spaltendaten an. Dies tritt auf, wenn die Abfrage entweder ganze Datensätze aus der Datenquelle oder nur ein Feld aus jedem Datensatz zurückgibt. In den folgenden Codebeispielen `customers` ist eine Auflistung von Objekten von einem `Customer` Klasse. Die Klasse verfügt über zahlreiche Eigenschaften, und Sie können eine oder mehrere dieser Servertypen im Abfrageergebnis in beliebiger Reihenfolge enthalten. In den ersten beiden Beispielen werden keine anonymen Typen erforderlich, da die Abfragen Elemente von benannten Typen auswählen:  
  
-   `custs1`enthält eine Auflistung von Zeichenfolgen, da `cust.Name` ist eine Zeichenfolge.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2`enthält eine Auflistung von `Customer` Objekten, da jedes Element der `customers` ist ein `Customer` Objekt und das ganze Element von der Abfrage ausgewählt ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 Entsprechende benannte Typen sind jedoch nicht immer verfügbar. Möglicherweise möchten Kundennamen und Adressen für einen bestimmten Zweck, Kunden-ID-Nummern und Speicherorte für eine andere und Kundennamen, Adressen und Reihenfolge Verlaufseinträge für eine dritte auswählen. Anonyme Typen können Sie jede beliebige Kombination von Eigenschaften dar, in beliebiger Reihenfolge zu aktivieren, ohne zuerst deklariert einen neuen benannten Typ, um das Ergebnis aufzunehmen. Stattdessen erstellt der Compiler einen anonymen Typ für jede Zusammenstellung von Eigenschaften. Die folgende Abfrage wählt nur die Customer Name und ID-Nummer aus allen `Customer` -Objekt in `customers`. Aus diesem Grund erstellt der Compiler einen anonymen Typ, der nur diese zwei Eigenschaften enthält.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 Die Namen und die Datentypen der Eigenschaften des anonymen Typs stammen aus den Argumenten um `Select`, `cust.Name` und `cust.ID`. Die Eigenschaften in einem anonymen Typ, der von einer Abfrage erstellt wird, sind immer Schlüsseleigenschaften. Wenn `custs3` ausgeführt wird, in der folgenden `For Each` Schleife, das Ergebnis ist eine Auflistung von Instanzen eines anonymen Typs mit zwei Schlüsseleigenschaften `Name` und `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 Die Elemente in der Auflistung dargestellte `custs3` sind stark typisiert, und Sie können IntelliSense verwenden, zum Navigieren durch die verfügbaren Eigenschaften und ihre Typen zu überprüfen.  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Die Entscheidung, ob anonyme Typen verwenden.  
 Bevor Sie ein Objekt als eine Instanz einer anonymen Klasse erstellen, erwägen Sie, ob dies die beste Option ist. Wenn verknüpfte Daten enthalten ein temporäres Objekt erstellt werden soll, und Sie benötigen keine weiteren Felder und Methoden, die möglicherweise eine vollständige Klasse enthalten, ist ein anonymer Typ eine gute Lösung. Anonyme Typen stellen auch praktisch, wenn Sie eine andere Auswahl von Eigenschaften für jede Deklaration möchten oder wenn Sie die Reihenfolge der Eigenschaften ändern möchten. Jedoch, wenn Ihr Projekt mehrere Objekte, die die gleichen Eigenschaften in einer festen Reihenfolge aufweisen enthält, können Sie sie leichter deklarieren mithilfe eines benannten Typs mit einem Klassenkonstruktor. Z. B. mit einem geeigneten Konstruktor, es ist einfacher, mehrere Instanzen von Deklarieren einer `Product` Klasse als es ist, mehrere Instanzen eines anonymen Typs deklarieren.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 Ein weiterer Vorteil von benannten Typen ist, dass der Compiler eine versehentliche Tippfehler neben einem Eigenschaftennamen erfasst werden kann. In den vorherigen Beispielen `firstProd2`, `secondProd2`, und `thirdProd2` sollten Instanzen desselben anonymen Typs verwendet werden. Wenn Sie unbeabsichtigt jedoch deklarieren `thirdProd2` in einem der folgenden Methoden, dessen Typ wären unterschiedlich aus, die von `firstProd2` und `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 Es gibt vor allem Einschränkungen bei der Verwendung von anonymen Typen, die auf Instanzen von benannten Typen nicht anwendbar sind. `firstProd2`, `secondProd2`, und `thirdProd2` Instanzen desselben anonymen Typs sind. Allerdings wird der Name für den freigegebenen anonymen Typ ist nicht verfügbar und kann nicht verwendet werden, wo ein Typname in Ihrem Code erwartet wird. Z. B. kann kein anonymes Typs verwendet werden, definieren Sie die Signatur einer Methode um eine andere Variable Felds oder in der Typdeklaration einer deklarieren. Daher sind anonyme Typen nicht geeignet, wenn Sie die Freigabe von Informationen über Methoden verfügen.  
  
## <a name="an-anonymous-type-definition"></a>Eine Definition von anonymen Typen  
 Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften enthält.  
  
 Wenn der anonyme Typ mindestens eine Schlüsseleigenschaft enthält, überschreibt die Definition drei von geerbte Member <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>. Der Code erzeugt zum Testen der Übereinstimmung und ermittelt, auf der Hashcodewert nur die Schlüsseleigenschaften betrachtet. Wenn des anonymen Typs nur keine Schlüsseleigenschaften enthält <xref:System.Object.ToString%2A> überschrieben wird. Explizit benannte Eigenschaften eines anonymen Typs können nicht mit diesen generierten Methoden in Konflikt stehen. D. h., Sie können keine `.Equals`, `.GetHashCode`, oder `.ToString` um eine Eigenschaft zu benennen.  
  
 Anonyme Typdefinitionen, bei denen mindestens einer Schlüsseleigenschaft auch implementieren die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle, in denen `T` ist der Typ des anonymen Typs.  
  
 Weitere Informationen zu den Code durch den Compiler und die Funktionalität der überschriebenen Methoden erstellt wird, finden Sie unter [anonymen Typdefinition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Definition von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
