---
title: 'Objektinitialisierer: benannte und anonyme Typen'
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
ms.openlocfilehash: 724407fed5bf90ed6e3e470cbabc9e42856cb99a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087478"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Objektinitialisierer: Benannte und anonyme Typen (Visual Basic)

Objektinitialisierer ermöglichen es Ihnen, mithilfe eines einzelnen Ausdrucks Eigenschaften für ein komplexes Objekt anzugeben. Sie können verwendet werden, um Instanzen benannter Typen und anonymer Typen zu erstellen.  
  
## <a name="declarations"></a>Deklarationen  

 Deklarationen von Instanzen von benannten und anonymen Typen können nahezu identisch aussehen, aber ihre Auswirkungen sind nicht identisch. Jede Kategorie verfügt über eigene Möglichkeiten und Einschränkungen. Das folgende Beispiel zeigt eine bequeme Methode zum Deklarieren und Initialisieren einer Instanz einer benannten Klasse, `Customer` , mithilfe einer Objektinitialisiererliste. Beachten Sie, dass der Name der Klasse nach dem-Schlüsselwort angegeben wird `New` .  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 Ein anonymer Typ hat keinen verwendbaren Namen. Daher kann eine Instanziierung eines anonymen Typs keinen Klassennamen enthalten.  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 Die Anforderungen und Ergebnisse der beiden Deklarationen sind nicht identisch. Für `namedCust` muss eine `Customer` Klasse, die über eine- `Name` Eigenschaft verfügt, bereits vorhanden sein, und die-Deklaration erstellt eine Instanz dieser Klasse. Für `anonymousCust` definiert der Compiler eine neue Klasse, die über eine Eigenschaft, eine Zeichenfolge `Name` mit dem Namen und eine neue Instanz dieser Klasse verfügt.  
  
## <a name="named-types"></a>Benannte Typen  

 Objektinitialisierer bieten eine einfache Möglichkeit, den Konstruktor eines Typs aufzurufen und dann die Werte einiger oder aller Eigenschaften in einer einzelnen Anweisung festzulegen. Der Compiler ruft den entsprechenden Konstruktor für die-Anweisung auf: den Parameter losen Konstruktor, wenn keine Argumente dargestellt werden, oder einen parametrisierten Konstruktor, wenn mindestens ein Argument gesendet wird. Anschließend werden die angegebenen Eigenschaften in der Reihenfolge initialisiert, in der Sie in der Initialisiererliste angezeigt werden.  
  
 Jede Initialisierung in der Initialisiererliste besteht aus der Zuweisung eines Anfangs Werts zu einem Member der Klasse. Die Namen und Datentypen der Elemente werden bestimmt, wenn die Klasse definiert ist. In den folgenden Beispielen muss die `Customer` -Klasse vorhanden sein, und Sie müssen Member mit dem Namen und enthalten, `Name` `City` die Zeichen folgen Werte akzeptieren können.  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 Sie können das gleiche Ergebnis auch mithilfe des folgenden Codes abrufen:  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 Jede dieser Deklarationen entspricht dem folgenden Beispiel, das ein `Customer` -Objekt mit dem Parameter losen Konstruktor erstellt und dann `Name` `City` mithilfe einer-Anweisung die Anfangswerte für die-Eigenschaft und die-Eigenschaft angibt `With` .  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 Wenn die `Customer` Klasse einen parametrisierten Konstruktor enthält, der es Ihnen ermöglicht, beispielsweise einen Wert für zu senden `Name` , können Sie auch ein-Objekt wie folgt deklarieren und initialisieren `Customer` :  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 Sie müssen nicht alle Eigenschaften initialisieren, wie im folgenden Code gezeigt.  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 Die Initialisierungs Liste darf jedoch nicht leer sein. Nicht initialisierte Eigenschaften behalten ihre Standardwerte bei.  
  
### <a name="type-inference-with-named-types"></a>Typrückschluss mit benannten Typen  

 Sie können den Code für die Deklaration von kürzen, `cust1` indem Sie Objektinitialisierer und den lokalen Typrückschluss kombinieren. Auf diese Weise können Sie die- `As` Klausel in der Variablen Deklaration weglassen. Der Datentyp der Variablen wird vom Objekttyp abgeleitet, der von der Zuweisung erstellt wird. Im folgenden Beispiel ist der Typ von `cust6` `Customer` .  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>Hinweise zu benannten Typen  
  
- Ein Klassenmember kann nicht mehr als einmal in der Objektinitialisiererliste initialisiert werden. Die Deklaration von `cust7` verursacht einen Fehler.  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- Ein Member kann verwendet werden, um sich selbst oder ein anderes Feld zu initialisieren. Wenn auf einen Member zugegriffen wird, bevor er initialisiert wurde, wie in der folgenden Deklaration für `cust8` , wird der Standardwert verwendet. Beachten Sie, dass beim Verarbeiten einer Deklaration, die einen Objektinitialisierer verwendet, das erste passiert, dass der entsprechende Konstruktor aufgerufen wird. Danach werden die einzelnen Felder in der Initialisiererliste initialisiert. In den folgenden Beispielen wird der Standardwert für `Name` zugewiesen `cust8` , und es wird ein initialisierter Wert in zugewiesen `cust9` .  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     Im folgenden Beispiel wird der parametrisierte Konstruktor von `cust3` und verwendet `cust4` , um und zu deklarieren und zu initialisieren `cust10` `cust11` .  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- Objektinitialisierer können eingebettet werden. Im folgenden Beispiel `AddressClass` ist eine Klasse mit zwei Eigenschaften, `City` und `State` , und die- `Customer` Klasse verfügt über eine- `Address` Eigenschaft, die eine Instanz von ist `AddressClass` .  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- Die Initialisierungs Liste darf nicht leer sein.  
  
- Die initialisierte Instanz kann nicht vom Typ "Object" sein.  
  
- Klassenmember, die initialisiert werden, können keine freigegebenen Member, keine schreibgeschützten Member, Konstanten oder Methodenaufrufe sein.  
  
- Klassenmember, die initialisiert werden, können nicht indiziert oder qualifiziert werden. In den folgenden Beispielen werden Compilerfehler hervorrufen:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Anonyme Typen  

 Anonyme Typen verwenden Objektinitialisierer, um Instanzen von neuen Typen zu erstellen, die Sie nicht explizit definieren und benennen. Stattdessen generiert der Compiler einen Typ entsprechend den Eigenschaften, die Sie in der Objektinitialisiererliste festlegen. Da der Name des Typs nicht angegeben wird, wird er als *anonymer Typ*bezeichnet. Vergleichen Sie beispielsweise die folgende Deklaration mit der vorherigen Deklaration für `cust6` .  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 Der einzige Unterschied besteht darin, dass nach `New` für den Datentyp kein Name angegeben wird. Was passiert jedoch ganz anders. Der Compiler definiert einen neuen anonymen Typ, der über zwei Eigenschaften verfügt: `Name` und `City` , und erstellt eine Instanz davon mit den angegebenen Werten. Der Typrückschluss bestimmt die Typen von `Name` und im Beispiel als Zeichen folgen `City` .  
  
> [!CAUTION]
> Der Name des anonymen Typs wird vom Compiler generiert und kann von der Kompilierung bis zur Kompilierung abweichen. Der Code darf nicht den Namen eines anonymen Typs verwenden oder sich darauf verlassen.  
  
 Da der Name des Typs nicht verfügbar ist, können Sie keine-Klausel verwenden, `As` um zu deklarieren `cust13` . Der Typ muss abgeleitet werden. Ohne die späte Bindung zu verwenden, schränkt dies die Verwendung anonymer Typen auf lokale Variablen ein.  
  
 Anonyme Typen bieten wichtige Unterstützung für LINQ-Abfragen. Weitere Informationen zur Verwendung anonymer Typen in Abfragen finden Sie unter [Anonyme Typen](anonymous-types.md) und [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Hinweise zu anonymen Typen  
  
- In der Regel sind alle oder die meisten Eigenschaften in einer Deklaration eines anonymen Typs Schlüsseleigenschaften, die durch Eingabe des Schlüssel Worts `Key` vor dem Eigenschaftsnamen angezeigt werden.  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     Weitere Informationen zu Schlüsseleigenschaften finden Sie unter [Key](../../../language-reference/modifiers/key.md).  
  
- Wie benannte Typen müssen die Initialisiererlisten für anonyme Typdefinitionen mindestens eine Eigenschaft deklarieren.  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- Wenn eine Instanz eines anonymen Typs deklariert ist, generiert der Compiler eine entsprechende anonyme Typdefinition. Die Namen und Datentypen der Eigenschaften werden aus der Instanzdeklaration entnommen und vom Compiler in der Definition eingeschlossen. Die Eigenschaften werden nicht im Voraus benannt und definiert, wie dies bei einem benannten Typ der Fall wäre. Ihre Typen werden abgeleitet. Die Datentypen der Eigenschaften können nicht mithilfe einer-Klausel angegeben werden `As` .  
  
- Anonyme Typen können auch auf verschiedene Weise die Namen und Werte ihrer Eigenschaften festlegen. Beispielsweise kann eine Eigenschaft eines anonymen Typs sowohl den Namen als auch den Wert einer Variablen oder den Namen und den Wert einer Eigenschaft eines anderen Objekts annehmen.  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     Weitere Informationen zu den Optionen zum Definieren von Eigenschaften in anonymen Typen finden Sie unter Gewusst [wie: Ableiten von Eigenschaften Namen und Typen in Deklarationen anonymer](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)Typen.  
  
## <a name="see-also"></a>Siehe auch

- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Anonyme Typen](anonymous-types.md)
- [Einführung in LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Vorgehensweise: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Schlüssel](../../../language-reference/modifiers/key.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](how-to-declare-an-object-by-using-an-object-initializer.md)
