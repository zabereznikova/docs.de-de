---
title: Erste Schritte mit der Syntaxtransformation (Roslyn-APIs)
description: Eine Einführung in das Durchlaufen, Abfragen und schrittweise Durchlaufen von Syntaxstrukturen.
ms.date: 06/01/2018
ms.custom: mvc
ms.openlocfilehash: 5879dfd6ed0a5f6465829eec496d10cfcfd07362
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202124"
---
# <a name="get-started-with-syntax-transformation"></a>Erste Schritte mit der Syntaxtransformation

Dieses Tutorial baut auf Konzepten und Methoden auf, die in den Schnellstarts [Erste Schritte mit der Syntaxanalyse](syntax-analysis.md) und [Erste Schritte mit der semantischen Analyse](semantic-analysis.md) erläutert werden. Wenn nicht bereits geschehen, sollten Sie diese Schnellstarts durchlaufen, bevor Sie mit diesem beginnen.

In diesem Schnellstart erforschen Sie Methoden zum Erstellen und Transformieren von Syntaxstrukturen. In Kombination mit den Methoden, die Sie in früheren Schnellstarts gelernt haben, erstellen Sie Ihr erstes Kommandozeilenrefactoring.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="immutability-and-the-net-compiler-platform"></a>Unveränderlichkeit und die .NET Compiler Platform

**Unveränderlichkeit** ist ein Grundprinzip der .NET Compiler Platform. Unveränderliche Datenstrukturen können nach ihrer Erstellung nicht mehr geändert werden. Sie können von mehreren Consumern gleichzeitig auf sichere Weise genutzt und analysiert werden. Es besteht kein Risiko, dass ein Consumer einen anderen auf unvorhersehbare Weise beeinträchtigt. Für Ihr Analysetool sind keine Sperren oder andere Maßnahmen für die gleichzeitige Verwendung erforderlich. Diese Regel gilt für Syntaxstrukturen, Kompilierungen, Symbole, semantische Modelle und jede andere Datenstruktur. Anstatt bestehende Strukturen zu modifizieren, werden durch APIs neue Objekte basierend auf den angegebenen Unterschieden zu den alten Objekten erstellt. Sie wenden dieses Konzept auf Syntaxstrukturen an, um mithilfe von Transformationen neue Strukturen zu erstellen.

## <a name="create-and-transform-trees"></a>Erstellen und Transformieren von Strukturen

Sie wählen eine von zwei Strategien für Syntaxtransformationen. **Factorymethoden** werden am besten verwendet, wenn Sie nach bestimmten Knoten suchen, die ersetzt werden sollen, oder nach bestimmten Stellen, an denen Sie neuen Code einfügen möchten. **Rewriter** sind am besten geeignet, wenn Sie ein ganzes Projekt nach Codemustern durchsuchen möchten, die Sie ersetzen möchten.

### <a name="create-nodes-with-factory-methods"></a>Erstellen von Knoten mit Factorymethoden

Durch die erste Syntaxtransformation werden die Factorymethoden demonstriert. Sie werden eine `using System.Collections;`-Anweisung durch eine `using System.Collections.Generic;`-Anweisung ersetzen. Dieses Beispiel zeigt, wie Sie <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxNode?displayProperty=nameWithType>-Objekte mit den <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType>-Factorymethoden erstellen. Für jede Art von **Knoten**, **Token** oder **Trivia** gibt es eine Factorymethode, die eine Instanz dieses Typs erstellt. Sie erstellen Syntaxstrukturen, indem Sie Knoten hierarchisch von unten nach oben zusammensetzen. Anschließend transformieren Sie das vorhandene Programm, indem Sie bestehende Knoten durch die neue, von Ihnen erstellte Struktur ersetzen.

Starten Sie Visual Studio, und erstellen Sie ein neues C#-Projekt namens **Stand-Alone Code Analysis Tool**. Wählen Sie in Visual Studio **Datei** > **Neu** > **Projekt** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen. Wählen Sie unter **Visual C#**  > **Erweiterbarkeit** die Option **Stand-Alone Code Analysis Tool** aus. Dieser Schnellstart enthält zwei Beispielprojekte. Nennen Sie daher die Lösung **SyntaxTransformationQuickStart** und das Projekt **ConstructionCS**. Klicken Sie auf **OK**.

Dieses Projekt verwendet die Methoden der Klasse <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType>, um ein <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>-Element zu erstellen, das den `System.Collections.Generic`-Namespace repräsentiert.

Fügen Sie am Anfang der Datei `Program.cs` die folgende using-Direktive hinzu.

[!code-csharp[import the SyntaxFactory class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#StaticUsings "import the Syntax Factory class and the System.Console class")]

Sie werden **Namenssyntaxknoten** erstellen, um die Struktur aufzubauen, die die `using System.Collections.Generic;`-Anweisung repräsentiert. <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax> ist die Basisklasse für vier Typen von Namen, die in C# verwendet werden. Sie setzen diese vier Typen von Namen zusammen, um einen beliebigen Namen zu erstellen, der in der Programmiersprache C# enthalten sein kann:

* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType> steht für einfache einzelne Bezeichner wie `System` und `Microsoft`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.GenericNameSyntax?displayProperty=nameWithType> steht für einen generischen Typ oder Methodennamen wie `List<int>`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax?displayProperty=nameWithType> steht für einen qualifizierten Namen der Form `<left-name>.<right-identifier-or-generic-name>` wie z.B. `System.IO`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.AliasQualifiedNameSyntax?displayProperty=nameWithType> steht für einen Namen unter Verwendung eines externen Assemblyalias wie `LibraryV2::Foo`.

Sie verwenden die <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory.IdentifierName(System.String)>-Methode, um einen <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>-Knoten zu erstellen. Fügen Sie den folgenden Code in Ihrer `Main`-Methode in `Program.cs` hinzu:

[!code-csharp[create the system identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateIdentifierName "Create and display the system name identifier")]

Der vorangehende Code erstellt ein <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax>-Objekt und weist es der Variablen `name` zu. Viele der Roslyn-APIs geben Basisklassen zurück, um die Arbeit mit verwandten Typen zu erleichtern. Die Variable `name`, eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>, kann beim Erstellen von <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax> wiederverwendet werden. Verwenden Sie für das Beispiel keinen Typrückschluss. Sie werden diesen Schritt in diesem Projekt automatisieren.

Sie haben nun den Namen erstellt. Jetzt ist es an der Zeit, die Struktur mit zusätzlichen Knoten zu erweitern, indem Sie ein <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>-Element erstellen. In der neuen Struktur wird `name` als linker Namensteil und ein neues <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax>-Element für den `Collections`-Namespace als rechter Teil von <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax> verwendet. Fügen Sie den folgenden Code zu `program.cs` hinzu:

[!code-csharp[create the collections identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateQualifiedIdentifierName "Build the System.Collections identifier")]

Führen Sie den Code erneut aus, und sehen Sie sich die Ergebnisse an. Sie bauen eine Knotenstruktur auf, die den Code darstellt. Sie werden dieses Muster fortsetzen, um das <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>-Element für den `System.Collections.Generic`-Namespace zu erstellen. Fügen Sie den folgenden Code zu `Program.cs` hinzu:

[!code-csharp[create the full identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateFullNamespace "Build the System.Collections.Generic identifier")]

Starten Sie das Programm erneut, um zu sehen, dass Sie die Struktur für den hinzuzufügenden Code erstellt haben.

### <a name="create-a-modified-tree"></a>Erstellen einer geänderten Struktur

Sie haben eine kleine Syntaxstruktur aufgebaut, die eine Anweisung enthält. Die APIs zum Erstellen neuer Knoten sind die richtige Wahl, um einzelne Anweisungen oder andere kleine Codeblöcke zu erstellen. Um jedoch größere Codeblöcke zu erstellen, sollten Sie Methoden verwenden, die Knoten ersetzen oder Knoten in eine bestehende Struktur einfügen. Denken Sie daran, dass Syntaxstrukturen unveränderlich sind. Die **Syntax-API** bietet keinen Mechanismus, um eine bestehende Syntaxstruktur nach deren Aufbau zu ändern. Stattdessen stellt sie Methoden zur Verfügung, die neue Strukturen auf der Grundlage von Änderungen an bestehenden Strukturen erzeugen. `With*`-Methoden werden in konkreten Klassen definiert, die von <xref:Microsoft.CodeAnalysis.SyntaxNode> abgeleitet sind, oder in Erweiterungsmethoden, die in der Klasse <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions> deklariert sind. Diese Methoden erstellen einen neuen Knoten, indem sie Änderungen an den untergeordneten Eigenschaften eines vorhandenen Knotens vornehmen. Zusätzlich kann die <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A>-Erweiterungsmethode verwendet werden, um einen untergeordneten Knoten in einer Teilstruktur zu ersetzen. Diese Methode aktualisiert auch das übergeordnete Element, sodass dieses auf das neu erstellte untergeordnete Element zeigt. Die Methode wiederholt diesen Prozess für die gesamte Struktur – dies ist auch als _Umlaufen_ der Struktur bekannt.

Der nächste Schritt besteht darin, eine Struktur zu erstellen, die ein ganzes (kleines) Programm darstellt, und diese dann zu ändern. Fügen Sie den folgenden Code am Anfang der `Program`-Klasse hinzu:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#DeclareSampleCode "Create a tree that represents a small program")]

> [!NOTE]
> Der Beispielcode verwendet den `System.Collections`-Namespace und nicht den `System.Collections.Generic`-Namespace.

Als Nächstes fügen Sie den folgenden Code am Ende der `Main`-Methode hinzu, um den Text zu analysieren und eine Struktur zu erstellen:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateParseTree "Create a tree that represents a small program")]

In diesem Beispiel wird die <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)?displayProperty=NameWithType>-Methode verwendet, um den Namen in einem <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax>-Knoten durch den im vorangehenden Code konstruierten zu ersetzen.

Erstellen Sie einen neuen <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax>-Knoten mit der <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)>-Methode, um den `System.Collections`-Namen mit dem Namen zu aktualisieren, den Sie im vorangehenden Code erstellt haben. Fügen Sie den folgenden Code am Ende der `Main`-Methode hinzu:

[!code-csharp[create a new subtree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#BuildNewUsing "Create the subtree with the replaced namespace")]

Starten Sie das Programm, und schauen Sie sich die Ausgabe genau an. Das `newusing`-Element wurde nicht in der Stammstruktur platziert. Die ursprüngliche Struktur wurde nicht geändert.

Fügen Sie den folgenden Code mit der <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A>-Erweiterungsmethode hinzu, um eine neuen Struktur zu erstellen. Die neue Struktur hat sich durch das Ersetzen des bestehenden Imports durch den aktualisierten `newUsing`-Knoten ergeben. Sie weisen diese neue Struktur der vorhandenen `root`-Variablen zu:

[!code-csharp[create a new root tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#TransformTree "Create the transformed root tree with the replaced namespace")]

Führen Sie das Programm erneut aus. Diesmal wird der `System.Collections.Generic`-Namespace korrekt in die Struktur importiert.

### <a name="transform-trees-using-syntaxrewriters"></a>Transformieren von Strukturen mit `SyntaxRewriters`

Die Methoden `With*` und <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> bieten komfortable Möglichkeiten, einzelne Branches einer Syntaxstruktur zu transformieren. Die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType>-Klasse führt mehrere Transformationen in einer Syntaxstruktur durch. Bei der <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType>-Klasse handelt es sich um eine Unterklasse von <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor%601?displayProperty=nameWithType>. Der <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> wendet eine Transformation auf einen bestimmten Typ von <xref:Microsoft.CodeAnalysis.SyntaxNode> an. Sie können Transformationen auf mehrere Typen von <xref:Microsoft.CodeAnalysis.SyntaxNode>-Objekten anwenden, unabhängig von deren Stelle in der Syntaxstruktur. Beim zweiten Projekt in diesem Schnellstart erstellen Sie ein Kommandozeilenrefactoring, das explizite Typen in lokalen Variablendeklarationen überall dort entfernt, wo Typrückschlüsse verwendet werden könnten.

Erstellen Sie ein neues C#-Projekt namens **Stand-Alone Code Analysis Tool**. Klicken Sie in Visual Studio mit der rechten Maustaste auf den Lösungsknoten `SyntaxTransformationQuickStart`. Wählen Sie **Hinzufügen** > **Neues Projekt**, um das Dialogfeld **Neues Projekt** anzuzeigen. Wählen Sie unter **Visual C#**  > **Erweiterbarkeit** die Option **Stand-Alone Code Analysis Tool** aus. Nennen Sie Ihr Projekt `TransformationCS`, und klicken Sie auf „OK“.

Der erste Schritt besteht in der Erstellung einer Klasse, die von <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> abgeleitet ist, um Ihre Transformationen durchzuführen. Fügen Sie zum Projekt eine neue Klassendatei hinzu. Wählen Sie in Visual Studio **Projekt** > **Klasse hinzufügen...** aus. Geben Sie im Dialogfeld **Neues Element hinzufügen**`TypeInferenceRewriter.cs` als Dateinamen ein.

Fügen Sie der Datei `TypeInferenceRewriter.cs` die folgenden using-Anweisungen hinzu:

[!code-csharp[add necessary usings](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#AddUsings "Add required usings")]

Als Nächstes nutzen Sie die `TypeInferenceRewriter`-Klasse zur Erweiterung der <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter>-Klasse:

[!code-csharp[add base class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BaseClass "Add base class")]

Fügen Sie den folgenden Code hinzu, um ein privates schreibgeschütztes Feld mit einem <xref:Microsoft.CodeAnalysis.SemanticModel>-Element zu deklarieren, und initialisieren Sie es im Konstruktor. Sie werden dieses Feld später benötigen, um zu bestimmen, wo ein Typrückschluss verwendet werden kann:

[!code-csharp[initialize members](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Construction "Declare and initialize member variables")]

Überschreiben Sie die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)>-Methode:

```csharp
public override SyntaxNode VisitLocalDeclarationStatement(LocalDeclarationStatementSyntax node)
{

}
```

> [!NOTE]
> Viele der Roslyn-APIs deklarieren Rückgabetypen, die Basisklassen der tatsächlich zurückgegebenen Runtimetypen sind. In vielen Szenarien kann eine Art von Knoten vollständig durch eine andere Art von Knoten ersetzt werden. Manchmal ist es sogar möglich, eine Art von Knoten zu entfernen. In diesem Beispiel gibt die <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)>-Methode, anstelle des abgeleiteten Typs von <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, ein <xref:Microsoft.CodeAnalysis.SyntaxNode>-Element zurück. Dieser Rewriter gibt einen neuen <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>-Knoten zurück, der auf dem vorhandenen Knoten basiert.

In diesem Schnellstart werden lokale Variablendeklarationen behandelt. Die diesbezüglichen Informationen können Sie auch für andere Deklarationen wie `foreach`-Schleifen, `for`-Schleifen, LINQ-Ausdrücke und Lambdaausdrücke nutzen. Außerdem transformiert der hier gezeigte Rewriter nur Deklarationen der einfachsten Form:

```csharp
Type variable = expression;
```

Wenn Sie selbst die verschiedenen Möglichkeiten erkunden möchten, ist es empfehlenswert, das fertig gestellte Beispiel für diese Typen von Variablendeklarationen einfach zu erweitern:

```csharp
// Multiple variables in a single declaration.
Type variable1 = expression1,
     variable2 = expression2;
// No initializer.
Type variable;
```

Fügen Sie den folgenden Code zum Text der `VisitLocalDeclarationStatement`-Methode hinzu, um das Umschreiben dieser Deklarationsformen zu überspringen:

[!code-csharp[exclude other declarations](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Exclusions "Exclude variables declarations not processed by this sample")]

Die Methode gibt an, dass kein Umschreiben stattfindet, indem der Parameter `node` unverändert zurückgegeben wird. Wenn keiner dieser `if`-Ausdrücke „TRUE“ ist, stellt der Knoten eine mögliche Deklaration mit Initialisierung dar. Fügen Sie diese Anweisungen hinzu, um den in der Deklaration angegebenen Typnamen zu extrahieren, und binden Sie ihn mit dem <xref:Microsoft.CodeAnalysis.SemanticModel>-Feld, um ein Typsymbol zu erhalten:

[!code-csharp[extract type name](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ExtractTypeSymbol "Extract the type name specified by the declaration")]

Fügen Sie nun diese Anweisung hinzu, um den Initialisierungsausdruck zu binden:

[!code-csharp[bind initializer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BindInitializer "Bind the initializer expressions")]

Abschließend fügen Sie die folgende `if`-Anweisung hinzu, um den vorhandenen Typnamen durch das Schlüsselwort `var` zu ersetzen, wenn der Typ des Initialisierungsausdrucks dem angegebenen Typ entspricht:

[!code-csharp[ReplaceNode](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ReplaceNode "Replace the initializer node")]

Die Bedingung ist erforderlich, da die Deklaration den Initialisierungsausdruck in eine Basisklasse oder eine Schnittstelle umwandeln kann. Wenn das gewünscht wird, stimmen die Typen auf der linken und rechten Seite der Zuweisung nicht überein. Das Entfernen des expliziten Typs würde in diesen Fällen die Semantik eines Programms verändern. `var` wird als Bezeichner und nicht als Schlüsselwort angegeben, da `var` ein kontextbezogenes Schlüsselwort ist. Die führenden und nachgestellten Trivia (Leerzeichen) werden vom alten Typnamen in das Schlüsselwort `var` übertragen, um vertikale Leerzeichen und Einrückungen beizubehalten. Es ist einfacher, `ReplaceNode` anstelle von `With*` für die Transformation der <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> zu verwenden, da der Typname eigentlich ein untergeordnetes Element der zweiten Ebene der Deklarationsanweisung ist.

Sie haben den `TypeInferenceRewriter` abgeschlossen. Kehren Sie nun zu Ihrer `Program.cs`-Datei zurück, um das Beispiel fertig zu stellen. Erstellen Sie einen <xref:Microsoft.CodeAnalysis.Compilation>-Test, und rufen Sie daraus das <xref:Microsoft.CodeAnalysis.SemanticModel> ab. Verwenden Sie dieses <xref:Microsoft.CodeAnalysis.SemanticModel>, um Ihren `TypeInferenceRewriter` auszuprobieren. Diesen Schritt führen Sie zuletzt aus. In der Zwischenzeit deklarieren Sie eine Platzhaltervariable, die Ihre Testkompilierung repräsentiert:

[!code-csharp[DeclareCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#DeclareTestCompilation "Declare the test compilation")]

Nach einer kurzen Unterbrechung sollten Sie eine Wellenlinie für einen Fehler sehen, die darauf hinweist, dass die `CreateTestCompilation`-Methode nicht vorhanden ist. Drücken Sie **Strg+Punkt**, um die Glühbirnenmeldung zu öffnen, und drücken Sie dann die EINGABETASTE, um den Befehl **Methodenstub generieren** aufzurufen. Dieser Befehl erzeugt einen Methodenstub für die `CreateTestCompilation`-Methode in der `Program`-Klasse. Sie werden diese Methode zu einem späteren Zeitpunkt ausfüllen:

![Generieren einer Methode aus der Verwendung in C#](./media/syntax-transformation/generate-from-usage.png)

Schreiben Sie den folgenden Code, um jede <xref:Microsoft.CodeAnalysis.SyntaxTree>-Klasse im <xref:Microsoft.CodeAnalysis.Compilation>-Test zu durchlaufen. Initialisieren Sie für jeden einen neuen `TypeInferenceRewriter` mit dem <xref:Microsoft.CodeAnalysis.SemanticModel> für diese Struktur:

[!code-csharp[IterateTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#IterateTrees "Iterate all the source trees in the test compilation")]

Fügen Sie innerhalb der von Ihnen erstellten `foreach`-Anweisung den folgenden Code hinzu, um die Transformation für jede Quellstruktur durchzuführen. Dieser Code schreibt die neu transformierte Struktur bedingt aus, falls Änderungen vorgenommen wurden. Ihr Rewriter sollte eine Struktur nur dann ändern, wenn er auf eine oder mehrere lokale Variablendeklarationen stößt, die durch einen Typrückschluss vereinfacht werden könnten:

[!code-csharp[TransformTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#TransformTrees "Transform and save any trees that are modified by the rewriter")]

Der Code `File.WriteAllText` sollte mit einer Wellenlinie unterstrichen sein. Wählen Sie die Glühbirne aus, und fügen Sie die erforderliche `using System.IO;`-Anweisung hinzu.

Sie haben es fast geschafft! Es gibt noch einen Schritt: das Erstellen eines <xref:Microsoft.CodeAnalysis.Compilation>-Tests. Da Sie bei diesem Schnellstart überhaupt keinen Typrückschluss verwendet haben, wäre das ein perfekter Testfall gewesen. Leider würde das Erstellen einer Kompilierung aus einer C#-Projektdatei außerhalb des Rahmens dieser exemplarischen Vorgehensweise liegen. Aber glücklicherweise gibt es, wenn Sie die Anweisungen genau befolgt haben, auch eine gute Nachricht. Ersetzen Sie den Inhalt der `CreateTestCompilation`-Methode durch folgenden Code. Es wird eine Testkompilierung erstellt, die zufällig mit dem in diesem Schnellstart beschriebenen Projekt übereinstimmt:

[!code-csharp[CreateTestCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#CreateTestCompilation "Create a test compilation using the code written for this quickstart.")]

Drücken Sie die Daumen, und führen Sie das Projekt aus. Wählen Sie in Visual Studio **Debuggen** > **Debugging starten**. Visual Studio informiert Sie darüber, dass sich die Dateien in Ihrem Projekt geändert haben. Klicken Sie auf „**Ja, alle**“, um die geänderten Dateien neu zu laden. Schauen Sie sich Ihr Werk etwas genauer an. Beachten Sie, wie viel sauberer der Code ohne all diese expliziten und redundanten Typspezifizierer aussieht.

Herzlichen Glückwunsch! Sie haben die **Compiler-APIs** verwendet, um Ihr eigenes Refactoring zu schreiben, das alle Dateien in einem C#-Projekt nach bestimmten syntaktischen Mustern durchsucht, die Semantik des Quellcodes in Übereinstimmung mit diesen Mustern analysiert und diese transformiert. Sie sind jetzt offiziell Refactoringautor!
