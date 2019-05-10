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
ms.openlocfilehash: bf608ebb36a2e8f29e8429b77e023eced67273e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649775"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Objektinitialisierer: Benannte und anonyme Typen (Visual Basic)
Objektinitialisierer können Sie Eigenschaften für ein komplexes Objekt mit einem einzelnen Ausdruck angeben. Sie können zum Erstellen von Instanzen benannter Typen und von anonymen Typen verwendet werden.  
  
## <a name="declarations"></a>Deklarationen  
 Deklarationen von Instanzen von benannten und anonymen Typen können fast identisch aussehen, aber ihre Auswirkungen stimmen nicht überein. Jede Kategorie verfügt über Funktionen und Einschränkungen der eigenen. Das folgende Beispiel zeigt eine bequeme Möglichkeit zum Deklarieren und initialisieren eine Instanz einer Klasse benannte `Customer`, mithilfe einer Objektinitialisiererliste enthalten. Beachten Sie, dass der Name der Klasse nach dem Schlüsselwort angegeben ist `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 Ein anonymer Typ hat keinen verwendbaren Namen. Eine Instanziierung eines anonymen Typs kann nicht aus diesem Grund einen Klassennamen enthalten.  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 Die Anforderungen und die Ergebnisse der beiden Deklarationen sind nicht identisch. Für `namedCust`, `Customer` -Klasse, verfügt eine `Name` Eigenschaft muss bereits vorhanden sein, und die Deklaration erstellt eine Instanz dieser Klasse. Für `anonymousCust`, definiert der Compiler eine neue Klasse, die eine Eigenschaft, eine Zeichenfolge mit dem Namen `Name`, und erstellt eine neue Instanz dieser Klasse.  
  
## <a name="named-types"></a>Benannte Typen  
 Objektinitialisierer bieten eine einfache Möglichkeit, den Konstruktor eines Typs aufzurufen, und legen Sie dann die Werte der Eigenschaften, die einige oder alle in einer einzigen Anweisung. Der Compiler Ruft den entsprechenden Konstruktor für die Anweisung: der Standardkonstruktor, wenn keine Argumente angegeben werden, oder einen parametrisierten Konstruktor, wenn ein oder mehrere Argumente gesendet werden. Danach werden die angegebenen Eigenschaften in der Reihenfolge initialisiert, in denen sie in der Initialisiererliste dargestellt werden.  
  
 Jede Initialisierung in der Initialisiererliste besteht die Zuweisung von einem Anfangswert auf einen Member der Klasse ab. Wenn die Klasse definiert ist, werden die Namen und Datentypen der Elemente bestimmt. In den folgenden Beispielen wird die `Customer` Klasse muss vorhanden sein und müssen haben Mitglieder mit dem Namen `Name` und `City` , können Werte akzeptieren.  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 Alternativ können Sie das gleiche Ergebnis abrufen, mit dem folgenden Code:  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 Jede dieser Deklarationen entspricht im folgenden Beispiel, das erstellt eine `Customer` -Objekt mit dem Standardkonstruktor, und gibt dann die Anfangswerte für die `Name` und `City` Eigenschaften mithilfe einer `With` -Anweisung.  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 Wenn die `Customer` -Klasse enthält einen parametrisierten Konstruktor, der Ihnen ermöglicht, senden Sie einen Wert für `Name`, z. B. können auch deklarieren und initialisieren eine `Customer` Objekt auf folgende Weise:  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 Sie müssen nicht alle Eigenschaften, wie im folgenden Code gezeigt zu initialisieren.  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 Allerdings werden die Initialisierungsliste darf nicht leer sein. Nicht initialisierte Eigenschaften behalten ihre Standardwerte zurück.  
  
### <a name="type-inference-with-named-types"></a>Typrückschluss mit benannten Typen  
 Sie können den Code für die Deklaration von verkürzen `cust1` durch Kombinieren von Objektinitialisierern und lokalen Typrückschluss. Dadurch können Sie weglassen der `As` -Klausel in die Variablendeklaration. Der Datentyp der Variablen wird aus dem Typ des Objekts abgeleitet, die durch die Zuweisung erstellt wird. Im folgenden Beispiel den Typ des `cust6` ist `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>Hinweise zu benannten Typen  
  
- Ein Klassenmember kann nicht mehr als einmal in der Objektinitialisiererliste initialisiert werden. Die Deklaration von `cust7` verursacht einen Fehler.  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- Ein Element kann verwendet werden, um sich selbst oder ein anderes Feld zu initialisieren. Wenn ein Element zugegriffen wird, bevor er, wie die folgende Deklaration für initialisiert wurde `cust8`, der Standardwert verwendet werden. Denken Sie daran, dass wenn eine Deklaration, die einen Objektinitialisierer wird verwendet, die verarbeitet wird, wird als erstes, das ausgeführt wird, dass der geeignete Konstruktor aufgerufen wird. Danach werden die einzelnen Felder in der Initialisierungsliste initialisiert. In den folgenden Beispielen wird der Standardwert für `Name` zugewiesen wird, für die `cust8`, und ein initialisierter Wert zugewiesen ist `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     Das folgende Beispiel verwendet den parametrisierten Konstruktor von `cust3` und `cust4` zu deklarieren und initialisieren `cust10` und `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- Objektinitialisierer können geschachtelt werden. Im folgenden Beispiel `AddressClass` ist eine Klasse mit zwei Eigenschaften, `City` und `State`, und die `Customer` -Klasse verfügt über eine `Address` -Eigenschaft, die eine Instanz von `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- Die Initialisierungsliste darf nicht leer sein.  
  
- Die Instanz initialisiert wird, darf nicht vom Typ Object sein.  
  
- Klassenmember initialisiert wird, darf nicht freigegebenen Member, schreibgeschützten Member, Konstanten oder Methodenaufrufe sein.  
  
- Klassenmember initialisiert wird, können nicht indiziert oder qualifiziert werden. In den folgenden Beispielen werden Compilerfehler ausgelöst:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen werden Objektinitialisierer zum Erstellen von Instanzen der neue Typen, die Sie nicht explizit definieren und den Namen verwenden. Stattdessen generiert der Compiler einen Typ gemäß den Eigenschaften, die Sie festlegen, in der Objektinitialisiererliste. Da der Name des Typs nicht angegeben ist, wird bezeichnet als ein *anonymen Typs*. Vergleichen Sie beispielsweise die folgende Deklaration mit der früheren für `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 Der einzige Unterschied ist syntaktisch, dass kein Name, nach dem angegeben ist `New` für den Datentyp. Was geschieht, ist jedoch sehr unterschiedlich. Der Compiler definiert einen neuen anonymen Typ, das zwei Eigenschaften `Name` und `City`, und erstellt eine Instanz mit den angegebenen Werten. Typrückschluss bestimmt die Art der `Name` und `City` im Beispiel um Zeichenfolgen handelt.  
  
> [!CAUTION]
>  Der Name des anonymen Typs wird vom Compiler generiert und von Kompilierungen abweichen. Ihr Code sollte nicht verwenden oder basieren auf den Namen eines anonymen Typs.  
  
 Da der Name des Typs nicht verfügbar ist, können kein `As` -Klausel, um zu deklarieren `cust13`. Muss der Typ nicht abgeleitet werden. Ohne spätes Binden, schränkt dies die Verwendung von anonymen Typen müssen die lokalen Variablen.  
  
 Anonyme Typen unterstützen für [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen. Weitere Informationen zur Verwendung von anonymen Typen in Abfragen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Hinweise zu anonymen Typen  
  
- In der Regel alle oder die meisten Eigenschaften in der Deklaration eines anonymen Typs werden Schlüsseleigenschaften, die angegeben werden, durch das Schlüsselwort `Key` vor den Namen der Eigenschaft.  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     Weitere Informationen zu den Schlüsseleigenschaften, finden Sie unter [Schlüssel](../../../../visual-basic/language-reference/modifiers/key.md).  
  
- Wie bei benannten Typen, Initialisierungslisten für Definitionen von anonymen Typen müssen mindestens eine Eigenschaft deklarieren.  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- Wenn eine Instanz eines anonymen Typs deklariert wird, generiert der Compiler eine entsprechende Definition von anonymen Typen. Die Namen und Datentypen der Eigenschaften der Deklaration der Instanz entnommen werden, und vom Compiler in der Definition enthalten sind. Die Eigenschaften sind nicht mit dem Namen und im Voraus definiert werden, wie sie für einen benannten Typ. Die Typen werden abgeleitet. Sie können nicht die Datentypen der Eigenschaften angeben, indem Sie mit einem `As` Klausel.  
  
- Anonyme Typen können auch die Namen und Werte der Eigenschaften auf verschiedene Weise einrichten. Eine Eigenschaft eines anonymen Typs kann z. B. den Namen und den Wert einer Variablen oder der Name und Wert einer Eigenschaft eines anderen Objekts dauern.  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     Weitere Informationen zu den Optionen zum Definieren von Eigenschaften in anonymen Typen finden Sie unter [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Siehe auch

- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
