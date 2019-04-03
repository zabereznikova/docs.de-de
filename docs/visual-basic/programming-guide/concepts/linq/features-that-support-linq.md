---
title: Visual Basic-Features, die LINQ unterstützen
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 155d5c36483accc12d066a5530fea20a563e1498
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814496"
---
# <a name="visual-basic-features-that-support-linq"></a>Visual Basic-Features, die LINQ unterstützen
Der Name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] bezieht sich auf die Technologie in Visual Basic unterstützt query Syntax und andere Sprachkonstrukte direkt in der Sprache. Mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], Sie müssen nicht zum Abfragen einer externen Datenquelle eine neue Sprache lernen. Sie können für Daten in relationalen Datenbanken, XML-Speicher oder Objekten Abfragen, mit Visual Basic. Diese Integration der Abfragefunktionen in der Sprache ermöglicht die Überprüfung auf Syntaxfehler und typsicherheit. Diese Integration wird sichergestellt, dass Sie bereits die meisten Was müssen wissen Sie wissen, umfangreiche und verschiedene Abfragen in Visual Basic schreiben.  
  
 Den folgenden Abschnitten werden die Sprachkonstrukte, die LINQ, detailliert genug unterstützen, um Ihnen den Einstieg beim Lesen der einführenden Dokumentation, Codebeispiele und Beispielanwendungen zu aktivieren. Sie können auch klicken Sie auf die Links, um ausführlichere Erklärungen wie die Sprachfunktionen zusammenkommen, um LINQ-Abfragen zu ermöglichen. Ein guter Ausgangspunkt ist [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Abfrageausdrücke  
 Abfrageausdrücke in Visual Basic können in einer deklarativen Syntax ähnelt der von SQL oder XQuery ausgedrückt werden. Zum Zeitpunkt der Kompilierung wird die Abfragesyntax in Methodenaufrufe an eine LINQ-Anbieter-Implementierung der Erweiterung die Methoden des Standardabfrageoperators konvertiert. Anwendungen steuern, welche die Standardabfrageoperatoren im Gültigkeitsbereich befinden, durch Angabe des entsprechenden Namespaces mit einem `Imports` Anweisung. Syntax für eine Visual Basic-Abfrageausdruck sieht folgendermaßen aus:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Implizit typisierte Variablen  
 Anstatt einen Typ explizit anzugeben, wenn Sie deklarieren und einer Variablen initialisieren, können Sie aktivieren, den Compiler den Typ abzuleiten und zuzuweisen. Dies wird als bezeichnet *lokaler Typrückschluss*.  
  
 Variablen, deren Typen hergeleitet werden, sind, wie Variablen typbindung, deren Typ Sie explizit angeben. Lokaler Typrückschluss funktioniert nur, wenn Sie eine lokale Variable in einem Methodentext definieren. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Das folgende Beispiel veranschaulicht die lokalen Typrückschluss. Um dieses Beispiel verwenden zu können, müssen Sie festlegen `Option Infer` zu `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 Lokaler Typrückschluss ermöglicht auch anonyme Typen zu erstellen, die weiter unten in diesem Abschnitt beschrieben werden und sind für LINQ-Abfragen erforderlich.  
  
 Im folgenden Beispiel LINQ Typrückschluss tritt auf, wenn `Option Infer` ist entweder `On` oder `Off`. Ein Fehler während der Kompilierung tritt auf, wenn `Option Infer` ist `Off` und `Option Strict` ist `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Objektinitialisierer  
 Objektinitialisierer werden in Abfrageausdrücken verwendet, wenn Sie einen anonymen Typ zum Speichern der Ergebnisse einer Abfrage erstellen müssen. Sie können auch zum Initialisieren von Objekten von benannten Typen außerhalb von Abfragen verwendet werden. Mithilfe eines Objektinitialisierers zu verwenden, können Sie ein Objekt in einer einzelnen Zeile ohne expliziten Aufruf eines Konstruktors initialisieren. Vorausgesetzt, dass eine mit dem Namen Klasse `Customer` , bei dem öffentlichen `Name` und `Phone` Eigenschaften ein Objektinitialisierers kann zusammen mit anderen Eigenschaften können auf diese Weise verwendet werden:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Weitere Informationen finden Sie unter [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen bieten eine bequeme Möglichkeit, einen Satz von Eigenschaften vorübergehend in ein Element zu gruppieren, die in einem Abfrageergebnis enthalten sein sollen. Dadurch können Sie eine beliebige Kombination der verfügbaren Felder in der Abfrage in beliebiger Reihenfolge auswählen, ohne die Definition eines benannten Datentyps für das Element.  
  
 Ein *anonymen Typs* wird vom Compiler dynamisch erstellt. Der Name des Typs wird vom Compiler zugewiesen, und es kann mit jeder neuen Kompilierung ändern. Aus diesem Grund kann nicht der Namen direkt verwendet werden. Anonyme Typen werden wie folgt initialisiert:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Erweiterungsmethoden  
 Erweiterungsmethoden ermöglichen Ihnen, einen Datentyp oder eine Schnittstelle, die von außerhalb der Klassendefinition Methoden hinzuzufügen. Dieses Feature können Sie neue Methoden zu einem vorhandenen Typ aktiviert ist, hinzufügen, ohne den Typ ändern. Die Standardabfrageoperatoren sind selbst einen Satz von Erweiterungsmethoden, bieten [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] -Abfragefunktionen für jeden Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601>. Andere Erweiterungen <xref:System.Collections.Generic.IEnumerable%601> enthalten <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, und <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Die folgende Erweiterungsmethode Fügt eine print-Methode, die <xref:System.String> Klasse.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Die Methode wird aufgerufen, wie eine normale Instanzmethode <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  
 Ein Lambda-Ausdruck ist eine Funktion ohne einen Namen, der berechnet und einen einzelnen Wert zurückgibt. Im Gegensatz zu Funktionen mit dem Namen kann ein Lambda-Ausdruck definiert und zur gleichen Zeit ausgeführt werden. Das folgende Beispiel zeigt die 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 Sie können weisen Sie die Definition des Lambda-Ausdrucks einer Variablen namens und klicken Sie dann verwenden Sie den Namen der Funktion aufgerufen. Das folgende Beispiel zeigt auch 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], Lambda-Ausdrücke zugrunde liegen viele der Standardabfrageoperatoren. Der Compiler erstellt die Lambda-Ausdrücke, um die Berechnungen zu erfassen, die in der grundlegenden Abfragemethoden, z. B. definiert sind `Where`, `Select`, `Order By`, `Take While`, und andere.  
  
 Der folgende Code definiert z. B. eine Abfrage, die alle senior Studenten aus einer Liste der Studenten zurückgibt.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 Die Abfragedefinition wird in Code, der ähnlich wie im folgenden Beispiel, die zwei Lambda-Ausdrücken verwendet werden, an die Argumente für kompiliert `Where` und `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Beide Versionen kann ausgeführt werden, indem Sie mit einem `For Each` Schleife:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
