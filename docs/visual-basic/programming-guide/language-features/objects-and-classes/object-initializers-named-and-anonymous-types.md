---
title: 'Objektinitialisierer: Benannte und anonyme Typen (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 612b1dcea0f776dfd4580803e76f2785e7d28da6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Objektinitialisierer: Benannte und anonyme Typen (Visual Basic)
Objektinitialisierer können Sie Eigenschaften für ein komplexes Objekt mit einem einzelnen Ausdruck angeben. Sie können zum Erstellen von Instanzen benannter Typen und anonymer Typen verwendet werden.  
  
## <a name="declarations"></a>Deklarationen  
 Deklarationen von Instanzen der benannte und anonyme Typen können fast identisch aussehen, aber deren Auswirkungen stimmen nicht überein. Jede Kategorie verfügt über Funktionen und Einschränkungen der eigenen. Das folgende Beispiel zeigt eine einfache Möglichkeit, deklarieren und initialisieren Sie eine Instanz einer benannten Klasse `Customer`, mithilfe einer Objektinitialisiererliste enthalten. Beachten Sie, dass der Name der Klasse nach dem Schlüsselwort angegeben ist `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Ein anonymer Typ hat keinen verwendbaren Namen. Eine Instanziierung eines anonymen Typs kann nicht aus diesem Grund einen Klassennamen enthalten.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Die Anforderungen und die Ergebnisse der beiden Deklarationen sind nicht identisch. Für `namedCust`, `Customer` -Klasse, verfügt ein `Name` Eigenschaft muss bereits vorhanden sein, und die Deklaration erstellt eine Instanz dieser Klasse. Für `anonymousCust`, definiert der Compiler eine neue Klasse, die eine Eigenschaft, eine Zeichenfolge mit dem Namen `Name`, und erstellt eine neue Instanz dieser Klasse.  
  
## <a name="named-types"></a>Benannter Typen  
 Objektinitialisierer bieten eine einfache Möglichkeit, rufen Sie den Konstruktor eines Typs, und legen Sie dann die Werte einiger oder aller Eigenschaften in einer einzelnen Anweisung. Der Compiler Ruft den entsprechenden Konstruktor für die Anweisung: der Standardkonstruktor, wenn keine Argumente angegeben werden, oder einen parametrisierten Konstruktor, wenn ein oder mehrere Argumente gesendet werden. Danach werden die angegebenen Eigenschaften in der Reihenfolge initialisiert, in denen sie in der Initialisiererliste dargestellt sind.  
  
 Jede Initialisierung in der Initialisiererliste besteht die Zuweisung von einem Anfangswert auf einen Member der Klasse ab. Wenn die Klasse definiert ist, werden die Namen und Datentypen der Elemente bestimmt. In den folgenden Beispielen wird die `Customer` Klasse muss vorhanden sein und müssen Mitglieder benannten `Name` und `City` Zeichenfolgenwerte akzeptieren können.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Alternativ können Sie das gleiche Ergebnis abrufen, indem Sie mit dem folgenden Code:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Jede dieser Deklarationen entspricht im folgenden Beispiel erstellt eine `Customer` -Objekts, indem Sie mit dem Standardkonstruktor, und legt dann die Anfangswerte für die `Name` und `City` Eigenschaften mithilfe einer `With` -Anweisung.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Wenn die `Customer` Klasse enthält einen parametrisierten Konstruktor, der Ihnen ermöglicht, einen Wert für Senden `Name`, z. B. können auch deklarieren und initialisieren Sie ein `Customer` Objekt auf folgende Weise:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 Sie müssen nicht alle Eigenschaften, wie im folgenden Code gezeigt zu initialisieren.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Allerdings werden die Initialisierungsliste darf nicht leer sein. Nicht initialisierte Eigenschaften behalten ihre Standardwerte.  
  
### <a name="type-inference-with-named-types"></a>Typrückschluss mit benannten Typen  
 Können Sie den Code für die Deklaration von kürzen `cust1` durch Kombinieren von Objektinitialisierer und lokalen Typrückschluss. Dies ermöglicht das Weglassen der `As` -Klausel in der Variablendeklaration. Der Datentyp der Variablen ist der Typ des Objekts abgeleitet, die durch die Zuweisung erstellt wird. Im folgenden Beispiel den Typ des `cust6` ist `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Hinweise zu benannten Typen  
  
-   Ein Klassenmember kann nicht mehr als einmal in der Objektinitialisiererliste initialisiert werden. Die Deklaration von `cust7` verursacht einen Fehler.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Ein Element kann verwendet werden, um sich selbst oder ein anderes Feld zu initialisieren. Wenn ein Element zugegriffen wird, bevor es wie in der folgenden Deklaration für initialisiert wurde, `cust8`, der Standardwert verwendet werden. Denken Sie daran, dass wenn eine Deklaration, die mithilfe ein Objektinitialisierers verarbeitet wird, ist das erste Ereignis, dass der entsprechende Konstruktor aufgerufen wird. Danach werden die einzelnen Felder in der Initialisiererliste initialisiert. In den folgenden Beispielen wird der Standardwert für `Name` wird für zugewiesen `cust8`, und ein initialisierter Wert zugewiesen ist `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     Im folgenden Beispiel wird den parametrisierten Konstruktor aus `cust3` und `cust4` zu deklarieren und initialisieren `cust10` und `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Objektinitialisierer können geschachtelt werden. Im folgenden Beispiel `AddressClass` ist eine Klasse mit zwei Eigenschaften `City` und `State`, und die `Customer` -Klasse verfügt über eine `Address` -Eigenschaft, die eine Instanz des `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Die Initialisierungsliste darf nicht leer sein.  
  
-   Die Instanz initialisiert wird, darf nicht vom Typ Object sein.  
  
-   Klassenmember, die initialisiert wird, darf nicht freigegebenen Member, schreibgeschützten Member, Konstanten oder Methodenaufrufe sein.  
  
-   Klassenmember, die derzeit initialisiert können nicht indiziert oder qualifiziert werden. In den folgenden Beispielen werden Compilerfehler ausgelöst:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen verwenden Objektinitialisierer zum Erstellen von Instanzen der neue Typen, die Sie nicht explizit definieren und den Namen an. Stattdessen generiert der Compiler einen Typ entsprechend die Eigenschaften, die Sie festlegen, in der Objektinitialisiererliste. Da der Name des Typs nicht angegeben ist, wird bezeichnet als ein *anonymen Typ*. Vergleichen Sie beispielsweise die folgende Deklaration mit der früheren für `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Der einzige Unterschied ist syntaktisch, dass kein Name, nach dem angegeben wird `New` für den Datentyp. Was geschieht, ist jedoch recht stark. Definiert einen neuen anonymen Typ, der zwei Eigenschaften hat der Compiler `Name` und `City`, und erstellt eine Instanz mit den angegebenen Werten. Typrückschluss bestimmt die Art der `Name` und `City` im Beispiel um Zeichenfolgen handelt.  
  
> [!CAUTION]
>  Der Name des anonymen Typs wird vom Compiler generiert und von Kompilierungen abweichen. Der Code sollte nicht verwenden oder basieren auf den Namen eines anonymen Typs.  
  
 Da der Name des Typs nicht verfügbar ist, können kein `As` -Klausel, um deklarieren `cust13`. Der Typ muss nicht abgeleitet werden. Ohne spätes Binden, schränkt dies die Verwendung von anonymen Typen, die lokalen Variablen.  
  
 Anonyme Typen stellen wichtige Unterstützung für [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen. Weitere Informationen zur Verwendung von anonymen Typen in Abfragen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Hinweise zu anonymen Typen  
  
-   In der Regel alle oder die meisten Eigenschaften in der Deklaration eines anonymen Typs wird Schlüsseleigenschaften angegeben sind, durch das Schlüsselwort `Key` vor den Namen der Eigenschaft.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Weitere Informationen zu Schlüsseleigenschaften finden Sie unter [Schlüssel](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Wie bei benannten Typen Initialisiererlisten für Definitionen von anonymen Typen müssen mindestens eine Eigenschaft deklarieren.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Wenn eine Instanz eines anonymen Typs deklariert ist, generiert der Compiler eine entsprechende Definition für den anonymen Typ an. Die Namen und Datentypen der Eigenschaften stammen aus der Deklaration der Instanz, und vom Compiler in der Definition enthalten sind. Die Eigenschaften sind nicht mit dem Namen und im Voraus definiert werden, wie für einen benannten Typ. Ihre Typen abgeleitet werden. Sie können nicht die Datentypen der Eigenschaften angeben, indem Sie mithilfe einer `As` Klausel.  
  
-   Anonyme Typen können auch die Namen und die Werte ihrer Eigenschaften auf verschiedene Weise einrichten. Eine Eigenschaft eines anonymen Typs kann z. B. den Namen und den Wert einer Variablen oder den Namen und Wert einer Eigenschaft eines anderen Objekts dauern.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Weitere Informationen zu den Optionen zum Definieren von Eigenschaften in anonymen Typen finden Sie unter [wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)  
 [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
