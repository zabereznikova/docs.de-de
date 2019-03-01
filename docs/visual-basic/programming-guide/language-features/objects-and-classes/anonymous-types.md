---
title: Anonyme Typen (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 5ff3b12e85b9ab7fb8341bb8665a057165e78816
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968017"
---
# <a name="anonymous-types-visual-basic"></a>Anonyme Typen (Visual Basic)
Visual Basic unterstützt anonyme Typen, die Ihnen ermöglichen, Objekte zu erstellen, ohne eine Klassendefinition für den Datentyp zu schreiben. Stattdessen erzeugt der Compiler eine Klasse. Die Klasse hat keinen verwendbaren Namen, erbt direkt von <xref:System.Object>, und enthält die Eigenschaften, die Sie in der Deklaration des Objekts angeben. Da der Name des Datentyps nicht angegeben ist, wird bezeichnet als ein *anonymen Typs*.  
  
 Im folgende Beispiel Variable deklariert und erstellt `product` als eine Instanz eines anonymen Typs, das zwei Eigenschaften `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Ein *Abfrageausdruck* anonyme Typen zum Kombinieren von Spalten der Daten von einer Abfrage verwendet. Den Typ des Ergebnisses kann nicht im Voraus definiert werden, da Sie die Spalten nicht vorhersehen können, die eine bestimmte Abfrage auswählen kann. Anonyme Typen können Sie eine Abfrage schreiben, die eine beliebige Anzahl von Spalten in einer beliebigen Reihenfolge auswählt. Der Compiler erstellt einen Datentyp, der die angegebenen Eigenschaften und der angegebenen Reihenfolge entspricht.  
  
 In den folgenden Beispielen `products` ist eine Liste der Product-Objekten, von denen jede verfügt über zahlreiche Eigenschaften. Variable `namePriceQuery` enthält die Definition einer Abfrage, die bei der Ausführung, gibt eine Auflistung von Instanzen eines anonymen Typs zurück, das zwei Eigenschaften `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 Variable `nameQuantityQuery` enthält die Definition einer Abfrage, die bei der Ausführung, gibt eine Auflistung von Instanzen eines anonymen Typs zurück, das zwei Eigenschaften `Name` und `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 Weitere Informationen zu den Code, der vom Compiler für einen anonymen Typ erstellt wird, finden Sie unter [anonymen Typdefinition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  Der Name des anonymen Typs ist Compiler generiert und kann von Kompilierungen variieren. Ihr Code sollte nicht verwenden oder basieren auf den Namen eines anonymen Typs, da der Name ändern kann, wenn ein Projekt erneut kompiliert wird.  
  
## <a name="declaring-an-anonymous-type"></a>Deklaration eines anonymen Typs  
 Die Deklaration einer Instanz eines anonymen Typs mithilfe eine Initialisiererliste, an die Eigenschaften des Typs. Sie können nur Eigenschaften angeben, wenn Sie eines anonymen Typs, die keine andere Klassenelemente wie Methoden oder Ereignisse deklarieren. Im folgenden Beispiel `product1` ist eine Instanz eines anonymen Typs, die über zwei Eigenschaften verfügt: `Name` und `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 Wenn Sie Eigenschaften als Eigenschaften festlegen, können sie Sie zwei Instanzen von anonymen Typen auf Gleichheit verglichen werden soll. Allerdings können die Werte der Eigenschaften geändert werden. Finden Sie im Abschnitt "Eigenschaften" weiter unten in diesem Thema enthält weitere Informationen.  
  
 Beachten Sie, dass eine Instanz eines anonymen Typs deklarieren z. B. eine Instanz eines benannten Typs mithilfe eines Objektinitialisierers deklarieren:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 Weitere Informationen zu anderen Möglichkeiten zum anonymen Typeigenschaften angeben, finden Sie unter [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Wichtige Eigenschaften unterscheiden sich einige grundlegende Arten von nicht schlüsselbezogene Eigenschaften:  
  
-   Nur die Werte der Haupteigenschaften werden verglichen, um festzustellen, ob die beiden Instanzen gleich sind.  
  
-   Die Werte der Eigenschaften sind schreibgeschützt und können nicht geändert werden.  
  
-   Eigenschaftenwerte sind nur im vom Compiler generierter Code Hashalgorithmus für einen anonymen Typ enthalten.  
  
### <a name="equality"></a>Gleichheit  
 Instanzen von anonymen Typen können nur dann, wenn sie Instanzen desselben anonymen Typs sind gleich sein. Der Compiler behandelt zwei Instanzen als Instanzen des gleichen Typs, wenn sie die folgenden Bedingungen erfüllen:  
  
-   Sie werden in der gleichen Assembly deklariert.  
  
-   Ihre Eigenschaften haben die gleichen Namen, denselben abgeleiteten Typ verwenden, und in der gleichen Reihenfolge deklariert werden. Beim Vergleichen wird nicht beachtet werden.  
  
-   Die gleichen Eigenschaften in den einzelnen werden als Schlüsseleigenschaften gekennzeichnet.  
  
-   Mindestens eine Eigenschaft in jeder Deklaration ist eine Schlüsseleigenschaft.  
  
 Eine Instanz eines anonymen Typs, die keine Schlüsseleigenschaften entspricht nur sich selbst zur Verfügung.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 Zwei Instanzen desselben anonymen Typs sind gleich, wenn die Werte der Eigenschaften, die ihren Schlüssel gleich sind. Die folgenden Beispiele veranschaulichen, wie auf Gleichheit getestet wird.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>Schreibgeschützte Werte  
 Die Werte der Eigenschaften können nicht geändert werden. Z. B. in `prod8` im vorherigen Beispiel die `Name` und `Price` Felder sind `read-only`, aber `OnHand` kann geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Anonyme Typen in Abfrageausdrücken  
 Abfrageausdrücke muss nicht immer die Erstellung von anonymen Typen. Wenn möglich, verwenden sie einen vorhandenen Typ zum Speichern der Spaltendaten an. Dies tritt auf, wenn die Abfrage entweder ganze Datensätze aus der Datenquelle oder nur ein Feld aus jedem Datensatz zurückgibt. In den folgenden Codebeispielen `customers` ist eine Auflistung von Objekten von einem `Customer` Klasse. Die Klasse verfügt über zahlreiche Eigenschaften, und Sie können eine oder mehrere von ihnen in das Abfrageergebnis in einer beliebigen Reihenfolge einschließen. In den ersten beiden Beispielen sind keine anonymen Typen erforderlich, da die Abfragen Elemente der benannten Typen auswählen:  
  
-   `custs1` enthält eine Auflistung von Zeichenfolgen, da `cust.Name` ist eine Zeichenfolge.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
-   `custs2` enthält eine Auflistung von `Customer` Objekte um, da jedes Element der `customers` ist eine `Customer` Objekt und das ganze Element von der Abfrage ausgewählt ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 Entsprechende benannte Typen sind jedoch nicht immer verfügbar. Sie möchten den Kundennamen und Adressen für einen bestimmten Zweck, Kunden-ID-Nummern und Speicherorte für einen anderen und Kundennamen, Adressen und Order-Verlaufseinträge für eine dritte auswählen. Anonyme Typen können Sie eine beliebige Kombination von Eigenschaften in beliebiger Reihenfolge auswählen, ohne dass die Deklaration eines neuen benannten Typs, um das Ergebnis aufzunehmen. Stattdessen erstellt der Compiler einen anonymen Typ für jede Zusammenstellung von Eigenschaften. Die folgende Abfrage wählt nur die den Namen und Kunden-ID-Nummer aus jedem `Customer` im-Objekt `customers`. Aus diesem Grund erstellt der Compiler einen anonymen Typ, der nur diese zwei Eigenschaften enthält.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 Sowohl die Namen und die Datentypen der Eigenschaften im anonymen Typ stammen aus den Argumenten um `Select`, `cust.Name` und `cust.ID`. Die Eigenschaften in einem anonymen Typ, der von einer Abfrage erstellt wird, sind immer Schlüsseleigenschaften. Wenn `custs3` ausgeführt wird, in der folgenden `For Each` Schleife, die das Ergebnis ist eine Auflistung von Instanzen eines anonymen Typs mit zwei wichtige Eigenschaften, `Name` und `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 Die Elemente in der Auflistung, dargestellt durch `custs3` sind stark typisiert, und Sie können IntelliSense verwenden, zum Navigieren durch die verfügbaren Eigenschaften und ihre Typen zu überprüfen.  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Entscheiden, ob anonymer Typen  
 Bevor Sie ein Objekt als eine Instanz einer anonymen Klasse erstellen, erwägen Sie, ob dies die beste Option ist. Wenn Sie zum Erstellen eines temporären Objekts verknüpfte Daten enthalten, und Sie müssen sich nicht für andere Felder und Methoden, die eine vollständige Klasse enthalten kann, ist ein anonymer Typ eine gute Lösung. Anonyme Typen sind ebenfalls praktisch, wenn Sie eine andere Auswahl von Eigenschaften für jede Deklaration möchten oder wenn Sie die Reihenfolge der Eigenschaften ändern möchten. Jedoch, wenn das Projekt mehrere Objekte, die die gleichen Eigenschaften in einer festen Reihenfolge aufweisen enthält, können Sie sie leichter Deklarieren eines Klassenkonstruktors eines benannten Typs mit. Z. B. mit einem geeigneten Konstruktor, es ist einfacher, mehrere Instanzen von deklarieren eine `Product` Klasse statt mehrere Instanzen eines anonymen Typs deklarieren.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 Ein weiterer Vorteil von benannten Typen ist, dass der Compiler eine versehentliche falsche Schreibweise eines Eigenschaftennamens abfangen kann. In den vorherigen Beispielen `firstProd2`, `secondProd2`, und `thirdProd2` Instanzen desselben anonymen Typs sein sollen. Allerdings deklarieren, wenn Sie unbeabsichtigt `thirdProd2` in eine der folgenden Möglichkeiten, der Typ wäre sich `firstProd2` und `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 Noch wichtiger: Es gibt Einschränkungen bei der Verwendung von anonymen Typen, die für Instanzen von benannten Typen nicht gelten. `firstProd2`, `secondProd2`, und `thirdProd2` Instanzen desselben anonymen Typs sind. Allerdings wird der Name für den freigegebenen anonymen Typ ist nicht verfügbar und kann nicht verwendet werden, wo ein Typname erwartet wird, in Ihrem Code. Z. B. kann kein anonymer Typ verwendet werden, zum Definieren einer Methodensignatur, um einen anderen Variablen Felds oder in der Deklaration Typen deklarieren. Daher sind anonyme Typen nicht geeignet, wenn Sie die Freigabe von Informationen über Methoden verfügen.  
  
## <a name="an-anonymous-type-definition"></a>Definition eines anonymen Typs  
 Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften enthält.  
  
 Wenn der anonyme Typ mindestens eine Schlüsseleigenschaft enthält, überschreibt die Definition von geerbte drei Member <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>. Der Code erzeugt, für das Testen auf Gleichheit und bestimmen, dass der Hashcode-Wert nur die wichtigsten Eigenschaften betrachtet. Wenn der anonyme Typ nur keine Schlüsseleigenschaften enthält <xref:System.Object.ToString%2A> überschrieben wird. Explizit benannte Eigenschaften eines anonymen Typs können nicht in Konflikt mit diesen generierten Methoden stehen. D. h. Sie können keine `.Equals`, `.GetHashCode`, oder `.ToString` um eine Eigenschaft zu nennen.  
  
 Definitionen von anonymen Typen, die mindestens eine Schlüsseleigenschaft auch implementieren die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle, in denen `T` ist der Typ des anonymen Typs.  
  
 Weitere Informationen zu den Code, der vom Compiler und die Funktionalität der überschriebenen Methoden erstellt, finden Sie unter [anonymen Typdefinition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Siehe auch
- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Definition von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
