---
title: Anonyme Typen
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 5ab3cf8c3c02ff35890f71ad6c7f314b51b87133
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075238"
---
# <a name="anonymous-types-visual-basic"></a>Anonyme Typen (Visual Basic)

Visual Basic unterstützt anonyme Typen, die es Ihnen ermöglichen, Objekte zu erstellen, ohne eine Klassendefinition für den Datentyp zu schreiben. Stattdessen erzeugt der Compiler eine Klasse. Die Klasse hat keinen verwendbaren Namen, erbt direkt von <xref:System.Object> und enthält die Eigenschaften, die Sie beim Deklarieren des Objekts angeben. Da der Name des Datentyps nicht angegeben wird, wird er als *anonymer Typ*bezeichnet.  
  
 Im folgenden Beispiel wird eine-Variable deklariert und `product` als Instanz eines anonymen Typs mit zwei Eigenschaften, und, erstellt `Name` `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Ein *Abfrage Ausdruck* verwendet anonyme Typen, um von einer Abfrage ausgewählte Spalten von Daten zu kombinieren. Sie können den Ergebnistyp nicht im Voraus definieren, da Sie die Spalten, die von einer bestimmten Abfrage ausgewählt werden können, nicht vorhersagen können. Mit anonymen Typen können Sie eine Abfrage schreiben, die eine beliebige Anzahl von Spalten in beliebiger Reihenfolge auswählt. Der Compiler erstellt einen Datentyp, der den angegebenen Eigenschaften und der angegebenen Reihenfolge entspricht.  
  
 In den folgenden Beispielen `products` ist eine Liste von Produkt Objekten, von denen jede über viele Eigenschaften verfügt. `namePriceQuery`Die Variable enthält die Definition einer Abfrage, die bei der Ausführung eine Auflistung von Instanzen eines anonymen Typs mit zwei Eigenschaften, und, zurückgibt `Name` `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 `nameQuantityQuery`Die Variable enthält die Definition einer Abfrage, die bei der Ausführung eine Auflistung von Instanzen eines anonymen Typs mit zwei Eigenschaften, und, zurückgibt `Name` `OnHand` .  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 Weitere Informationen zu dem Code, der vom Compiler für einen anonymen Typ erstellt wurde, finden Sie unter [Anonyme Typdefinition](anonymous-type-definition.md).  
  
> [!CAUTION]
> Der Name des anonymen Typs ist vom Compiler generiert und kann von der Kompilierung bis zur Kompilierung abweichen. Der Code sollte nicht den Namen eines anonymen Typs verwenden oder darauf basieren, da sich der Name bei der erneuten Kompilierung eines Projekts ändern kann.  
  
## <a name="declaring-an-anonymous-type"></a>Deklarieren eines anonymen Typs  

 Die Deklaration einer Instanz eines anonymen Typs verwendet eine Initialisiererliste, um die Eigenschaften des Typs anzugeben. Sie können nur Eigenschaften angeben, wenn Sie einen anonymen Typ deklarieren, nicht jedoch andere Klassen Elemente, wie z. b. Methoden oder Ereignisse. Im folgenden Beispiel `product1` ist eine Instanz eines anonymen Typs mit zwei Eigenschaften: `Name` und `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 Wenn Sie Eigenschaften als Schlüsseleigenschaften festlegen, können Sie diese verwenden, um zwei anonyme Typinstanzen auf Gleichheit zu vergleichen. Die Werte der Schlüsseleigenschaften können jedoch nicht geändert werden. Weitere Informationen finden Sie im Abschnitt Schlüsseleigenschaften weiter unten in diesem Thema.  
  
 Beachten Sie, dass das Deklarieren einer Instanz eines anonymen Typs dem Deklarieren einer Instanz eines benannten Typs mithilfe eines Objektinitialisierers ähnelt:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 Weitere Informationen zu anderen Methoden zum angeben anonymer Typeigenschaften finden Sie unter Gewusst [wie: Ableiten von Eigenschaften Namen und Typen in Deklarationen anonymer Typen](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  

 Schlüsseleigenschaften unterscheiden sich auf verschiedene Arten von nicht Schlüsseleigenschaften:  
  
- Es werden nur die Werte der Schlüsseleigenschaften verglichen, um zu bestimmen, ob zwei Instanzen gleich sind.  
  
- Die Werte der Schlüsseleigenschaften sind schreibgeschützt und können nicht geändert werden.  
  
- Nur Schlüssel Eigenschaftswerte sind im vom Compiler generierten Hash Code Algorithmus für einen anonymen Typ enthalten.  
  
### <a name="equality"></a>Gleichheit  

 Instanzen anonymer Typen können nur gleich sein, wenn es sich um Instanzen desselben anonymen Typs handelt. Der Compiler behandelt zwei Instanzen als Instanzen desselben Typs, wenn Sie die folgenden Bedingungen erfüllen:  
  
- Sie werden in derselben Assembly deklariert.  
  
- Ihre Eigenschaften haben die gleichen Namen, die gleichen abhergenten Typen und werden in derselben Reihenfolge deklariert. Bei namens vergleichen wird die Groß-/Kleinschreibung nicht beachtet  
  
- Die gleichen Eigenschaften sind jeweils als Schlüsseleigenschaften gekennzeichnet.  
  
- Mindestens eine Eigenschaft in jeder Deklaration ist eine Schlüsseleigenschaft.  
  
 Eine Instanz eines anonymen Typs ohne Schlüsseleigenschaften ist nur mit sich selbst identisch.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 Zwei Instanzen desselben anonymen Typs sind gleich, wenn die Werte ihrer Schlüsseleigenschaften gleich sind. In den folgenden Beispielen wird veranschaulicht, wie Gleichheit getestet wird.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>Schreibgeschützte Werte  

 Die Werte der Schlüsseleigenschaften können nicht geändert werden. Beispielsweise sind in `prod8` im vorherigen Beispiel die `Name` `Price` Felder und `read-only` , aber Sie `OnHand` können geändert werden.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Anonyme Typen aus Abfrage Ausdrücken  

 Abfrage Ausdrücke erfordern nicht immer die Erstellung anonymer Typen. Wenn möglich, verwenden Sie einen vorhandenen Typ zum Speichern der Spaltendaten. Dies tritt auf, wenn die Abfrage entweder ganze Datensätze aus der Datenquelle oder nur ein Feld aus jedem Datensatz zurückgibt. In den folgenden Codebeispielen `customers` ist eine Auflistung von-Objekten einer- `Customer` Klasse. Die-Klasse verfügt über zahlreiche Eigenschaften, und Sie können eine oder mehrere davon in beliebiger Reihenfolge in das Abfrageergebnis einschließen. In den ersten beiden Beispielen sind keine anonymen Typen erforderlich, da die Abfragen Elemente benannter Typen auswählen:  
  
- `custs1` enthält eine Auflistung von Zeichen folgen, da `cust.Name` eine Zeichenfolge ist.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
- `custs2` enthält eine Auflistung von- `Customer` Objekten, da jedes Element von `customers` ein `Customer` -Objekt ist und das gesamte Element von der Abfrage ausgewählt wird.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 Geeignete benannte Typen sind jedoch nicht immer verfügbar. Möglicherweise möchten Sie Kundennamen und Adressen für einen Zweck, Kunden-ID-Nummern und Standorte für einen anderen, Kundennamen, Adressen und Bestell Verläufe für eine dritte auswählen. Mit anonymen Typen können Sie eine beliebige Kombination von Eigenschaften in beliebiger Reihenfolge auswählen, ohne zuerst einen neuen benannten Typ für das Ergebnis zu deklarieren. Stattdessen erstellt der Compiler einen anonymen Typ für jede Kompilierung von Eigenschaften. Mit der folgenden Abfrage werden nur der Name und die ID-Nummer des Kunden aus den einzelnen `Customer` Objekten in ausgewählt `customers` . Daher erstellt der Compiler einen anonymen Typ, der nur die beiden Eigenschaften enthält.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 Sowohl der Name als auch die Datentypen der Eigenschaften im anonymen Typ werden von den Argumenten zu `Select` , und entnommen `cust.Name` `cust.ID` . Die Eigenschaften in einem anonymen Typ, der von einer Abfrage erstellt wird, sind immer Schlüsseleigenschaften. Wenn `custs3` in der folgenden Schleife ausgeführt wird `For Each` , ist das Ergebnis eine Auflistung von Instanzen eines anonymen Typs mit zwei Schlüsseleigenschaften, `Name` und `ID` .  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 Die Elemente in der durch dargestellten Auflistung `custs3` sind stark typisiert, und Sie können IntelliSense verwenden, um durch die verfügbaren Eigenschaften zu navigieren und deren Typen zu überprüfen.  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Entscheiden, ob anonyme Typen verwendet werden sollen  

 Bevor Sie ein Objekt als Instanz einer anonymen Klasse erstellen, sollten Sie berücksichtigen, ob dies die beste Option ist. Wenn Sie z. b. ein temporäres Objekt erstellen möchten, das verwandte Daten enthält, und Sie keine weiteren Felder und Methoden benötigen, die eine komplette Klasse enthalten kann, ist ein anonymer Typ eine gute Lösung. Anonyme Typen sind auch dann praktisch, wenn Sie für jede Deklaration eine andere Auswahl von Eigenschaften benötigen oder wenn Sie die Reihenfolge der Eigenschaften ändern möchten. Wenn das Projekt jedoch mehrere Objekte mit denselben Eigenschaften enthält, können Sie diese in einer festgelegten Reihenfolge leichter deklarieren, indem Sie einen benannten Typ mit einem Klassenkonstruktor verwenden. Mit einem geeigneten Konstruktor ist es z. b. einfacher, mehrere Instanzen einer Klasse zu deklarieren, `Product` als mehrere Instanzen eines anonymen Typs zu deklarieren.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 Ein weiterer Vorteil von benannten Typen besteht darin, dass der Compiler ein versehentliches falsch formatiping eines Eigenschafts namens abfangen kann. In den vorherigen Beispielen sollen `firstProd2` , `secondProd2` und `thirdProd2` Instanzen desselben anonymen Typs sein. Wenn Sie jedoch versehentlich `thirdProd2` auf eine der folgenden Arten deklarieren würden, unterscheidet sich der Typ von `firstProd2` und `secondProd2` .  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 Noch wichtiger ist, dass die Verwendung anonymer Typen, die nicht für Instanzen benannter Typen gelten, eingeschränkt ist. `firstProd2`, `secondProd2` und `thirdProd2` sind Instanzen desselben anonymen Typs. Der Name des freigegebenen anonymen Typs ist jedoch nicht verfügbar und kann nicht angezeigt werden, wenn in Ihrem Code ein Typname erwartet wird. Ein anonymer Typ kann z. b. nicht verwendet werden, um eine Methoden Signatur zu definieren, eine andere Variable oder ein anderes Feld oder eine Typdeklaration zu deklarieren. Daher sind anonyme Typen nicht geeignet, wenn Sie Informationen über Methoden hinweg freigeben müssen.  
  
## <a name="an-anonymous-type-definition"></a>Eine anonyme Typdefinition  

 Als Antwort auf die Deklaration einer Instanz eines anonymen Typs erstellt der Compiler eine neue Klassendefinition, die die angegebenen Eigenschaften enthält.  
  
 Wenn der anonyme Typ mindestens eine Schlüsseleigenschaft enthält, überschreibt die Definition drei von geerbte Member <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> und <xref:System.Object.ToString%2A> . Der Code, der zum Testen der Gleichheit und zum Ermitteln des Hashcodewerts erstellt wurde, berücksichtigt nur die Schlüsseleigenschaften. Wenn der anonyme Typ keine Schlüsseleigenschaften enthält, <xref:System.Object.ToString%2A> wird nur überschrieben. Explizit benannte Eigenschaften eines anonymen Typs können nicht mit diesen generierten Methoden in Konflikt stehen. Das heißt, Sie können, oder nicht verwenden, `.Equals` `.GetHashCode` `.ToString` um eine Eigenschaft zu benennen.  
  
 Anonyme Typdefinitionen, die über mindestens eine Schlüsseleigenschaft verfügen, implementieren auch die- <xref:System.IEquatable%601?displayProperty=nameWithType> Schnittstelle, wobei `T` der Typ des anonymen Typs ist.  
  
 Weitere Informationen zu dem vom Compiler erstellten Code und zu den Funktionen der überschriebenen Methoden finden Sie unter [Anonyme Typdefinition](anonymous-type-definition.md).  
  
## <a name="see-also"></a>Siehe auch

- [Objektinitialisierer: benannte und anonyme Typen](object-initializers-named-and-anonymous-types.md)
- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Definition von anonymen Typen](anonymous-type-definition.md)
- [Schlüssel](../../../language-reference/modifiers/key.md)
