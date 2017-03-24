---
title: "Visual Basic-Features, die LINQ unterstützen | Microsoft-Dokumentation"
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
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
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
ms.openlocfilehash: 3bca15a07a88195589b9c9de5f9842eea42912f1
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-features-that-support-linq"></a>Visual Basic-Funktionen, die LINQ unterstützen
Der Name [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] bezieht sich auf eine Technologie in Visual Basic unterstützt die Abfragesyntax und andere Sprachkonstrukte direkt in der Sprache. Mit [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], Sie müssen nicht für die Abfrage einer externen Datenquelle eine neue Sprache lernen. Sie können Daten in relationalen Datenbanken, XML-Speicher oder Objekte mithilfe von Visual Basic Abfragen. Diese Integration von Abfragefunktionen in der Sprache ermöglicht, während der Kompilierung überprüft auf Syntaxfehler und Sicherheit. Diese Integration sichergestellt, dass Sie bereits wissen, was Sie wissen, umfangreiche, vielseitiger Abfragen in Visual Basic schreiben müssen die meisten.  
  
 Den folgenden Abschnitten werden die Sprachkonstrukte, die LINQ, detailliert genug unterstützen, um zu beginnen, lesen Sie die einführende Dokumentation, Codebeispiele und Beispielanwendungen zu ermöglichen. Sie können auch die Links, um ausführliche Erklärungen der wie die Sprachfeatures zusammen Language integrated Query aktivieren klicken. Ein guter Ausgangspunkt ist [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Abfrageausdrücke  
 Abfrageausdrücke in Visual Basic können in einer deklarativen Syntax ähnlich wie SQL oder XQuery ausgedrückt werden. Zum Zeitpunkt der Kompilierung wird die Abfragesyntax in Methodenaufrufe an den Standardabfrageoperator-Methoden-Erweiterung ein LINQ-Anbieter Implementierung konvertiert. Clientanwendungen steuern, welche die Standardabfrageoperatoren im Gültigkeitsbereich befinden, durch Angabe der entsprechenden Namespaces mit einem `Imports` Anweisung. Syntax für einen Visual Basic-Abfrageausdruck sieht folgendermaßen aus:  
  
 [!code-vb[VbLINQVbFeatures&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Implizit typisierte Variablen  
 Anstatt beim Deklarieren und eine Variablen initialisieren einen Typ explizit anzugeben, können Sie den Compiler an, den Typ abzuleiten und zuzuweisen. Dies wird als bezeichnet *lokaler Typrückschluss*.  
  
 Variablen, deren Typen abgeleitet, werden, wie Variablen stark, deren Typ Sie explizit angeben. Der lokale Typrückschluss funktioniert nur, wenn Sie eine lokale Variable in einem Methodentext definieren. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Im folgende Beispiel wird der lokale Typrückschluss veranschaulicht. Um dieses Codebeispiel verwenden zu können, müssen Sie festlegen `Option Infer` auf `On`.  
  
 [!code-vb[VbLINQVbFeatures&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Der lokale Typrückschluss ermöglicht außerdem das anonyme Typen zu erstellen, die später in diesem Abschnitt beschriebenen und sind für LINQ-Abfragen erforderlich.  
  
 Im folgenden Beispiel LINQ Typrückschluss erfolgt, wenn `Option Infer` ist entweder `On` oder `Off`. Ein Kompilierungsfehler tritt auf, wenn `Option Infer` ist `Off` und `Option Strict` ist `On`.  
  
 [!code-vb[VbLINQVbFeatures&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Objektinitialisierer  
 Objektinitialisierer werden in Abfrageausdrücken verwendet, wenn Sie einen anonymen Typ zum Speichern der Ergebnisse einer Abfrage zu erstellen. Sie können auch verwendet werden, um Objekte benannter Typen außerhalb von Abfragen zu initialisieren. Mithilfe eines Objektinitialisierers zu verwenden, können Sie ein Objekt in einer einzelnen Zeile initialisieren, ohne einen Konstruktor explizit aufzurufen. Angenommen, Sie eine Klasse namens haben `Customer` , bei dem öffentlichen `Name` und `Phone` Eigenschaften, zusammen mit anderen Eigenschaften ein Objektinitialisierers kann auf diese Weise verwendet werden:  
  
 [!code-vb[VbLINQVbFeatures&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen stellen eine bequeme Möglichkeit, einen Satz von Eigenschaften vorübergehend in einem Element zu gruppieren, die in einem Abfrageergebnis angezeigt werden sollen. Dadurch können Sie eine beliebige Kombination der verfügbaren Felder in der Abfrage in einer beliebigen Reihenfolge auswählen, ohne einen benannten Datentyp für das Element definieren.  
  
 Ein *anonymen Typ* wird dynamisch vom Compiler erstellt. Der Name des Typs wird vom Compiler zugewiesen und kann mit jeder neuen Kompilierung ändern. Daher kann der Name direkt verwendet werden. Anonyme Typen werden auf folgende Weise initialisiert:  
  
 [!code-vb[VbLINQVbFeatures&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Erweiterungsmethoden  
 Erweiterungsmethoden können Sie einen Datentyp oder eine Schnittstelle, die von außerhalb der Klassendefinition Methoden hinzuzufügen. Diese Funktion ermöglicht Ihnen, neue Methoden auf einen vorhandenen Typ hinzufügen, ohne den Typ ändern. Die Standardabfrageoperatoren sind selbst eine Reihe von Erweiterungsmethoden, bieten [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragefunktionen für jeden Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> Andere Erweiterungen <xref:System.Collections.Generic.IEnumerable%601>gehören <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, und <xref:System.Linq.Enumerable.Intersect%2A>.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Count%2A> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Die folgende Erweiterungsmethode Fügt eine print-Methode der <xref:System.String>Klasse.</xref:System.String>  
  
 [!code-vb[VbLINQVbFeatures&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Die Methode wird wie jede normale Instanzenmethode von <xref:System.String>:</xref:System.String> aufgerufen.  
  
 [!code-vb[VbLINQVbFeatures&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  
 Ein Lambda-Ausdruck ist eine Funktion ohne Namen, der berechnet und einen einzelnen Wert zurückgibt. Im Gegensatz zu benannten Funktionen kann ein Lambda-Ausdruck definiert und zur gleichen Zeit ausgeführt werden. Im folgende Beispiel wird 4 angezeigt.  
  
 [!code-vb[VbLINQVbFeatures&#8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Sie können die Definition des Lambda-Ausdrucks einem Variablennamen zuweisen und verwenden Sie den Namen der Funktion aufgerufen. Im folgende Beispiel wird ebenfalls 4 angezeigt.  
  
 [!code-vb[VbLINQVbFeatures&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 In [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], liegen Sie vielen der Standardabfrageoperatoren Lambda-Ausdrücke zugrunde. Der Compiler erstellt die Lambda-Ausdrücke, um die Berechnung zu erfassen, die im Wesentlichen Abfragemethoden, z. B. definiert sind `Where`, `Select`, `Order By`, `Take While`, und andere.  
  
 Der folgende Code definiert z. B. eine Abfrage, die aus einer Liste von Studenten alle Studenten im Abschlussjahr zurückgibt.  
  
 [!code-vb[VbLINQVbFeatures&#9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 Die Abfragedefinition wird in Code, der ähnlich wie im folgenden Beispiel, das zwei Lambda-Ausdrücke verwendet, geben Sie die Argumente für kompiliert `Where` und `Select`.  
  
 [!code-vb[VbLINQVbFeatures&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Beide Versionen kann ausgeführt werden, mithilfe einer `For Each` Schleife:  
  
 [!code-vb[VbLINQVbFeatures&#11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Weitere Informationen finden Sie unter [Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
