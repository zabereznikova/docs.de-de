---
title: "Object Initializers: Named and Anonymous Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ObjectInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object initializers [Visual Basic]"
  - "anonymous types [Visual Basic], object initializers"
  - "initializing properties [Visual Basic]"
  - "initializers [Visual Basic]"
  - "named types [Visual Basic]"
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Object Initializers: Named and Anonymous Types (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Durch Objektinitialisierer können mithilfe eines einzelnen Ausdrucks die Eigenschaften für ein komplexes Objekt angegeben werden.  Sie können verwendet werden, um Instanzen von benannten Typen und anonymen Typen zu erstellen.  
  
## Deklarationen  
 Deklarationen von Instanzen benannter und anonymer Typen können fast identisch aussehen. Ihre Auswirkungen sind jedoch unterschiedlich.  Jede Kategorie verfügt über eigene Möglichkeiten und Einschränkungen.  Im folgenden Beispiel wird eine einfache Möglichkeit gezeigt, unter Verwendung einer Objektinitialisiererliste eine Instanz einer benannten Klasse, der `Customer`\-Klasse, zu deklarieren und zu initialisieren.  Beachten Sie, dass der Name der Klasse nach dem Schlüsselwort `New` angegeben wird.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Ein anonymer Typ hat keinen verwendbaren Namen.  Daher kann eine Instanziierung eines anonymen Typs keinen Klassennamen einschließen.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Die Anforderungen und Ergebnisse der beiden Deklarationen sind nicht identisch.  Für `namedCust` muss bereits eine `Customer`\-Klasse mit einer `Name`\-Eigenschaft vorhanden sein. Die Deklaration erstellt eine Instanz dieser Klasse.  Für `anonymousCust` definiert der Compiler eine neue Klasse mit einer Eigenschaft, einer Zeichenfolge mit dem Namen `Name`, und erstellt eine neue Instanz dieser Klasse.  
  
## Benannte Typen  
 Objektinitialisierer bieten eine einfache Möglichkeit, den Konstruktor eines Typs aufzurufen und die Werte einiger oder aller Eigenschaften in einer einzigen Anweisung festzulegen.  Der Compiler ruft den entsprechenden Konstruktor für die Anweisung auf: den Standardkonstruktor, wenn keine Argumente angegeben werden, oder einen parametrisierten Konstruktor, wenn mindestens ein Argument übergeben wird.  Anschließend werden die angegebenen Eigenschaften in der Reihenfolge initialisiert, in der sie in der Initialisiererliste angezeigt werden.  
  
 Jede Initialisierung in der Initialisiererliste besteht aus der Zuweisung eines Anfangswerts zu einem Member der Klasse.  Die Namen und Datentypen der Member werden bei der Definition der Klasse bestimmt.  In den folgenden Beispielen muss die `Customer`\-Klasse vorhanden sein. Diese muss über Member mit Namen `Name` und `City` verfügen, die Zeichenfolgenwerte akzeptieren.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Alternativ erhalten Sie das gleiche Ergebnis, indem Sie den folgenden Code verwenden:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Jede dieser Deklarationen entspricht dem folgenden Beispiel, in dem mithilfe des Standardkonstruktors ein `Customer`\-Objekt erzeugt wird und dann unter Verwendung einer `With`\-Anweisung Anfangswerte für die `Name`\-Eigenschaft und die `City`\-Eigenschaft angegeben werden.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Wenn die `Customer`\-Klasse einen parametrisierten Konstruktor enthält, mit dem beispielsweise ein Wert für `Name` festgelegt werden kann, können Sie ein `Customer`\-Objekt auch folgendermaßen deklarieren und initialisieren:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 Wie folgender Code zeigt, müssen Sie nicht alle Eigenschaften initialisieren.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Die Initialisierungsliste darf jedoch nicht leer sein.  Nicht initialisierte Eigenschaften behalten ihre Standardwerte.  
  
### Typrückschluss mit benannten Typen  
 Sie können den Code für die Deklaration von `cust1` verkürzen, indem Sie Objektinitialisierer und lokalen Typrückschluss kombinieren.  Dadurch können Sie auf die `As`\-Klausel in der Variablendeklaration verzichten.  Der Datentyp der Variablen wird vom Typ des von der Zuweisung erstellten Objekts abgeleitet.  Im folgenden Beispiel ist `cust6` vom Typ `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### Hinweise zu benannten Typen  
  
-   Ein Klassenmember kann nicht mehr als einmal in der Objektinitialisiererliste initialisiert werden.  Die Deklaration von `cust7` verursacht einen Fehler.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Ein Member kann verwendet werden, um sich selbst oder ein anderes Feld zu initialisieren.  Wenn, wie in der folgenden Deklaration für `cust8`, auf einen Member zugegriffen wird, bevor er initialisiert wurde, wird der Standardwert verwendet.  Beachten Sie, dass bei der Verarbeitung einer Deklaration, die einen Objektinitialisierer verwendet, als erstes der entsprechende Konstruktor aufgerufen wird.  Danach werden die einzelnen Felder in der Initialisiererliste initialisiert.  In den folgenden Beispielen wird der Standardwert für `Name` für `cust8` zugewiesen, und `cust9` wird ein initialisierter Wert zugewiesen.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     Im folgenden Beispiel wird der parametrisierte Konstruktor aus `cust3` und `cust4` verwendet, um `cust10` und `cust11` zu deklarieren und zu initialisieren.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Objektinitialisierer können geschachtelt werden.  Im folgenden Beispiel ist `AddressClass` eine Klasse mit zwei Eigenschaften, `City` und `State`. Die `Customer`\-Klasse verfügt über eine `Address`\-Eigenschaft, die eine Instanz von `AddressClass` ist.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Die Initialisierungsliste darf nicht leer sein.  
  
-   Die Instanz, die initialisiert wird, kann nicht vom Typ Object sein.  
  
-   Klassenmember, die initialisiert werden, können keine freigegebenen Member, schreibgeschützten Member, Konstanten oder Methodenaufrufe sein.  
  
-   Klassenmember, die initialisiert werden, können nicht indiziert oder qualifiziert werden.  In den folgenden Beispielen werden Compilerfehler ausgelöst:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## Anonyme Typen  
 Anonyme Typen verwenden Objektinitialisierer, um Instanzen neuer Typen zu erstellen, die Sie nicht explizit definieren und benennen.  Stattdessen generiert der Compiler einen Typ entsprechend den Eigenschaften, die Sie in der Objektinitialisiererliste festlegen.  Da der Name des Typs nicht angegeben wird, wird er als *anonymer Typ* bezeichnet.  Vergleichen Sie die folgende Deklaration z. B. mit der früheren für `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Der einzige syntaktische Unterschied besteht darin, dass nach `New` kein Name für den Datentyp angegeben wird.  Es geschieht jedoch etwas ganz anderes.  Vom Compiler wird ein neuer anonymer Typ definiert, der über zwei Eigenschaften, `Name` und `City`, verfügt. Dann wird mit den angegebenen Werten eine Instanz davon erstellt.  Im Beispiel werden die Typen von `Name` und `City` per Typrückschluss als Zeichenfolgen bestimmt.  
  
> [!CAUTION]
>  Der Name des anonymen Typs wird vom Compiler erzeugt und kann von Kompilierung zu Kompilierung variieren.  Sie sollten im Code den Namen eines anonymen Typs nicht verwenden oder sich darauf verlassen.  
  
 Da der Name des Typs nicht verfügbar ist, können Sie keine `As`\-Klausel verwenden, um `cust13` zu deklarieren.  Der Typ muss abgeleitet werden.  Ohne die Verwendung später Bindung wird dadurch die Verwendung anonymer Typen auf lokale Variablen eingeschränkt.  
  
 Anonyme Typen unterstützen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]\-Abfragen.  Weitere Informationen zur Verwendung anonymer Typen in Abfragen finden Sie unter [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### Hinweise zu anonymen Typen  
  
-   In der Regel sind alle bzw. die meisten Eigenschaften in einer Deklaration von anonymen Typen Schlüsseleigenschaften, die durch das Schlüsselwort `Key` vor dem Eigenschaftennamen gekennzeichnet werden.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Weitere Informationen zu Schlüsseleigenschaften finden Sie unter [Key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Wie bei benannten Typen müssen Initialisiererlisten für anonyme Typdefinitionen mindestens eine Eigenschaft deklarieren.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Wenn eine Instanz eines anonymen Typs deklariert wird, generiert der Compiler eine entsprechende anonyme Typdefinition.  Die Namen und Datentypen der Eigenschaften werden aus der Deklaration der Instanz übernommen und vom Compiler in die Definition eingefügt.  Die Eigenschaften werden nicht im Voraus benannt und definiert, wie dies bei einem benannten Typ der Fall wäre.  Ihre Typen werden abgeleitet.  Sie können die Datentypen der Eigenschaften nicht durch Verwendung einer `As`\-Klausel angeben.  
  
-   Anonyme Typen können die Namen und Werte ihrer Eigenschaften auch auf andere Weisen bestimmen.  Beispielsweise kann eine Eigenschaft eines anonymen Typs sowohl den Namen als auch den Wert einer Variablen oder aber den Namen und den Wert einer Eigenschaft eines anderen Objekts annehmen.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Weitere Informationen über die Optionen zum Definieren von Eigenschaften in anonymen Typen finden Sie unter [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## Siehe auch  
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)   
 [How to: Declare an Object by Using an Object Initializer](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)