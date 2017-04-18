---
title: 'Objektinitialisierer: Benannte und anonyme Typen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d684ad4f3dd47dc7400ea401a94660af832ef866
ms.lasthandoff: 03/13/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Objektinitialisierer: Benannte und anonyme Typen (Visual Basic)
Mit Objektinitialisierern können Sie Eigenschaften für ein komplexes Objekt mit einem einzelnen Ausdruck angeben. Sie können zum Erstellen von Instanzen benannter Typen und anonymer Typen verwendet werden.  
  
## <a name="declarations"></a>Deklarationen  
 Deklarationen von Instanzen von benannten und anonymen Typen können fast identisch aussehen, aber die Auswirkungen sind nicht identisch. Jede Kategorie verfügt über Funktionen und Einschränkungen der eigenen. Das folgende Beispiel zeigt eine bequeme Möglichkeit zum Deklarieren und initialisieren eine Instanz einer benannten Klasse, `Customer`, mithilfe einer Initialisierungsliste Objekt. Beachten Sie, dass der Name der Klasse nach dem Schlüsselwort angegeben wird `New`.  
  
 [!code-vb[VbVbalrObjectInit&#1;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Ein anonymer Typ hat keinen verwendbaren Namen. Eine Instanziierung eines anonymen Typs kann nicht aus diesem Grund Klassennamen angeben.  
  
 [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Die Anforderungen und die Ergebnisse der beiden Deklarationen sind nicht identisch. Für `namedCust`, `Customer` -Klasse, verfügt eine `Name` Eigenschaft muss bereits vorhanden sein, und die Deklaration erstellt eine Instanz dieser Klasse. Für `anonymousCust`, definiert der Compiler eine neue Klasse, die eine eine Zeichenfolge mit dem Namen Eigenschaft `Name`, und erstellt eine neue Instanz dieser Klasse.  
  
## <a name="named-types"></a>Benannte Typen  
 Objektinitialisierer bieten eine einfache Möglichkeit, den Konstruktor eines Typs aufzurufen, und legen Sie die Werte einiger oder aller Eigenschaften in einer einzelnen Anweisung. Der Compiler Ruft den entsprechenden Konstruktor für die Anweisung: der Standardkonstruktor, wenn keine Argumente angegeben werden, oder einen parametrisierten Konstruktor, wenn ein oder mehrere Argumente gesendet werden. Danach werden die angegebenen Eigenschaften in der Reihenfolge initialisiert, in denen sie in der Initialisiererliste angezeigt werden.  
  
 Jede Initialisierung in der Initialisiererliste besteht aus der Zuweisung eines Anfangswerts auf einen Member der Klasse. Wenn die Klasse definiert ist, werden die Namen und Datentypen der Elemente bestimmt. In den folgenden Beispielen wird die `Customer` Klasse muss vorhanden sein und müssen Mitglieder benannten `Name` und `City` können Werte akzeptieren.  
  
 [!code-vb[VbVbalrObjectInit&3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Alternativ können Sie das gleiche Ergebnis abrufen, mit dem folgenden Code:  
  
 [!code-vb[VbVbalrObjectInit&4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Jede dieser Deklarationen entspricht dem folgenden Beispiel erstellt eine `Customer` -Objekts, indem Sie mit dem Standardkonstruktor, und legt dann die Anfangswerte für die `Name` und `City` Eigenschaften mithilfe einer `With` Anweisung.  
  
 [!code-vb[VbVbalrObjectInit&5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Wenn die `Customer` Klasse enthält einen parametrisierten Konstruktor, der Ihnen ermöglicht, ein Wert für `Name`, z. B. können auch deklarieren und Initialisieren einer `Customer` Objekt auf folgende Weise:  
  
 [!code-vb[VbVbalrObjectInit&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 Sie müssen nicht alle Eigenschaften, wie im folgenden Code gezeigt zu initialisieren.  
  
 [!code-vb[VbVbalrObjectInit&#7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Allerdings werden die Initialisierungsliste darf nicht leer sein. Nicht initialisierte Eigenschaften behalten ihre Standardwerte.  
  
### <a name="type-inference-with-named-types"></a>Typrückschluss mit benannten Typen  
 Sie können den Code für die Deklaration von verkürzen `cust1` durch Objektinitialisierer und lokalen Typrückschluss kombinieren. Dadurch können Sie weglassen der `As` -Klausel in der Variablendeklaration. Der Datentyp der Variablen wird vom Typ des Objekts abgeleitet, die durch die Zuweisung erstellt wird. Im folgenden Beispiel den Typ des `cust6` ist `Customer`.  
  
 [!code-vb[VbVbalrObjectInit&#8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Hinweise zu benannten Typen  
  
-   Ein Klassenmember kann nicht mehr als einmal in der Objektinitialisiererliste initialisiert werden. Die Deklaration von `cust7` verursacht einen Fehler.  
  
     [!code-vb[VbVbalrObjectInit&#9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Ein Element kann verwendet werden, um sich selbst oder ein anderes Feld zu initialisieren. Wenn ein Mitglied zugegriffen wird, bevor es in der folgenden Deklaration für initialisiert wurde, `cust8`, der Standardwert verwendet werden. Denken Sie daran, dass wenn eine Deklaration, die mithilfe ein Objektinitialisierers verarbeitet wird, ist das erste Ereignis, dass der entsprechende Konstruktor aufgerufen wird. Danach werden die einzelnen Felder in der Initialisierungsliste initialisiert. In den folgenden Beispielen wird der Standardwert für `Name` für zugewiesen ist `cust8`, und ein initialisierter Wert zugewiesen ist `cust9`.  
  
     [!code-vb[VbVbalrObjectInit&#10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     Im folgenden Beispiel wird den parametrisierten Konstruktor aus `cust3` und `cust4` zu deklarieren und initialisieren `cust10` und `cust11`.  
  
     [!code-vb[VbVbalrObjectInit&#11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Objektinitialisierer können geschachtelt werden. Im folgenden Beispiel `AddressClass` ist eine Klasse mit zwei Eigenschaften, `City` und `State`, und die `Customer` -Klasse verfügt über eine `Address` -Eigenschaft, die eine Instanz des `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit&#12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Die Initialisierungsliste darf nicht leer sein.  
  
-   Die initialisierte Instanz darf nicht vom Typ Object sein.  
  
-   Member der Klasse initialisiert wird, können nicht freigegebene Member, schreibgeschützten Member, Konstanten oder Methodenaufrufe sein.  
  
-   Klassenmember, die initialisiert können nicht indiziert oder qualifiziert werden. In den folgenden Beispielen werden Compilerfehler ausgelöst:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen verwenden Objektinitialisierer, um Instanzen neue Typen, die Sie nicht explizit definieren und den Namen erstellen. In diesem Fall generiert der Compiler einen Typ mit den Eigenschaften, die Sie angeben, in der Objektinitialisiererliste. Da der Name des Typs nicht angegeben wird, wird bezeichnet als ein *anonymen Typ*. Vergleichen Sie beispielsweise die folgende Deklaration mit der früheren für `cust6`.  
  
 [!code-vb[VbVbalrObjectInit&#13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Der einzige Unterschied ist syntaktisch, dass kein Name angegeben wird `New` für den Datentyp. Was geschieht, ist jedoch sehr unterschiedlich. Der Compiler definiert einen neuen anonymen Typ mit den beiden Eigenschaften `Name` und `City`, und erstellt eine Instanz mit den angegebenen Werten. Typrückschluss bestimmt die Art der `Name` und `City` im Beispiel um Zeichenfolgen handelt.  
  
> [!CAUTION]
>  Der Name des anonymen Typs wird vom Compiler generiert und kann von Kompilierung zu Kompilierung variieren. Ihr Code sollte nicht verwenden oder basieren auf den Namen eines anonymen Typs.  
  
 Da der Name des Typs nicht verfügbar ist, können kein `As` -Klausel, um deklarieren `cust13`. Der Typ muss abgeleitet werden. Keine späten Bindung, schränkt dies die Verwendung von anonymen Typen auf lokale Variablen.  
  
 Anonyme Typen unterstützen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen. Weitere Informationen zur Verwendung anonymer Typen in Abfragen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Hinweise zu anonymen Typen  
  
-   In der Regel alle oder die meisten der Eigenschaften in der Deklaration eines anonymen Typs werden wichtige Eigenschaften, die angegeben werden, durch das Schlüsselwort `Key` vor dem Eigenschaftennamen.  
  
     [!code-vb[VbVbalrObjectInit&14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Weitere Informationen zu Schlüsseleigenschaften finden Sie unter [Schlüssel](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Wie bei benannten Typen müssen Initialisiererlisten für anonyme Typdefinitionen mindestens eine Eigenschaft deklarieren müssen.  
  
     [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Wenn eine Instanz eines anonymen Typs deklariert wird, generiert der Compiler eine entsprechende anonyme Typdefinition. Die Namen und Datentypen der Eigenschaften werden aus der Deklaration der Instanz übernommen und vom Compiler in der Definition enthalten sind. Die Eigenschaften sind nicht mit dem Namen und im Voraus definiert werden, wie bei einem benannten Typ. Ihre Typen werden abgeleitet. Sie können die Datentypen der Eigenschaften durch Verwendung angeben einer `As` Klausel.  
  
-   Anonyme Typen können die Namen und Werte ihrer Eigenschaften auch auf verschiedene Weise einrichten. Eine Eigenschaft eines anonymen Typs kann z. B. den Namen und den Wert einer Variablen oder den Namen und Wert einer Eigenschaft eines anderen Objekts dauern.  
  
     [!code-vb[VbVbalrObjectInit&#15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Weitere Informationen zu den Optionen zum Definieren von Eigenschaften in anonymen Typen finden Sie unter [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Schlüssel](../../../../visual-basic/language-reference/modifiers/key.md)   
 [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
