---
title: Erste Schritte mit der Syntaxanalyse (Roslyn-APIs)
description: Eine Einführung in das Durchlaufen, Abfragen und schrittweise Durchlaufen von Syntaxstrukturen.
ms.date: 02/05/2018
ms.custom: mvc
ms.openlocfilehash: 22d1303c9daa2ae35cf130b0c857cd7a5efdbe76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240517"
---
# <a name="get-started-with-syntax-analysis"></a>Erste Schritte mit der Syntaxanalyse

In diesem Tutorial lernen Sie die **Syntax-API** kennen. Die Syntax-API bietet Zugriff auf die Datenstrukturen, die ein C#- oder Visual Basic-Programm beschreiben. Diese Datenstrukturen sind so detailliert, dass sie ein Programm jeder Größe vollständig darstellen können. Diese Strukturen können komplette Programme beschreiben, die sich fehlerfrei kompilieren und ausführen lassen. Sie können auch unvollständige Programme beschreiben, während Sie diese im Editor schreiben.

Um diese umfangreiche Ausdrucksmöglichkeit zu unterstützen, müssen die Datenstrukturen und APIs, aus denen die Syntax-API besteht, notwendigerweise komplex sein. Als Einstieg sehen wir uns die Datenstruktur für ein typisches Hello World-Programm an:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Sehen Sie sich den Text des oben stehenden Programms an. Sie werden bekannte Elemente erkennen. Der gesamte Text repräsentiert eine einzelne Quelldatei, eine **Kompilierungseinheit**. Die ersten drei Zeilen dieser Quelldatei sind **using-Direktiven**. Der Rest der Quelle ist in einer **Namespacedeklaration** enthalten. Die Namespacedeklaration enthält eine untergeordnete **Klassendeklaration**. Die Klassendeklaration enthält eine **Methodendeklaration**.

Die Syntax-API erstellt eine Baumstruktur, deren Stamm die Kompilierungseinheit repräsentiert. Knoten in der Struktur repräsentieren die using-Direktiven, die Namespacedeklaration und alle anderen Elemente des Programms. Die Baumstruktur setzt sich bis zur untersten Ebene fort: Die Zeichenfolge „Hello World!“ ist ein **Token für ein Zeichenfolgenliteral**, das eine Ableitung eines **Arguments** ist. Die Syntax-API bietet Zugriff auf die Struktur des Programms. Sie können Abfragen nach bestimmten Codemethoden erstellen, die gesamte Struktur schrittweise durchlaufen, um den Code zu verstehen und durch Modifizieren der vorhandenen Struktur neue Strukturen erstellen.

Diese kurze Beschreibung bietet einen Überblick über die Art der Informationen, auf die Sie mithilfe der Syntax-API zugreifen können. Die Syntax-API ist nichts anderes als eine formale API, die die vertrauten Codekonstrukte beschreibt, die Sie aus C# kennen. Sie bietet Informationen zur Formatierung des Codes, z.B. zu Zeilenumbrüchen, Leerräumen und Einzügen. Mit diesen Informationen können Sie den Code genau so darstellen, wie er von Programmierern oder dem Compiler geschrieben und gelesen wird. Dank dieser Struktur gewinnt der Quellcode eine ganz neue Bedeutungsebene, auf der Sie interagieren können. Sie sehen nicht nur Zeichenfolgen, sondern Daten, die die Struktur eines C#-Programms repräsentieren.

Installieren Sie zunächst das **SDK für die .NET Compiler Platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-syntax-trees"></a>Grundlegendes zu Syntaxstrukturen

Verwenden Sie die Syntax-API zur Analyse der Struktur von C#-Code. Die **Syntax-API** stellt die Parser, die Syntaxstrukturen und die Hilfsprogramme zur Verfügung, die Sie zum Analysieren und Konstruieren von Syntaxstrukturen benötigen. So können Sie im Code nach bestimmten Syntaxelementen suchen oder den Code für ein Programm lesen.

Eine Syntaxstruktur ist eine Datenstruktur, die von den C#- und Visual Basic-Compilern verwendet wird, um C#- und Visual Basic-Programme zu verstehen. Syntaxstrukturen werden durch denselben Parser erzeugt, der ausgeführt wird, wenn ein Projekt erstellt wird oder ein Entwickler die Taste F5 drückt. Die Syntaxstrukturen weisen vollständige Datentreue mit der Sprache auf; jedes Informationselement in einer Codedatei wird in der Struktur dargestellt. Das Schreiben einer Syntaxstruktur als Text reproduziert exakt den ursprünglichen Text, der analysiert wurde. Syntaxstrukturen sind zudem **unveränderlich** – nach dem Erstellen kann eine Syntaxstruktur nicht mehr geändert werden. Consumer der Strukturen können die Strukturen ohne Sperren oder andere Parallelitätsmaßnahmen in mehreren Threads analysieren, weil sie wissen, dass sich die Daten niemals ändern. Sie können APIs verwenden, um neue Strukturen zu erstellen, die durch Modifizieren einer vorhandenen Struktur entstehen.

Syntaxstrukturen bestehen aus den folgenden vier primären Bausteinen:

* Die <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>-Klasse: Eine Instanz dieser Klasse repräsentiert eine vollständige Analysestruktur. <xref:Microsoft.CodeAnalysis.SyntaxTree> ist eine abstrakte Klasse mit sprachspezifischen Ableitungen. Sie verwenden die Analysemethoden der Klasse <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType> (oder <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType>), um Text in C# oder Visual Basic zu analysieren.
* Die <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>-Klasse: Instanzen dieser Klasse repräsentieren syntaktische Konstrukte wie Deklarationen, Anweisungen, Klauseln und Ausdrücke.
* Die <xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType>-Struktur: Diese Struktur repräsentiert ein einzelnes Schlüsselwort oder Interpunktionszeichen oder einen einzelnen Bezeichner oder Operator.
* Die <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType>-Struktur: Diese Struktur repräsentiert syntaktisch unwichtige Informationen wie Leerräume zwischen Token, Vorverarbeitungsdirektiven und Kommentare.

Trivia, Token und Knoten werden hierarchisch zusammengestellt und bilden eine Struktur, die alle Elemente in einem Visual Basic- oder C#-Codefragment vollständig repräsentiert. Sie können diese Struktur im Fenster **Syntaxschnellansicht** anzeigen. Wählen Sie in Visual Studio **Ansicht** > **Weitere Fenster** > **Syntaxschnellansicht** aus. Die oben gezeigte C#-Quelldatei sieht in der **Syntaxschnellansicht** ungefähr wie folgt aus:

**SyntaxNode**: Blau | **SyntaxToken**: Grün | **SyntaxTrivia**: Rot ![C#-Codedatei](media/walkthrough-csharp-syntax-figure1.png)

Durch Navigieren in dieser Struktur lässt sich jede Anweisung, jeder Ausdruck, jedes Token und jeder Leerraum in einer Codedatei auffinden.

Sie können zwar in einer Codedatei mithilfe der Syntax-APIs alles finden, in den meisten Szenarien müssen Sie jedoch kleine Codeausschnitte untersuchen oder nach bestimmten Anweisungen oder Fragmenten suchen. Die beiden folgenden Beispiele zeigen typische Vorgehensweisen beim Durchsuchen der Codestruktur oder beim Suchen nach einzelnen Anweisungen.

## <a name="traversing-trees"></a>Durchlaufen von Strukturen

Sie können die Knoten in einer Syntaxstruktur auf zwei Arten untersuchen. Sie können die Struktur durchlaufen und jeden einzelnen Knoten untersuchen oder Abfragen für bestimmte Elemente oder Knoten ausführen.

### <a name="manual-traversal"></a>Manuelles Durchlaufen

Den fertig gestellten Code für dieses Beispiel finden Sie in [unserem GitHub-Repository](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart).

> [!NOTE]
> Die Syntaxstrukturtypen verwenden Vererbung, um die verschiedenen Syntaxelemente zu beschreiben, die an verschiedenen Positionen im Programm gültig sind. Bei der Verwendung dieser APIs müssen häufig Eigenschaften oder Sammlungsmember in bestimmte abgeleitete Typen umgewandelt werden. In den folgenden Beispielen sind die Zuweisung und die Umwandlung separate Anweisungen, bei denen explizit typisierte Variablen verwendet werden. Sie können den Code lesen, um die Rückgabetypen der API und den Laufzeittyp der zurückgegebenen Objekte zu sehen. In der Praxis ist es eher üblich, implizit typisierte Variablen zu verwenden und die Typen der zu untersuchenden Objekte mithilfe von API-Namen zu beschreiben.

Erstellen Sie ein neues **Stand-Alone Code Analysis Tool**-Projekt für C#:

* Wählen Sie in Visual Studio **Datei** > **Neu** > **Projekt** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.
* Wählen Sie unter **Visual C#**  > **Erweiterbarkeit** die Option **Stand-Alone Code Analysis Tool** aus.
* Nennen Sie Ihr Projekt **SyntaxTreeManualTraversal**, und klicken Sie auf „OK“.

Sie werden das einfache Hello World!- Programm analysieren, das weiter oben in diesem Artikel gezeigt wurde.
Fügen Sie den Text für das Hello World-Programm als Konstante in Ihre `Program`-Klasse ein:

[!code-csharp[Declare the program text](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#1 "Declare a constant string for the program text to analyze")]

Anschließend fügen Sie den folgenden Code hinzu, um die **Syntaxstruktur** für den Codetext in der `programText`-Konstante zu erstellen.  Fügen Sie Ihrer `Main`-Methode die folgende Zeile hinzu:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#2 "Create the syntax tree")]

Diese beiden Zeilen erstellen die Struktur und rufen den Stammknoten dieser Struktur ab. Jetzt können Sie die Knoten in der Struktur untersuchen. Fügen Sie diese Zeilen zu Ihrer `Main`-Methode hinzu, um einige der Eigenschaften des Stammknotens in der Struktur anzuzeigen:

[!code-csharp[Examine the root node](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#3 "Examine the root node")]

Führen Sie die Anwendung aus, um festzustellen, was Ihr Code in Zusammenhang mit dem Stammknoten in dieser Struktur erkannt hat.

In der Regel würden Sie die Struktur durchlaufen, um mehr über den Code zu erfahren. In diesem Beispiel analysieren Sie bekannten Code, um die APIs zu erkunden. Fügen Sie folgenden Code hinzu, um den ersten Member des `root`-Knotens zu untersuchen:

[!code-csharp[Find the first member](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#4 "Find the first member")]

Dieser Member ist eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType>. Er repräsentiert alle Elemente im Bereich der `namespace HelloWorld`-Deklaration. Fügen Sie folgenden Code hinzu, um zu ermitteln, welche Knoten im `HelloWorld`-Namespace deklariert sind:

[!code-csharp[Find the class declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#5 "Find the class declaration")]

Führen Sie das Programm aus, um das Ergebnis anzuzeigen.

Da Sie jetzt wissen, dass die Deklaration eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType> ist, deklarieren Sie eine neue Variable dieses Typs, um die Klassendeklaration zu untersuchen. Diese Klasse enthält nur einen Member: die `Main`-Methode. Fügen Sie folgenden Code hinzu, um die `Main`-Methode zu suchen und in eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType> umzuwandeln.

[!code-csharp[Find the main declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#6 "Find the main declaration")]

Der Knoten mit der Methodendeklaration enthält alle syntaktischen Informationen zu der Methode. Jetzt zeigen wir den Rückgabetyp der `Main`-Methode, die Anzahl und Typen der Argumente und den Textkörper der Methode an. Fügen Sie den folgenden Code hinzu:

[!code-csharp[Examine the syntax of the main method](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#7 "Display information about the main method")]

Führen Sie das Programm aus, um alle Informationen anzuzeigen, die Sie zu diesem Programm ermittelt haben:

```text
The tree is a CompilationUnit node.
The tree has 1 elements in it.
The tree has 4 using statements. They are:
        System
        System.Collections
        System.Linq
        System.Text
The first member is a NamespaceDeclaration.
There are 1 members declared in this namespace.
The first member is a ClassDeclaration.
There are 1 members declared in the Program class.
The first member is a MethodDeclaration.
The return type of the Main method is void.
The method has 1 parameters.
The type of the args parameter is string[].
The body text of the Main method follows:
        {
            Console.WriteLine("Hello, World!");
        }
```

### <a name="query-methods"></a>Abfragemethoden

Zusätzlich zum Durchlaufen von Strukturen können Sie die Syntaxstruktur auch mithilfe der in <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType> definierten Abfragemethoden untersuchen. Diese Methoden werden Ihnen vertraut vorkommen, wenn Sie XPath kennen. Sie können diese Methoden mit LINQ verwenden, um Elemente in einer Struktur schnell zu finden. <xref:Microsoft.CodeAnalysis.SyntaxNode> weist Abfragemethoden wie z.B. <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> und <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A> auf.

Sie können diese Abfragemethoden verwenden, um anstelle des Navigierens in der Struktur das Argument für die `Main`-Methode zu suchen. Fügen Sie am Ende Ihrer `Main`-Methode folgenden Code hinzu:

[!code-csharp[Query the tree for the arguments to Main](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#8 "Query the tree for the arguments to Main")]

Die erste Anweisung verwendet einen LINQ-Ausdruck und die <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>-Methode, um denselben Parameter zu suchen wie im vorherigen Beispiel.

Führen Sie das Programm aus, und Sie werden feststellen, dass der LINQ-Ausdruck denselben Parameter gefunden hat wie beim manuellen Navigieren durch die Struktur.

Das Beispiel verwendet `WriteLine`-Anweisungen, um während des Durchlaufens Informationen zu den Syntaxstrukturen anzuzeigen. Sie erhalten auch mehr Informationen, wenn Sie das fertig gestellte Programm im Debugger ausführen. Sie können die Eigenschaften und Methoden, die zu der für das Hello World-Programm erstellten Syntaxstruktur gehören, genauer untersuchen.

## <a name="syntax-walkers"></a>Syntaxwalker

Es gibt häufig Situationen, in denen Sie in einer Syntaxstruktur alle Knoten eines bestimmten Typs finden möchten, z.B. jede Eigenschaftendeklaration in einer Datei. Indem Sie die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType>-Klasse erweitern und die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)>-Methode überschreiben, können Sie jede Eigenschaftendeklaration in einer Syntaxstruktur verarbeiten, ohne die Struktur vorher kennen zu müssen. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> ist eine bestimmte Art von <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor>, der rekursiv einen Knoten und jedes seiner untergeordneten Elemente besucht.

Dieses Beispiel implementiert einen <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>, der eine Syntaxstruktur untersucht. Gefundene `using`-Direktiven, die keinen `System`-Namespace importieren, werden gesammelt.

Erstellen Sie ein neues **Stand-Alone Code Analysis Tool**-Projekt für C#, und nennen Sie es **SyntaxWalker**.

Den fertig gestellten Code für dieses Beispiel finden Sie in [unserem GitHub-Repository](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart). Das Beispiel in GitHub enthält beide in diesem Tutorial beschriebenen Projekte.

Wie im vorherigen Beispiel können Sie eine Zeichenfolgenkonstante definieren, die den Text des Programms enthält, das Sie analysieren möchten:

[!code-csharp[Define the code text to analyzer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#1 "Define the program text to analyze")]

Dieser Quelltext enthält `using`-Direktiven, die an vier Stellen verteilt sind: auf Dateiebene, im Namespace der obersten Ebene und in den beiden geschachtelten Namespaces. Dieses Beispiel zeigt ein grundlegendes Szenario für die Verwendung der <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>-Klasse zum Abfragen von Code. Es wäre sehr umständlich, jeden Knoten in der Stammsyntaxstruktur besuchen zu müssen, um using-Deklarationen zu finden. Stattdessen erstellen Sie eine abgeleitete Klasse und überschreiben die Methoden, die nur aufgerufen werden, denn der aktuelle Knoten in der Struktur eine using-Direktive ist. Ihr Besucher führt keine Aktionen für einen andern Knotentyp aus. Diese Einzelmethode untersucht jede der `using`-Anweisungen und erstellt eine Sammlung der Namespaces, die sich nicht im `System`-Namespace befinden. Sie erstellen einen <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>, der alle `using`-Anweisungen untersucht, und zwar nur die `using`-Anweisungen.

Nachdem Sie den Programmtext definieren haben, müssen Sie eine `SyntaxTree` erstellen und das Stammelement dieser Struktur abrufen:

[!code-csharp[Create the Syntax tree and access the root](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#2 "Create the Syntax tree and access the root node.")]

Erstellen Sie als Nächstes eine neue Klasse. Wählen Sie in Visual Studio **Projekt** > **Neues Element hinzufügen** aus. Geben Sie im Dialogfeld **Neues Element hinzufügen** den Namen *UsingCollector.cs* als Dateinamen ein.

Sie implementieren die `using`-Besucherfunktionalität in der `UsingCollector`-Klasse. Beginnen Sie, indem Sie die `UsingCollector`-Klasse aus <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> ableiten.

[!code-csharp[Declare the base class for the using collector](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#3 "Declare the base class for the UsingCollector")]

Sie benötigen Speicherplatz, um die gesammelten Namespaceknoten zu speichern.  Deklarieren Sie eine öffentliche schreibgeschützte Eigenschaft in der `UsingCollector`-Klasse, und verwenden Sie diese Variable, um die gefundenen <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax>-Knoten zu speichern:

[!code-csharp[Declare storage for the using syntax nodes](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#4 "Declare storage for the using syntax nodes")]

Die Basisklasse <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> implementiert die Logik, gemäß der jeder Knoten in der Syntaxstruktur besucht wird. Die abgeleitete Klasse überschreibt die Methoden, die für die Knoten aufgerufen werden, für die Sie sich interessieren. In diesem Fall gilt Ihr Interesse allen `using`-Direktiven. Das bedeutet, dass Sie die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>-Methode überschreiben müssen. Das einzige Argument in dieser Methode ist ein <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType>-Objekt. Das ist ein wichtiger Vorteil gegenüber der Verwendung der Besucher: Diese rufen die überschriebenen Methoden mit Argumenten auf, die bereits in den bestimmten Knotentyp umgewandelt wurden. Die <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType>-Klasse weist eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name>-Eigenschaft auf, die den Namen des zu importierenden Namespace speichert. Es handelt sich um eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>. Fügen Sie folgenden Code in die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>-Überschreibung ein:

[!code-csharp[Examine using nodes for the System namespace](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#5 "Examine all using nodes for the System namespace.")]

Wie beim oben aufgeführten Beispiel haben Sie eine Vielzahl von `WriteLine`-Anweisungen hinzugefügt, die dabei helfen, diese Methode zu verstehen. Sie sehen, wann die Methode aufgerufen wird und welche Argumente bei jedem Aufruf an die Methode übergeben werden.

Zum Schluss müssen Sie zwei Codezeilen hinzufügen, um den `UsingCollector` zu erstellen und dafür zu sorgen, dass dieser den Stammknoten besucht und alle `using`-Anweisungen sammelt. Fügen Sie dann eine `foreach`-Schleife ein, um alle `using`-Anweisungen anzuzeigen, die der Collector gefunden hat:

[!code-csharp[Create the UsingCollector and visit the root node.](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#6 "Create the UsingCollector and visit the root node.")]

Kompilieren Sie das Projekt, und führen Sie es aus. Die folgende Ausgabe wird angezeigt:

```console
        VisitUsingDirective called with System.
        VisitUsingDirective called with System.Collections.Generic.
        VisitUsingDirective called with System.Linq.
        VisitUsingDirective called with System.Text.
        VisitUsingDirective called with Microsoft.CodeAnalysis.
                Success. Adding Microsoft.CodeAnalysis.
        VisitUsingDirective called with Microsoft.CodeAnalysis.CSharp.
                Success. Adding Microsoft.CodeAnalysis.CSharp.
        VisitUsingDirective called with Microsoft.
                Success. Adding Microsoft.
        VisitUsingDirective called with System.ComponentModel.
        VisitUsingDirective called with Microsoft.Win32.
                Success. Adding Microsoft.Win32.
        VisitUsingDirective called with System.Runtime.InteropServices.
        VisitUsingDirective called with System.CodeDom.
        VisitUsingDirective called with Microsoft.CSharp.
                Success. Adding Microsoft.CSharp.
Microsoft.CodeAnalysis
Microsoft.CodeAnalysis.CSharp
Microsoft
Microsoft.Win32
Microsoft.CSharp
Press any key to continue . . .
```

Herzlichen Glückwunsch! Sie haben die **Syntax-API** verwendet, um bestimmte Arten von C#-Anweisungen und -Deklarationen in C#-Quellcode zu ermitteln.
