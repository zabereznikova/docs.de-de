---
title: Visual Basic-Funktionen, die LINQ unterstützen
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643899"
---
# <a name="visual-basic-features-that-support-linq"></a>Visual Basic-Funktionen, die LINQ unterstützen
Der Name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] bezieht sich auf Technologie in Visual Basic unterstützt Abfragesyntax und andere Sprachkonstrukte direkt in der Sprache. Mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], Sie müssen keine erfahren, eine neue Sprache für die Abfrage einer externen Datenquelle. Sie können für Daten in relationalen Datenbanken, XML-Speicher oder Objekte Abfragen, mit Visual Basic. Dank der Integration von Abfragefunktionen in der Sprache ermöglicht kompilierzeitüberprüfung für Syntaxfehler und typsicherheit. Diese Integration wird auch sichergestellt, dass Sie bereits, die meisten Sie habe kennen sollten wissen, um umfassenden und vielfältigen Abfragen in Visual Basic schreiben.  
  
 In den folgenden Abschnitten wird beschrieben, die Sprachkonstrukte, die LINQ, detailliert genug unterstützen, um zu beginnen, lesen Sie die einführende Dokumentation, Codebeispiele und Beispielanwendungen zu können. Sie können auch klicken Sie auf die Links, um ausführlichere erläuterungen wie die Funktionen der Programmiersprache zusammentreffen, um LINQ-Abfrage zu aktivieren. Ist eine gute Möglichkeit zum [Exemplarische Vorgehensweise: Schreiben von Abfragen in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Abfrageausdrücke  
 Abfrageausdrücke in Visual Basic können in einer deklarativen Syntax ähnlich wie SQL oder XQuery ausgedrückt werden. Zum Zeitpunkt der Kompilierung wird die Abfragesyntax in Methodenaufrufe an eine LINQ-Anbieter-Implementierung, der die Standardabfrageoperator-Erweiterungsmethoden konvertiert. Anwendungen steuern, welche Standardabfrageoperatoren im Bereich durch Angabe der entsprechenden Namespaces mit einem `Imports` Anweisung. Syntax für eine Visual Basic-Abfrageausdruck sieht folgendermaßen aus:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Implizit typisierte Variablen  
 Anstatt beim Deklarieren und eine Variablen initialisieren einen Typ explizit anzugeben, können Sie den Compiler ableiten, und weisen Sie den Typ aktivieren. Dies wird als bezeichnet *lokaler Typrückschluss*.  
  
 Variablen, deren Typen abgeleitet werden, sind stark, wie Variablen typisiert, deren Typ Sie explizit angeben. Lokaler Typrückschluss funktioniert nur, wenn Sie eine lokale Variable in einem Methodentext definieren. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Das folgende Beispiel veranschaulicht den lokalen Typrückschluss. Um dieses Codebeispiel verwenden zu können, müssen Sie festlegen `Option Infer` auf `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Lokaler Typrückschluss ist es außerdem möglich, anonyme Typen zu erstellen, die später in diesem Abschnitt beschrieben werden und sind für LINQ-Abfragen erforderlich.  
  
 Im folgenden Beispiel LINQ Typrückschluss tritt auf, wenn `Option Infer` handelt es sich um `On` oder `Off`. Ein Fehler während der Kompilierung tritt auf, wenn `Option Infer` ist `Off` und `Option Strict` ist `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Objektinitialisierer  
 Objektinitialisierer werden in Abfrageausdrücken verwendet, wenn Sie einen anonymen Typ zum Speichern der Ergebnisse einer Abfrage zu erstellen. Sie können auch verwendet werden, um Objekte benannter Typen außerhalb von Abfragen zu initialisieren. Mithilfe eines Objektinitialisierers zu verwenden, können Sie ein Objekt in einer einzelnen Zeile initialisieren, ohne einen Konstruktor explizit aufzurufen. Vorausgesetzt, dass Sie eine Klasse mit dem Namen haben `Customer` mit dem öffentlichen `Name` und `Phone` Eigenschaften zusammen mit anderen Eigenschaften ein Objektinitialisierers kann auf diese Weise verwendet werden:  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Anonyme Typen bieten eine einfache Möglichkeit, einen Satz von Eigenschaften vorübergehend in ein Element zu gruppieren, die in einem Abfrageergebnis enthalten sein sollen. Dadurch können Sie eine beliebige Kombination der verfügbaren Felder in der Abfrage in einer beliebigen Reihenfolge auswählen, ohne einen benannten Datentyp für das Element definiert.  
  
 Ein *anonymen Typ* vom Compiler dynamisch erstellt wird. Der Name des Typs wird vom Compiler zugewiesen, und es kann mit jeder neuen Kompilierung ändern. Aus diesem Grund kann der Name direkt verwendet werden. Anonyme Typen werden auf folgende Weise initialisiert:  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Weitere Informationen finden Sie unter [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Erweiterungsmethoden  
 Erweiterungsmethoden können Sie einen Datentyp oder die Schnittstelle von außerhalb der Klassendefinition Methoden hinzuzufügen. Diese Funktion können Sie neue Methoden aktiviert ist, auf einen vorhandenen Typ hinzufügen, ohne den Typ ändern. Die Standardabfrageoperatoren stellen selbst ein Satz von Erweiterungsmethoden, die bereitstellen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragefunktionen für jeden Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601>. Andere Erweiterungen <xref:System.Collections.Generic.IEnumerable%601> enthalten <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, und <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Die folgende Erweiterungsmethode Fügt eine print-Methode, um die <xref:System.String> Klasse.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Die Methode wird aufgerufen, wie eine gewöhnliche Instanzenmethode dieser <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  
 Ein Lambda-Ausdruck ist eine Funktion ohne Namen, der einen einzelnen Wert berechnet und zurückgibt. Im Gegensatz zu benannten Funktionen kann ein Lambda-Ausdruck definiert und zur gleichen Zeit ausgeführt werden. Das folgende Beispiel zeigt die 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Sie können die Definition des Lambda-Ausdrucks ein Variablenname zugewiesen und verwenden Sie den Namen der Funktion aufgerufen. Das folgende Beispiel zeigt auch 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], Lambda-Ausdrücke zugrunde liegen, viele der Standardabfrageoperatoren. Der Compiler erstellt Lambdaausdrücke, um die Berechnungen zu erfassen, die in grundlegende Abfragemethoden, z. B. definiert sind `Where`, `Select`, `Order By`, `Take While`, und andere.  
  
 Der folgende Code definiert z. B. eine Abfrage, die alle senior Studenten aus einer Liste der Schüler zurückgibt.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 Die Abfragedefinition wird in Code, der ähnlich wie im folgenden Beispiel wird die zwei Lambda-Ausdrücke verwendet werden, an die Argumente für kompiliert `Where` und `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Entweder Version kann ausgeführt werden, mithilfe einer `For Each` Schleife:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
