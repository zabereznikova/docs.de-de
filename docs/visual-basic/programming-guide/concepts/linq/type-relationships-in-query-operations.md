---
title: Typbeziehungen in Abfrageoperationen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a966b69feca7a7021cafbccb7971913ea781c479
ms.lasthandoff: 03/13/2017

---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Typbeziehungen in Abfrageoperationen (Visual Basic)
Variablen in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Abfrage Vorgänge sind stark typisiert und müssen miteinander kompatibel sein. Starke Typisierung wird in der Datenquelle, in der Abfrage selbst und in die Ausführung der Abfrage verwendet werden. Die folgende Abbildung Begriffe, die zum Beschreiben einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage. Weitere Informationen über die Teile einer Abfrage finden Sie unter [Grundlegende Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Pseudocode-Abfrage mit hervorgehobenen Elementen.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Teile einer LINQ-Abfrage  
  
 Der Typ der Bereichsvariablen in der Abfrage muss mit dem Typ der Elemente in der Datenquelle übereinstimmen. Der Typ der Abfragevariablen muss kompatibel mit dem Sequenzelement gemäß der `Select` Klausel. Schließlich der Typ der Sequenzelemente auch muss kompatibel mit dem Typ, der die Loop-Steuerelementvariable, die in verwendet wird die `For Each` -Anweisung, die die Abfrage ausgeführt wird. Diese starke Typisierung erleichtert die Identifizierung von Typfehler zur Kompilierzeit.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]erleichtert eine starke Typisierung durch die Implementierung von lokaler Typrückschluss, auch bekannt als *implizite Typisierung*. Feature im vorherigen Beispiel verwendet wird, und sehen Sie in allen verwendet die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Beispiele und Dokumentation. Der lokale Typrückschluss erfolgt in Visual Basic einfach mithilfe einer `Dim` -Anweisung ohne ein `As` Klausel. Im folgenden Beispiel `city` als Zeichenfolge stark typisiert ist.  
  
 [!code-vb[VbLINQTypeRels&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Der lokale Typrückschluss funktioniert nur, wenn `Option Infer` Wert `On`. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Auch wenn Sie den lokalen Typrückschluss in einer Abfrage verwenden, sind jedoch die gleichen typbeziehungen zwischen den Variablen in der Datenquelle, die Abfragevariable und der Ausführungsschleife Abfrage vorhanden. Es empfiehlt sich, ein grundlegendes Verständnis dieser Typ Beziehungen haben, wenn Sie schreiben [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen oder Arbeiten mit den Beispielen und Codebeispielen in der Dokumentation.  
  
 Sie müssen möglicherweise einen expliziten Typ für eine Bereichsvariable angeben, der nicht den Typ der Datenquelle übereinstimmt. Sie können den Typ der Bereichsvariablen angeben, mit einem `As` Klausel. Dies führt jedoch zu einem Fehler, wenn die Konvertierung ist ein [einschränkende Konvertierung](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und `Option Strict` Wert `On`. Wir empfehlen daher, die aus der Datenquelle abgerufenen Werte die Konvertierung ausführen. Sie können die Werte in den Typ der expliziten Bereich aus der Datenquelle konvertieren, mithilfe der <xref:System.Linq.Enumerable.Cast%2A>-Methode.</xref:System.Linq.Enumerable.Cast%2A> Sie können auch die Werte in ausgewählten Umwandeln der `Select` -Klausel, um einen expliziten Typ, der den Typ der Bereichsvariablen unterscheidet. Diese Punkte werden im folgenden Code veranschaulicht.  
  
 [!code-vb[VbLINQTypeRels&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Abfragen, die ganze Elemente der Quelldaten zurückgeben  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrageoperation, die eine Sequenz von Elementen, die aus den Quelldaten ausgewählt zurückgibt. Die Quelle `names`, enthält ein Array von Zeichenfolgen, und die Abfrageausgabe ist eine Sequenz mit Zeichenfolgen, die mit dem Buchstaben M beginnen.  
  
 [!code-vb[VbLINQTypeRels&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Dies entspricht dem folgenden Code, aber viel kürzer und einfacher zu schreiben. Abhängigkeit von lokalem Typrückschluss in Abfragen ist das bevorzugte Format in Visual Basic.  
  
 [!code-vb[VbLINQTypeRels&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 In den beiden vorherigen Codebeispielen, bestehen die folgenden Beziehungen, ob Typen implizit oder explizit bestimmt werden.  
  
1.  Der Typ der Elemente in der Datenquelle `names`, ist der Typ der Bereichsvariablen `name`, in der Abfrage.  
  
2.  Der Typ des Objekts, das ausgewählt ist, `name`, bestimmt den Typ der Abfragevariablen, `mNames`. Hier `name` ist eine Zeichenfolge, daher ist die Abfragevariable IEnumerable (Of String) in Visual Basic.  
  
3.  Die in definierte Abfrage `mNames` ausgeführt wird, der `For Each` Schleife. Die Schleife durchläuft das Ergebnis der Ausführung der Abfrage. Da `mNames`, wenn er ausgeführt wird, gibt eine Sequenz von Zeichenfolgen, die Schleifeniterationsvariable `nm`, ist auch eine Zeichenfolge.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Abfragen, die ein Feld aus ausgewählten Elementen zurückgeben  
 Das folgende Beispiel zeigt eine [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] Abfrageoperation, die eine Sequenz zurückgibt, enthält nur ein Teil jedes Element aus der Datenquelle ausgewählt. Die Abfrage nimmt eine Auflistung von `Customer` Objekte als Datenquelle und projiziert nur die `Name` -Eigenschaft im Ergebnis. Da der Kundenname eine Zeichenfolge ist, erzeugt die Abfrage eine Sequenz von Zeichenfolgen als Ausgabe.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Die Beziehung zwischen Variablen sind vergleichbar mit der einfacher wird.  
  
1.  Der Typ der Elemente in der Datenquelle `customers`, ist der Typ der Bereichsvariablen `cust`, in der Abfrage. In diesem Beispiel ist `Customer`.  
  
2.  Die `Select` Anweisung gibt die `Name` -Eigenschaft jedes `Customer` Objekt anstelle des gesamten Objekts. Da `Name` ist eine Zeichenfolge, die Abfragevariable `custNames`, werden nicht erneut IEnumerable (Of String), der `Customer`.  
  
3.  Da `custNames` stellt eine Sequenz von Zeichenfolgen, die `For Each` die Iterationsvariable-Schleife, `custName`, muss eine Zeichenfolge sein.  
  
 Ohne lokaler Typrückschluss wäre das vorherige Beispiel komplizierter zu schreiben und zu verstehen, wie im folgenden Beispiel gezeigt.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="queries-that-require-anonymous-types"></a>Abfragen, die anonyme Typen erfordern  
 Das folgende Beispiel zeigt eine komplexere Situation. Im vorherigen Beispiel war es unpraktisch, Typen für alle Variablen explizit angeben. In diesem Beispiel ist es unmöglich. Anstelle des gesamten `Customer` Elemente aus der Datenquelle oder ein einzelnes Feld aus jedem Element der `Select` -Klausel in dieser Abfrage gibt zwei Eigenschaften des ursprünglichen `Customer` Objekt: `Name` und `City`. Als Antwort auf die `Select` -Klausel, definiert der Compiler einen anonymen Typ, der diese beiden Eigenschaften enthält. Das Ergebnis der Ausführung `nameCityQuery` in den `For Each` Schleife ist eine Auflistung von Instanzen des neuen anonymen Typs. Da der anonyme Typ keinen verwendbaren Namen hat, kann nicht, geben Sie den Typ des `nameCityQuery` oder `custInfo` explizit. Mit einem anonymen Typ, haben Sie also keinen Typnamen anstelle der `String` in `IEnumerable(Of String)`. Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Obwohl es nicht möglich, Typen für alle Variablen im vorherigen Beispiel angegeben ist, werden die Beziehungen nicht geändert.  
  
1.  Der Typ der Elemente in der Datenquelle ist erneut den Typ der Bereichsvariablen in der Abfrage. In diesem Beispiel `cust` ist eine Instanz von `Customer`.  
  
2.  Da die `Select` -Anweisung erstellt einen anonymen Typ der Abfragevariablen `nameCityQuery`, implizit als anonymer Typ typisiert sein. Ein anonymer Typ hat keinen verwendbaren Namen und kann daher nicht explizit angegeben werden.  
  
3.  Der Typ der Iterationsvariablen in der `For Each` Schleife wird in Schritt 2 erstellten anonymen Typs. Da der Typ keinen verwendbaren Namen aufweist, muss der Typ der Schleifeniterationsvariablen implizit bestimmt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)
