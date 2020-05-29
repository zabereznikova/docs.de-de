---
title: Verwenden des .NET Compiler Platform SDK-Syntaxmodells
description: Diese Übersicht bietet einen Überblick über die Typen, die Sie zum Verstehen und Bearbeiten von Syntaxknoten verwenden.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: fdb13095c2b91e54d58988a51a51b05652e57ea6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208394"
---
# <a name="work-with-syntax"></a>Arbeiten mit der Syntax

Die *Syntaxstruktur* ist eine grundlegende Datenstruktur, die von Compiler-APIs verfügbar gemacht wird. Diese Strukturen stellen die lexikalische und syntaktische Struktur des Quellcodes dar. Sie erfüllen zwei wichtige Aufgaben:

- Damit Tools wie zum Beispiel eine IDE, Add-Ins, Codeanalysetools und Refactorings die syntaktische Struktur von Quellcode in dem Projekt eines Benutzers anzeigen und verarbeiten können.
- Damit Tools wie zum Beispiel Refactorings und eine IDE ermöglicht wird, Quellcode auf natürliche Weise zu erstellen, zu ändern und neu anzuordnen, ohne den Text direkt zu bearbeiten. Durch Erstellen und Bearbeiten von Strukturen können Tools einfach Quellcode erstellen und neu anordnen.

## <a name="syntax-trees"></a>Syntaxstrukturen

Syntaxstrukturen sind die primär verwendete Struktur für Kompilierung, Codeanalyse, Bindung, Refactoring, IDE-Funktionen und Codegenerierung. Kein Teil des Quellcodes kann verstanden werden, ohne zunächst als eines von vielen bekannten strukturellen Sprachelementen identifiziert und kategorisiert worden zu sein.

Syntaxstrukturen verfügen über drei wichtige Attribute. Das erste Attribut ist, dass Syntaxstrukturen alle Quellinformationen in voller Genauigkeit enthalten. Volle Genauigkeit bedeutet: Die Syntaxstruktur enthält jede Information aus dem Quelltext, jedes grammatische Konstrukt, jedes lexikalische Token und alles, was dazwischen liegt – einschließlich Leerzeichen, Kommentaren und Präprozessordirektiven. Zum Beispiel wird jedes Literal, das in der Quelle erwähnt wird, so dargestellt, wie es eingegeben wurde. Syntaxstrukturen erfassen auch Fehler im Quellcode, wenn das Programm unvollständig oder falsch formatiert ist, indem übersprungene oder fehlende Token angezeigt werden.

Das zweite Attribut von Syntaxstrukturen ist, dass sie den exakten Text, aus dem sie analysiert wurden, produzieren können. Es ist möglich, die im Knoten verankerte Textdarstellung der Teilstruktur aus einem beliebigen Syntaxknoten zu erhalten. Diese Fähigkeit bedeutet, dass Syntaxstrukturen verwendet werden können, um Quelltext zu erstellen und zu bearbeiten. Durch das Erstellen einer Struktur erstellen Sie gleichzeitig auch den entsprechenden Text, und durch das Bearbeiten einer Syntaxstruktur (d. h. das Erstellen einer neuen Struktur durch das Ändern einer vorhandenen Struktur) nehmen Sie Änderungen am Text vor.

Das dritte Attribut von Syntaxstrukturen ist, dass sie unveränderlich und threadsicher sind. Nach dem Erstellen ist eine Struktur eine Momentaufnahme des aktuellen Zustands des Codes, die sich nie ändert. Dadurch können mehrere Benutzer gleichzeitig mit der selben Syntaxstruktur in verschiedenen Threads interagieren, ohne etwas sperren oder duplizieren zu müssen. Da Strukturen unveränderlich sind, und keine direkten Änderungen an ihnen vorgenommen werden können, sind Factorymethoden hilfreich beim Erstellen und Bearbeiten von Syntaxstrukturen, weil sie zusätzliche Momentaufnahmen von der Struktur erstellen. Strukturen sind bei der Wiederverwendung von grundlegenden Knoten effizient, weshalb eine neue Version schnell und mit geringem zusätzlichem Speicherplatz neu erstellt werden kann.

Eine Syntaxstruktur ist eine Datenstruktur, in der nichtterminale Strukturelemente anderen Elementen übergeordnet sind. Jede Syntaxstruktur besteht aus Knoten, Token und Trivia.

## <a name="syntax-nodes"></a>Syntaxknoten

Syntaxknoten gehören zu den Hauptelementen der Syntaxstrukturen. Diese Knoten stellen Syntaxkonstrukte wie Deklarationen, Anweisungen, Klauseln und Ausdrücke dar. Jede Kategorie der Syntaxknoten wird durch eine separate Klasse dargestellt, die von <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType> abgeleitet wird. Die Anzahl von Knotenklassen ist nicht erweiterbar.

Alle Syntaxknoten sind nichtterminale Knoten in der Syntaxstruktur, was bedeutet, dass ihnen immer andere Knoten und Token untergeordnet sind. Als untergeordnetes Element eines anderen Knotens hat jeder Knoten einen übergeordneten Knoten, auf den mit der Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxNode.Parent?displayProperty=nameWithType> zugegriffen werden kann. Da Knoten und Strukturen unveränderlich sind, ändert sich das übergeordnete Element eines Knotens nie. Das übergeordnete Element des Stamms der Struktur ist NULL.

Jeder Knoten verfügt über die Methode <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes?displayProperty=nameWithType>, die die untergeordneten Knoten sequenziell, je nach ihrer Position im Quelltext, auflistet. Diese Auflistung enthält keine Token. Alle Knoten verfügen auch über Methoden zum Untersuchen von Nachfolgern, wie <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantTokens%2A> oder <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantTrivia%2A>, die eine Liste aller Knoten, Token oder Trivia darstellen, die in der Unterstruktur vorhanden sind, die von dem Knoten abstammt.

Darüber hinaus macht jede Unterklasse der Syntaxknoten alle identischen untergeordneten Elemente durch stark typisierte Eigenschaften verfügbar. Zum Beispiel verfügt eine Knotenklasse <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax> über drei zusätzliche Eigenschaften, die auf binäre Operatoren beschränkt sind: <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left>, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> und <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right>. Der Typ von <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left> und <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right> ist <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ExpressionSyntax>, und der Typ von <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> ist <xref:Microsoft.CodeAnalysis.SyntaxToken>.

Einige Syntaxknoten haben optionale untergeordnete Elemente. Zum Beispiel hat <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IfStatementSyntax> ein optionales <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ElseClauseSyntax>. Die Eigenschaft gibt NULL zurück, wenn das untergeordnete Element nicht vorhanden ist.

## <a name="syntax-tokens"></a>Syntaxtoken

Syntaxtoken sind terminale Elemente der Grammatik und repräsentieren die kleinsten syntaktischen Elemente des Codes. Sie sind nie übergeordnete Elemente von anderen Knoten oder Token. Syntaxtoken bestehen aus Schlüsselwörtern, Bezeichnern, Literalen und Interpunktion.

Der Typ <xref:Microsoft.CodeAnalysis.SyntaxToken> ist zugunsten der Effizienz ein CLR-Werttyp. Im Gegensatz zu Syntaxknoten gibt es deshalb nur eine Struktur für alle Arten von Token mit verschiedenen Eigenschaften, deren Bedeutung von der Art des dargestellten Tokens abhängt.

Zum Beispiel stellt ein Token für ein Integer-Literal einen numerischen Wert dar. Zusätzlich zu dem unformatierten Quelltext den das Token umfasst, verfügt das Literal-Token über eine <xref:Microsoft.CodeAnalysis.SyntaxToken.Value>-Eigenschaft, die den genauen Ganzzahlwert dekodiert angibt. Diese Eigenschaft wird mit <xref:System.Object> typisiert, weil sie eine von vielen primitiven Typen sein kann.

Die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> gibt die selben Informationen an wie die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxToken.Value> an, sie wird jedoch immer als <xref:System.String> typisiert. Ein Bezeichner in einem C#-Quelltext kann Escapezeichen in Unicode enthalten, aber die Syntax der Escapesequenz selbst zählt nicht als Teil des Namens des Bezeichners. Obwohl der unformatierte Text, den das Token umfasst, die Escapesequenz einschließt, tut die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> das nicht. Stattdessen enthält sie die Unicode-Zeichen, die von dem Escapezeichen identifiziert werden. Wenn der Quelltext zum Beispiel einen Bezeichner enthält, der als `\u03C0` geschrieben wird, dann gibt die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxToken.ValueText> dieses Tokens `π` zurück.

## <a name="syntax-trivia"></a>Syntaxtrivia

Syntaxtrivia stellen hauptsächlich die Bestandteile des Quelltexts dar, die für das normale Verständnis des Codes nicht wichtig sind, z.B. Leerzeichen, Kommentare und Präprozessordirektiven. Syntaxtrivia sind, wie Syntaxtoken, Werttypen. Der einzelne Typ <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType> wird dazu verwendet, alle Arten von Trivia zu beschreiben.

Trivia werden nicht als untergeordnetes Element eines Knotens in der Syntaxstruktur eingeschlossen, weil sie kein Teil der normalen Sprachsyntax sind, und überall zwischen zwei Token auftauchen können. Dennoch sind sie als Teil der Syntaxstruktur vorhanden, weil sie beim Implementieren einer Funktion, wie dem Refactoring und der genauen Beibehaltung des Quelltexts, wichtig sind.

Sie können auf Trivia zugreifen, indem Sie die Sammlungen <xref:Microsoft.CodeAnalysis.SyntaxToken.LeadingTrivia?displayProperty=nameWithType> oder <xref:Microsoft.CodeAnalysis.SyntaxToken.TrailingTrivia?displayProperty=nameWithType> eines Tokens überprüfen. Triviasequenzen werden beim Analysieren von Quelltext den Token zugeordnet. Im Allgemeinen sind einem Token alle darauffolgenden Trivia in der selben Zeile bis zum nächsten Token zugeordnet. Alle Trivia nach dieser Zeile sind dem nächsten Token zugeordnet. Dem ersten Token in der Quelldatei werden alle anfänglichen Trivia zugeordnet, und die letzte Triviasequenz der Datei wird dem Dateiende-Token zugewiesen, das andernfalls eine Breite von 0 (null) hat.

Im Gegensatz zu Syntaxknoten und Token haben Syntaxtrivia keine übergeordneten Elemente. Da sie Teil der Struktur sind und jeweils einem einzelnen Token zugeordnet sind, können Sie auf dieses Token mit der <xref:Microsoft.CodeAnalysis.SyntaxTrivia.Token?displayProperty=nameWithType>-Eigenschaft zugreifen.

## <a name="spans"></a>Span-Eigenschaften

Alle Knoten, Token und Trivia kennen ihre Position im Quelltext und die Anzahl der von ihnen enthaltenen Zeichen. Eine Position im Text wird von einer 32-Bit-Ganzzahl, also einem nullbasierten `char`-Index, dargestellt. Ein <xref:Microsoft.CodeAnalysis.Text.TextSpan>-Objekt ist eine Anfangsposition und eine Anzahl von Zeichen, die jeweils beide als ganze Zahl dargestellt werden. Wenn <xref:Microsoft.CodeAnalysis.Text.TextSpan> die Länge 0 (null) hat, bezieht es sich auf eine Position zwischen zwei Zeichen.

Jeder Knoten verfügt über zwei <xref:Microsoft.CodeAnalysis.Text.TextSpan>-Eigenschaften: <xref:Microsoft.CodeAnalysis.SyntaxNode.Span%2A> und <xref:Microsoft.CodeAnalysis.SyntaxNode.FullSpan%2A>.

Die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxNode.Span%2A> bezeichnet die Textspanne vom ersten Token in der Unterstruktur des Knotens bis zum Ende des letzten Tokens. Diese Spanne umfasst keine führenden oder nachgestellten Trivia.

Die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxNode.FullSpan%2A> bezeichnet die Textspanne, die die normale Spanne des Knotens und die Spannen jeglicher führenden oder nachgestellten Trivia enthält.

Zum Beispiel:

``` csharp
      if (x > 3)
      {
||        // this is bad
          |throw new Exception("Not right.");|  // better exception?||
      }
```

Der Anweisungsknoten im Block verfügt über eine Spanne, die von einzelnen senkrechten Strichen (|) ausgezeichnet wird. Sie umfasst die Zeichen `throw new Exception("Not right.");`. Die vollständige Spanne wird mit doppelten senkrechten Strichen (||) ausgezeichnet. Sie enthält die gleichen Zeichen wie die Spanne und Zeichen, die den führenden und nachfolgenden Trivia zugeordnet sind.

## <a name="kinds"></a>Kind-Eigenschaften

Alle Knoten, Token und Trivia über die Eigenschaft <xref:Microsoft.CodeAnalysis.SyntaxNode.RawKind?displayProperty=nameWithType> vom Typ <xref:System.Int32?displayProperty=nameWithType>, die das genaue Syntax-Element identifiziert, das dargestellt wird. Dieser Wert kann in eine sprachspezifische Enumeration umgewandelt werden. Jede Programmiersprache (C# oder Visual Basic) verfügt über eine einzelne `SyntaxKind`-Enumeration (<xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind?displayProperty=nameWithType> bzw. <xref:Microsoft.CodeAnalysis.VisualBasic.SyntaxKind?displayProperty=nameWithType>), die alle möglichen Knoten, Token und Trivia in der Grammatik auflistet. Diese Konvertierung kann automatisch erfolgen, indem Sie auf die Erweiterungsmethoden <xref:Microsoft.CodeAnalysis.CSharp.CSharpExtensions.Kind%2A?displayProperty=nameWithType> oder <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions.Kind%2A?displayProperty=nameWithType> zugreifen.

Die <xref:Microsoft.CodeAnalysis.SyntaxToken.RawKind>-Eigenschaft ermöglicht einfache Mehrdeutigkeitsvermeidung für Syntaxknotentypen, die die gleiche Knotenklasse nutzen. Für Token und Trivia ist diese Eigenschaft die einzige Möglichkeit, verschiedene Elementtypen voneinander zu unterscheiden.

Angenommen, eine einzelne <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax>-Klasse verfügt über die untergeordneten Elemente <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Left>, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.OperatorToken> und <xref:Microsoft.CodeAnalysis.CSharp.Syntax.BinaryExpressionSyntax.Right>. Dann unterscheidet die <xref:Microsoft.CodeAnalysis.CSharp.CSharpExtensions.Kind%2A>-Eigenschaft, ob es sich um einen Syntaxknoten mit <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.AddExpression>, <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.SubtractExpression> oder <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.MultiplyExpression> handelt.

## <a name="errors"></a>Fehler

Auch wenn der Quelltext Syntaxfehler enthält, wird eine vollständige Syntaxstruktur verfügbar gemacht, die auf die Quelle zurückführbar ist. Wenn der Parser auf Code trifft, der nicht der definierten Syntax der Programmiersprache entspricht, nutzt er eines von zwei Verfahren, um eine Syntaxstruktur zu erstellen:

- Wenn der Parser eine bestimmte Art von Token erwartet, es aber nicht vorhanden ist, kann er dort, wo er das Token erwartet hat, ein fehlendes Token in die Syntaxstruktur einfügen. Ein fehlendes Token stellt das Token dar, das vom Parser erwartet wurde, es besitzt jedoch eine leere Span-Eigenschaft, und die zugehörige <xref:Microsoft.CodeAnalysis.SyntaxNode.IsMissing?displayProperty=nameWithType>-Eigenschaft gibt `true` an.

- Der Parser kann Token überspringen, bis er ein Token findet, bei dem er mit der Analyse fortfahren kann. Wenn das der Fall ist, werden die übersprungenen Token als Triviaknoten mit der Eigenschaft <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.SkippedTokensTrivia> angefügt.
