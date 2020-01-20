---
title: Erste Schritte mit der semantischen Analyse
description: Dieses Tutorial bietet einen Überblick über die Arbeit mit semantischen Analysen mithilfe des .NET Compiler SDK.
ms.date: 02/06/2018
ms.custom: mvc
ms.openlocfilehash: 7bf2f40ea0bc059d9c517780016ca5deb805ceb6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346979"
---
# <a name="get-started-with-semantic-analysis"></a>Erste Schritte mit der semantischen Analyse

Bei diesem Tutorial wird davon ausgegangen, dass Sie mit der Syntax-API vertraut sind. Der Artikel [Erste Schritte mit der Syntaxanalyse](syntax-analysis.md) bietet eine Einführung zu diesem Thema.

Im vorliegenden Tutorial erkunden Sie die APIs für **Symbol** und **Bindung**. Diese APIs bieten Informationen zur _semantischen Bedeutung_ eines Programms. Sie ermöglichen es Ihnen, Fragen zu den Typen zu stellen und zu beantworten, die durch ein Symbol in Ihrem Programm dargestellt werden.

Die Installation des **SDK für die .NET Compiler Platform** ist erforderlich.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-compilations-and-symbols"></a>Grundlegendes zu Kompilierungen und Symbolen

Wenn Sie eine Weile mit dem .NET Compiler SDK arbeiten, werden Ihnen die Unterschiede zwischen der Syntax-API und der Semantik-API immer vertrauter. Die **Syntax-API** ermöglicht es Ihnen, die _Struktur_ eines Programms zu untersuchen. In vielen Fällen benötigen Sie jedoch weitere Informationen zur Semantik bzw. _Bedeutung_ eines Programms. Sie können zwar eine einzelne, losgelöste Codedatei oder einen isolierten Visual Basic- oder C#-Codeausschnitt syntaktisch analysieren, aber es ist wenig sinnvoll, Fragen wie „Welchen Typ weist diese Variable auf?“ sozusagen im luftleeren Raum zu stellen. Die Bedeutung eines Typnamens kann von Assemblyverweisen, Namespaceimporten oder anderen Codedateien abhängig sein. Diese Fragen werden mithilfe der **Semantik-API**, insbesondere der <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType>-Klasse, beantwortet.

Eine Instanz von <xref:Microsoft.CodeAnalysis.Compilation> entspricht einem einzelnen Projekt aus Sicht des Compilers und repräsentiert alle Elemente, die zum Kompilieren eines Visual Basic- oder C#-Programms erforderlich sind. Die **Kompilierung** umfasst die Quelldateien, die kompiliert werden sollen, sowie Assemblyverweise und Compileroptionen. Sie können alle weiteren Informationen in diesem Kontext heranziehen, um die Bedeutung des Codes genau zu verstehen. Eine <xref:Microsoft.CodeAnalysis.Compilation> ermöglicht es Ihnen, **Symbole** zu suchen: Entitäten wie z.B. Typen, Namespaces, Member und Variablen, auf die Namen und andere Ausdrücke verweisen. Der Prozess der Verknüpfung von Namen und Ausdrücken mit **Symbolen** wird als **Bindung** bezeichnet.

Ebenso wie <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType> ist <xref:Microsoft.CodeAnalysis.Compilation> eine abstrakte Klasse mit sprachspezifischen Ableitungen. Wenn Sie eine Instanz von „Compilation“ erstellen, müssen Sie eine Factorymethode in der Klasse <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (oder <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) aufrufen.

## <a name="querying-symbols"></a>Abfragen von Symbolen

In diesem Tutorial betrachten wir noch einmal das Hello World-Programm. Diesmal fragen Sie die Symbole im Programm ab, um zu verstehen, welche Typen durch diese Symbole repräsentiert werden. Sie fragen die Typen in einem Namespace ab und lernen, wie Sie die verfügbaren Methoden in einem Typ finden.

Den fertig gestellten Code für dieses Beispiel finden Sie in [unserem GitHub-Repository](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SemanticQuickStart).

> [!NOTE]
> Die Syntaxstrukturtypen verwenden Vererbung, um die verschiedenen Syntaxelemente zu beschreiben, die an verschiedenen Positionen im Programm gültig sind. Bei der Verwendung dieser APIs müssen häufig Eigenschaften oder Sammlungsmember in bestimmte abgeleitete Typen umgewandelt werden. In den folgenden Beispielen sind die Zuweisung und die Umwandlung separate Anweisungen, bei denen explizit typisierte Variablen verwendet werden. Sie können den Code lesen, um die Rückgabetypen der API und den Laufzeittyp der zurückgegebenen Objekte zu sehen. In der Praxis ist es eher üblich, implizit typisierte Variablen zu verwenden und die Typen der zu untersuchenden Objekte mithilfe von API-Namen zu beschreiben.

Erstellen Sie ein neues **Stand-Alone Code Analysis Tool**-Projekt für C#:

* Wählen Sie in Visual Studio **Datei** > **Neu** > **Projekt** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.
* Wählen Sie unter **Visual C#**  > **Erweiterbarkeit** die Option **Stand-Alone Code Analysis Tool** aus.
* Nennen Sie Ihr Projekt **SemanticQuickStart**, und klicken Sie auf „OK“.

Sie werden das einfache Hello World!- Programm analysieren, das weiter oben in diesem Artikel gezeigt wurde.
Fügen Sie den Text für das Hello World-Programm als Konstante in Ihre `Program`-Klasse ein:

[!code-csharp[Declare the program test](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

Anschließend fügen Sie den folgenden Code hinzu, um die Syntaxstruktur für den Codetext in der `programText`-Konstante zu erstellen.  Fügen Sie Ihrer `Main`-Methode die folgende Zeile hinzu:

[!code-csharp[Create the tree](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

Anschließend erstellen Sie aus der bereits erstellten Struktur eine <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation>. Das Hello World-Beispiel basiert auf den Typen <xref:System.String> und <xref:System.Console>. Sie müssen auf die Assembly verweisen, die diese beiden Typen in Ihrer Kompilierung deklariert. Fügen Sie Ihrer `Main`-Methode folgende Zeile hinzu, um eine Kompilierung Ihrer Syntaxstruktur einschließlich des Verweises auf die entsprechende Assembly zu erstellen:

[!code-csharp[Create the compilation](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

Die <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType>-Methode fügt Verweise zur Kompilierung hinzu. Die <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType>-Methode lädt eine Assembly als Verweis.

## <a name="querying-the-semantic-model"></a>Abfragen des semantischen Modells

Sobald Sie über eine <xref:Microsoft.CodeAnalysis.Compilation> verfügen, können Sie diese nach einem <xref:Microsoft.CodeAnalysis.SemanticModel> für jede <xref:Microsoft.CodeAnalysis.SyntaxTree> in dieser <xref:Microsoft.CodeAnalysis.Compilation> abfragen. Sie können sich das Semantikmodell als die Quelle aller Informationen vorstellen, die Sie normalerweise aus IntelliSense erhalten. Ein <xref:Microsoft.CodeAnalysis.SemanticModel> kann Fragen wie die folgenden beantworten: „Welche Namen befinden sich an diesem Ort im Gültigkeitsbereich?“, „Auf welche Member kann von dieser Methode aus zugegriffen werden?“, „Welche Variablen werden in diesem Textblock verwendet?“ und „Vorauf verweist dieser Name/dieser Ausdruck?“. Fügen Sie diese Anweisung hinzu, um das semantische Modell zu erstellen:

[!code-csharp[Create the semantic model](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a>Binden eines Namens

Die <xref:Microsoft.CodeAnalysis.Compilation> erstellt das <xref:Microsoft.CodeAnalysis.SemanticModel> aus der <xref:Microsoft.CodeAnalysis.SyntaxTree>. Nach dem Erstellen des Modells können Sie es abfragen, um die erste `using`-Direktive zu suchen und die Symbolinformationen für den `System`-Namespace abzurufen. Fügen Sie die folgenden beiden Zeilen zu Ihrer `Main`-Methode hinzu, um das Semantikmodell zu erstellen und das Symbol für die erste using-Anweisung abzurufen:

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

Nachdem das Modell abgerufen wurde, wird der Name in der ersten `using`-Anweisung gebunden, um eine <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> für den `System`-Namespace abzurufen. Dieser Code verdeutlicht auch, dass Sie das **Syntaxmodell** verwenden, um die Struktur des Codes zu ermitteln. Das **Semantikmodell** verwenden Sie, um die Bedeutung des Codes zu verstehen. Das **Syntaxmodell** sucht die Zeichenfolge `System` in der using-Anweisung. Das **Semantikmodell** verfügt über alle Informationen zu den im `System`-Namespace definierten Typen.

Aus dem <xref:Microsoft.CodeAnalysis.SymbolInfo>-Objekt können Sie mithilfe der <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType>-Eigenschaft das <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> abrufen. Diese Eigenschaft gibt das Symbol zurück, auf das dieser Ausdruck verweist. Bei Ausdrücken, die auf nichts verweisen (wie z.B. numerische Literale), lautet diese Eigenschaft `null`. Wenn <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> nicht null ist, bezeichnet <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> den Typ des Symbols. In diesem Beispiel ist die <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType>-Eigenschaft ein <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>. Fügen Sie der `Main`-Methode den folgenden Code hinzu. Der Code ruft das Symbol für den `System`-Namespace ab und zeigt alle untergeordneten Namespaces an, die im `System`-Namespace deklariert sind:

[!code-csharp[Display all the child namespaces](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

Führen Sie das Programm aus. Folgende Ausgabe sollte angezeigt werden:

```output
System.Collections
System.Configuration
System.Deployment
System.Diagnostics
System.Globalization
System.IO
System.Numerics
System.Reflection
System.Resources
System.Runtime
System.Security
System.StubHelpers
System.Text
System.Threading
Press any key to continue . . .
```

> [!NOTE]
> Die Ausgabe umfasst nicht jeden Namespace, der ein untergeordneter Namespace des `System`-Namespace ist. Sie zeigt jeden Namespace an, der in dieser Kompilierung vorhanden ist. Diese verweist nur auf die Assembly, in der `System.String` deklariert ist. Namespaces, die in anderen Assemblys deklariert wurden, sind dieser Kompilierung unbekannt.

### <a name="binding-an-expression"></a>Binden eines Ausdrucks

Der oben gezeigte Code veranschaulicht, wie Sie ein Symbol suchen, indem Sie es an einen Namen binden. Es gibt weitere Ausdrücke in einem C#-Programm, die gebunden werden können, aber keine Namen sind. Um diese Funktion zu demonstrieren, sehen wir uns die Bindung an ein einfaches Zeichenfolgenliteral an.

Das Hello World-Programm enthält eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>: die Hello, World!- Zeichenfolge, die in der Konsole angezeigt wird.

Sie finden die Hello, World!- Zeichenfolge, indem Sie das einzelne Zeichenfolgenliteral im Programm suchen. Wenn Sie den Syntaxknoten gefunden haben, rufen Sie die Typinformationen für diesen Knoten aus dem Semantikmodell ab. Fügen Sie der `Main`-Methode den folgenden Code hinzu:

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

Die <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType>-Struktur enthält eine <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType>-Eigenschaft, die Zugriff auf die semantischen Informationen zum Typ des Literals erlaubt. In diesem Beispiel handelt es sich um den Typ `string`. Fügen Sie eine Deklaration hinzu, die diese Eigenschaft einer lokalen Variable zuweist:

[!code-csharp[Find the semantic information about the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

Zum Abschluss dieses Tutorials erstellen wir eine LINQ-Abfrage, die eine Sequenz aller öffentlichen Methoden erstellt, die im `string`-Typ deklariert sind und eine `string` zurückgeben. Diese Abfrage wird ziemlich komplex – wir bauen sie daher Zeile für Zeile auf und rekonstruieren sie dann als Einzelabfrage. Die Quelle dieser Abfrage ist die Sequenz aller Member, die im `string`-Typ deklariert sind:

[!code-csharp[Access the sequence of members on the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

Diese Quellsequenz enthält alle Member, einschließlich Eigenschaften und Feldern. Filtern Sie die Sequenz daher mit der <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType>-Methode, um die Elemente zu finden, bei denen es sich um <xref:Microsoft.CodeAnalysis.IMethodSymbol?displayProperty=nameWithType>-Objekte handelt:

[!code-csharp[Filter the sequence to only methods](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

Danach fügen Sie einen weiteren Filter hinzu, um nur die Methoden zurückzugeben, die öffentlich sind und eine `string` zurückgeben:

[!code-csharp[Filter on return type and accessibility](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

Wählen Sie nur die name-Eigenschaft und nur eindeutige Namen aus, indem Sie alle Überladungen entfernen:

[!code-csharp[find the distinct names.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

Sie können auch mithilfe der LINQ-Abfragesyntax die vollständige Abfrage erstellen und dann alle Methodennamen in der Konsole anzeigen:

[!code-csharp[build and display the results of this query.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#13 "Build and display the results of the query.")]

Kompilieren Sie das Programm, und führen Sie es aus. Die folgende Ausgabe wird angezeigt:

```output
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```

Sie haben die Semantik-API verwendet, um Informationen zu den Symbolen zu finden und anzuzeigen, die zu diesem Programm gehören.
