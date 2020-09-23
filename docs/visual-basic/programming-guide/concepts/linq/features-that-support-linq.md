---
title: Features, die LINQ unterstützen
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: bd63cd36c1f85fd89349293a71ecc5b281165380
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078305"
---
# <a name="visual-basic-features-that-support-linq"></a>Visual Basic-Features, die LINQ unterstützen

Der Name Language-Integrated Query (LINQ) bezieht sich auf Technologie in Visual Basic, die die Abfrage Syntax und andere Sprachkonstrukte direkt in der Sprache unterstützt. Mit LINQ müssen Sie keine neue Sprache erlernen, um eine externe Datenquelle abzufragen. Mithilfe Visual Basic können Sie Daten in relationalen Datenbanken, XML-speichern oder Objekten Abfragen. Diese Integration von Abfragefunktionen in die-Sprache ermöglicht die Kompilierzeit Überprüfung für Syntax Fehler und Typsicherheit. Durch diese Integration wird außerdem sichergestellt, dass Sie bereits wissen, was Sie wissen müssen, um umfangreiche, unterschiedliche Abfragen in Visual Basic zu schreiben.  
  
 In den folgenden Abschnitten werden die Sprachkonstrukte beschrieben, die LINQ in ausreichendem Detail unterstützen, um Ihnen den Einstieg in die Einführungs Dokumentation, Codebeispiele und Beispielanwendungen zu ermöglichen. Sie können auch auf die Links klicken, um ausführlichere Erläuterungen dazu zu erhalten, wie die sprach Features zusammenkommen, um die sprach integrierte Abfrage zu aktivieren. Ein guter Ausgangspunkt ist die exemplarische Vorgehensweise [: Schreiben von Abfragen in Visual Basic](walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Abfrageausdrücke  

 Abfrage Ausdrücke in Visual Basic können in einer deklarativen Syntax ausgedrückt werden, die mit der von SQL oder XQuery vergleichbar ist. Zum Zeitpunkt der Kompilierung wird die Abfrage Syntax in Methodenaufrufe der Implementierung der Standard Abfrage Operator-Erweiterungs Methoden eines LINQ-Anbieters konvertiert. Anwendungen steuern, welche Standard Abfrage Operatoren sich im Gültigkeitsbereich befinden, indem Sie den entsprechenden Namespace mit einer- `Imports` Anweisung angeben. Die Syntax für einen Visual Basic Abfrage Ausdruck sieht wie folgt aus:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Weitere Informationen finden Sie unter [Einführung in LINQ in Visual Basic](../../language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Implizit typisierte Variablen  

 Anstatt explizit einen Typ anzugeben, wenn Sie eine Variable deklarieren und initialisieren, können Sie den Compiler zum ableiten und Zuweisen des Typs aktivieren. Dies wird als *lokaler Typrückschluss*bezeichnet.  
  
 Variablen, deren Typen abgeleitet werden, sind stark typisiert, genauso wie Variablen, deren Typ Sie explizit angeben. Der lokale Typrückschluss funktioniert nur, wenn Sie eine lokale Variable in einem Methoden Text definieren. Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md) und [lokaler Typrückschluss](../../language-features/variables/local-type-inference.md).  
  
 Im folgenden Beispiel wird der lokale Typrückschluss veranschaulicht. Um dieses Beispiel verwenden zu können, müssen Sie `Option Infer` auf festlegen `On` .  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 Der lokale Typrückschluss ermöglicht auch die Erstellung anonymer Typen, die weiter unten in diesem Abschnitt beschrieben werden und für LINQ-Abfragen notwendig sind.  
  
 Im folgenden LINQ-Beispiel tritt ein Typrückschluss auf, wenn `Option Infer` entweder `On` oder ist `Off` . Ein Kompilierzeitfehler tritt auf, wenn den Wert hat `Option Infer` `Off` und `Option Strict` ist `On` .  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Objektinitialisierer  

 Objektinitialisierer werden in Abfrage Ausdrücken verwendet, wenn Sie einen anonymen Typ erstellen müssen, um die Ergebnisse einer Abfrage zu speichern. Sie können auch zum Initialisieren von Objekten benannter Typen außerhalb von Abfragen verwendet werden. Wenn Sie einen Objektinitialisierer verwenden, können Sie ein Objekt in einer einzelnen Zeile initialisieren, ohne einen Konstruktor explizit aufrufen zu müssen. Angenommen, Sie verfügen über eine Klasse `Customer` mit dem Namen, die über öffentliche `Name` und- `Phone` Eigenschaften sowie andere Eigenschaften verfügt, kann ein Objektinitialisierer auf diese Weise verwendet werden:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Weitere Informationen finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Anonyme Typen  

 Anonyme Typen stellen eine bequeme Möglichkeit dar, einen Satz von Eigenschaften temporär zu einem Element zu gruppieren, das Sie in ein Abfrageergebnis einschließen möchten. Dadurch können Sie eine beliebige Kombination der verfügbaren Felder in der Abfrage in beliebiger Reihenfolge auswählen, ohne einen benannten Datentyp für das Element zu definieren.  
  
 Ein *anonymer Typ* wird vom Compiler dynamisch erstellt. Der Name des Typs wird vom Compiler zugewiesen und kann bei jeder neuen Kompilierung geändert werden. Daher kann der Name nicht direkt verwendet werden. Anonyme Typen werden wie folgt initialisiert:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Weitere Informationen finden Sie unter [Anonyme Typen](../../language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Erweiterungsmethoden  

 Erweiterungs Methoden ermöglichen es Ihnen, Methoden zu einem Datentyp oder einer Schnittstelle außerhalb der Definition hinzuzufügen. Mit dieser Funktion können Sie einem vorhandenen Typ neue Methoden hinzufügen, ohne den Typ tatsächlich zu ändern. Die Standard Abfrage Operatoren sind selbst eine Reihe von Erweiterungs Methoden, die LINQ-Abfragefunktionen für jeden Typ bereitstellen, der implementiert <xref:System.Collections.Generic.IEnumerable%601> . Andere Erweiterungen für <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Union%2A> und <xref:System.Linq.Enumerable.Intersect%2A> .  
  
 Die folgende Erweiterungsmethode fügt der-Klasse eine Print-Methode hinzu <xref:System.String> .  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Die-Methode wird wie eine normale Instanzmethode von aufgerufen <xref:System.String> :  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  

 Ein Lambda-Ausdruck ist eine Funktion ohne einen Namen, der einen einzelnen Wert berechnet und zurückgibt. Anders als benannte Funktionen kann ein Lambda-Ausdruck gleichzeitig definiert und ausgeführt werden. Im folgenden Beispiel wird 4 angezeigt.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 Sie können die Definition des Lambda-Ausdrucks einem Variablennamen zuweisen und dann den Namen verwenden, um die Funktion aufzurufen. Im folgenden Beispiel wird auch 4 angezeigt.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 In LINQ unterliegen Lambda-Ausdrücke vielen der Standard Abfrage Operatoren. Der Compiler erstellt Lambda-Ausdrücke, um die Berechnungen zu erfassen, die in grundlegenden Abfrage Methoden wie `Where` , `Select` , `Order By` , `Take While` und anderen definiert sind.  
  
 Der folgende Code definiert z. b. eine Abfrage, die alle leitenden Studenten aus einer Liste von Schülern zurückgibt.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 Die Abfrage Definition wird in Code kompiliert, der dem folgenden Beispiel ähnelt, in dem zwei Lambda-Ausdrücke verwendet werden, um die Argumente für `Where` und anzugeben `Select` .  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Beide Versionen können mithilfe einer-Schleife ausgeführt werden `For Each` :  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Weitere Informationen finden Sie unter [Lambdaausdrücke](../../language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Language Integrated Query (LINQ) (Visual Basic)](index.md)
- [Erste Schritte mit LINQ in Visual Basic](getting-started-with-linq.md)
- [LINQ und Zeichenfolgen (Visual Basic)](linq-and-strings.md)
- [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
