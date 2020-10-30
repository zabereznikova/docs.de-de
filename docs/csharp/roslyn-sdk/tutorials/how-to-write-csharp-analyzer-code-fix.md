---
title: 'Tutorial: Schreiben Ihres ersten Analysetools und Codefixes'
description: Dieses Tutorial enthält Schritt-für-Schritt-Anleitungen zum Erstellen eines Analysetools und eines Codefixes mithilfe des .NET Compiler SDK (Roslyn-APIs).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: 33c00e90d768021e36a7987be0ddd7daec4cfcec
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224041"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a>Tutorial: Schreiben Ihres ersten Analysetools und Codefixes

Das .NET Compiler Platform SDK stellt die Tools zur Verfügung, die Sie zum Erstellen von benutzerdefinierten Warnungen mit C#- oder Visual Basic-Code als Ziel benötigen. Ihr **Analysetool** enthält Code, der Verstöße gegen Ihre Regel erkennt. Ihr **Codefix** enthält den Code, der den Verstoß behebt. Die Regeln, die Sie implementieren, können sich auf alles Mögliche beziehen, von der Codestruktur über das Codeformat bis zu Benennungskonventionen usw. Die .NET Compiler Platform stellt das Framework zum Ausführen der Analyse bereit, während die Entwickler Code schreiben, mit allen Features der Visual Studio-Benutzeroberfläche für das Beheben von Codeproblemen: Anzeigen von Wellenlinien im Editor, Auffüllen der Fehlerliste von Visual Studio, Erstellen der "Glühbirnen"-Vorschläge und Darstellung der umfassenden Vorschau vorgeschlagener Fixe.

In diesem Tutorial lernen Sie die Erstellung eines **Analysetools** und eines begleitenden **Codefixes** unter Verwendung der Roslyn-APIs kennen. Ein Analysetool ist eine Möglichkeit, Quellcodeanalyse auszuführen und dem Benutzer ein Problem zu melden. Optional kann ein Analysetool auch einen Codefix bereitstellen, der eine Änderung am Quellcode des Benutzers darstellt. In diesem Tutorial wird ein Analysetool erstellt, das Deklarationen von lokalen Variablen enthält, die mithilfe des `const`-Modifizierers deklariert werden könnten, es aber nicht sind. Der begleitende Codefix ändert diese Deklarationen, indem er den `const`-Modifizierer hinzufügt.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019](https://www.visualstudio.com/downloads), Version 16.7 oder höher

Installieren Sie zunächst über den Visual Studio-Installer das **SDK für die .NET Compiler Platform** :

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Das Erstellen und Überprüfen Ihres Analysetools erfolgt in mehreren Schritten:

1. Erstellen der Projektmappe
1. Registrieren von Name und Beschreibung des Analysetools
1. Melden von Warnungen und Empfehlungen des Analysetools
1. Implementieren des Codefixes zum Übernehmen der Empfehlungen
1. Verbessern der Analyse durch Komponententests

## <a name="explore-the-analyzer-template"></a>Kennenlernen der Vorlage für das Analysetool

Ihr Analysetool meldet dem Benutzer alle lokalen Variablendeklarationen, die in lokale Konstanten konvertiert werden können. Beachten Sie z. B. folgenden Code:

```csharp
int x = 0;
Console.WriteLine(x);
```

Im Code oben ist `x` ein konstanter Wert zugewiesen, der nie geändert wird. Er kann mithilfe des `const`-Modifizierers deklariert werden:

```csharp
const int x = 0;
Console.WriteLine(x);
```

Dies bringt die Analyse mit sich, mit der bestimmt wird, ob eine Variable zu einer Konstanten gemacht werden kann, wozu Syntaxanalyse, Konstantenanalyse des Initialisiererausdrucks und eine Datenflussanalyse erforderlich sind, um sicherzustellen, dass zu keinem Zeitpunkt in die Variable geschrieben wird. Die .NET Compiler Platform stellt APIs zur Verfügung, die das Durchführen dieser Analyse erleichtern. Der erste Schritt ist die Erstellung eines neuen C#-Projekts **Analysetool mit Codefix** .

- Wählen Sie in Visual Studio **Datei > Neu > Projekt...** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.
- Wählen Sie unter **Visual C# > Erweiterbarkeit** **Analyzer with code fix (.NET Standard)** (Analysetool mit Codefix (.NET Standard)) aus.
- Benennen Sie Ihr Projekt " **MakeConst** ", und klicken Sie auf „OK“.

Die Vorlage für das Analysetool mit Codefix erstellt drei Projekte: Das erste enthält das Analysetool und den Codefix, das zweite ist ein Komponententestprojekt, und das dritte ist das VSIX-Projekt. Das Standardstartprojekt ist das VSIX-Projekt. Drücken Sie <kbd>F5</kbd>, um das VSIX-Projekt zu starten. Dadurch wird eine zweite Instanz von Visual Studio mit geladenem neuem Analysemodul gestartet.

> [!TIP]
> Wenn Sie das Analysetool ausführen, wird eine zweite Instanz von Visual Studio gestartet. Diese zweite Kopie verwendet eine andere Registrierungsstruktur zum Speichern von Einstellungen. Dadurch können Sie in beiden Instanzen von Visual Studio verschiedene Anzeigeeinstellungen verwenden. Sie können für die Testinstanz von Visual Studio ein anderes Design auswählen. Achten Sie außerdem darauf, Ihre Einstellungen oder Ihre Anmeldung nicht mithilfe der Testinstanz von Visual Studio als mobiler Benutzer auf Ihr Visual Studio-Konto zu übertragen. Auf diese Weise bleiben die unterschiedlichen Einstellungen erhalten.

Erstellen Sie in der zweiten Visual Studio-Instanz, die Sie gerade gestartet haben, ein neues Projekt für eine C#-Konsolenanwendung (wahlweise ein .NET Core- oder ein .NET Framework-Projekt – Analysetools arbeiten auf Quellebene.) Zeigen Sie auf das wellenförmig unterstrichene Token, dann wird der von einem Analysetool bereitgestellte Warnungstext angezeigt.

Die Vorlage erstellt ein Analysetool, das für jede Typdeklaration, deren Typname Kleinbuchstaben enthält, eine Warnung meldet, wie in der folgenden Abbildung dargestellt:

![Analysetool beim Melden einer Warnung](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

Die Vorlage stellt darüber hinaus einen Codefix bereit, der jeden Typnamen, der Kleinbuchstaben enthält, in durchgängig Großbuchstaben ändert. Sie können auf die zusammen mit der Warnung angezeigte Glühbirne klicken, um die vorgeschlagenen Änderungen anzuzeigen. Wenn Sie die vorgeschlagenen Änderungen akzeptieren, werden der Typname und alle Verweise auf den betreffenden Typ in der Projektmappe aktualisiert. Nachdem Sie jetzt das anfängliche Analysetool in Aktion gesehen haben, schließen Sie die zweite Visual Studio-Instanz, und kehren Sie zu Ihrem Analysetoolprojekt zurück.

Sie brauchen keine zweite Instanz von Visual Studio zu starten und neuen Code zu erstellen, um jede Änderung an Ihrem Analysetool zu testen. Die Vorlage erstellt für Sie außerdem ein Komponententestprojekt. Dieses Projekt enthält zwei Tests. `TestMethod1` zeigt das typische Format eines Tests, der Code analysiert, ohne eine Diagnose auszulösen. `TestMethod2` zeigt das Format eines Tests, der eine Diagnose auslöst und dann einen vorgeschlagenen Codefix anwendet. Beim Erstellen Ihres Analysetools und Codefixes werden Sie Tests für verschiedene Codestrukturen schreiben, um Ihre Arbeit zu überprüfen. Komponententests für Analysetools sind viel schneller als interaktive Tests in Visual Studio.

> [!TIP]
> Analysetool-Komponententests sind ein hervorragendes Werkzeug, wenn Sie wissen, welche Codekonstrukte Ihr Analysetool auslösen sollten und welche nicht. Das Laden Ihres Analysetools in einer weiteren Visual Studio-Instanz ist ein tolles Hilfsmittel, um Konstrukte zu finden und zu untersuchen, die Ihnen möglicherweise noch nicht in den Sinn gekommen sind.

## <a name="create-analyzer-registrations"></a>Erstellen von Analysetoolregistrierungen

Die Vorlage erstellt die anfängliche `DiagnosticAnalyzer`-Klasse in der Datei **MakeConstAnalyzer.cs** . Dieses anfängliche Analysetool zeigt zwei wichtige Eigenschaften jedes Analysetools.

- Jedes Diagnoseanalysetool muss ein `[DiagnosticAnalyzer]`-Attribut bereitstellen, das die Sprache beschreibt, in der es arbeitet.
- Jedes Diagnoseanalysetool muss aus der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>-Klasse abgeleitet sein.

Die Vorlage zeigt außerdem die grundlegenden Features, die jedes Analysetool auszeichnen:

1. Registrieren von Aktionen. Die Aktionen stellen Codeänderungen dar, die Ihr Analysetool auslösen sollten, um den Code auf Verstöße hin zu untersuchen. Wenn Visual Studio Codebearbeitungen erkennt, die mit einer registrierten Aktion übereinstimmen, ruft es die registrierte Methode Ihres Analysetools auf.
1. Erstellen von Diagnosen. Wenn Ihr Analysemodul einen Verstoß erkennt, erstellt es ein Diagnoseobjekt, das von Visual Studio verwendet wird, um den Benutzer vom Verstoß zu benachrichtigen.

Sie registrieren Aktionen in Ihrer Überschreibung der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>-Methode. In diesem Tutorial suchen Sie auf der Suche nach lokalen Deklarationen **Syntaxknoten** auf und sehen, welche von ihnen konstante Werte aufweisen. Wenn eine Deklaration eine Konstante vorsehen könnte, erstellt und meldet Ihr Analysetool eine Diagnose.

Der erste Schritt besteht darin, die Registrierungskonstanten und die `Initialize`-Methode zu aktualisieren, damit diese Konstanten Ihr „Make Const“-Analysetool anzeigen. Die meisten der Zeichenfolgenkonstanten sind in der Zeichenfolgen-Ressourcendatei definiert. Sie sollten sich zwecks einfacherer Lokalisierung auch an diese Praxis halten. Öffnen Sie die **Resources.resx** -Datei für das **MakeConst** -Analysetoolprojekt. Dadurch wird der Ressourcen-Editor angezeigt. Aktualisieren Sie die Zeichenfolgenressourcen wie folgt:

- Ändern Sie `AnalyzerTitle` in „Variable kann als Konstante umdeklariert werden“.
- Ändern Sie `AnalyzerMessageFormat` in „Kann als Konstante deklariert werden“.
- Ändern Sie `AnalyzerDescription` in „Als Konstante deklarieren“.

Ändern Sie außerdem die **Zugriffsmodifizierer** -Dropdownliste in `public`. Das vereinfacht die Verwendung dieser Konstanten in Komponententests. Wenn Sie fertig sind, sollte der Ressourcen-Editor wie in der folgenden Abbildung aussehen:

![Zeichenfolgenressourcen aktualisieren](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

Die verbleibenden Änderungen finden sich in der Analysetooldatei. Öffnen Sie **MakeConstAnalyzer.cs** in Visual Studio. Ändern Sie die registrierte Aktion von einer Aktion, die für Symbole aktiv ist, in eine, die mit Syntax agiert. Suchen Sie in der `MakeConstAnalyzerAnalyzer.Initialize`-Methode die Zeile, die die Aktion für Symbole registriert:

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

Ersetzen Sie sie durch die folgende Zeile:

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

Nach dieser Änderung können Sie die `AnalyzeSymbol`-Methode löschen. Dieses Analysetool untersucht <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>-Anweisungen, keine <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>-Anweisungen. Beachten Sie, dass `AnalyzeNode` mit roten Wellenlinien unterstrichen ist. Der Code, den Sie soeben hinzugefügt haben, verweist auf eine `AnalyzeNode`-Methode, die noch nicht deklariert wurde. Deklarieren Sie diese Methode mithilfe des folgenden Codes:

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

Ändern Sie in **MakeConstAnalyzer.cs** die `Category` in „Usage“, wie im folgenden Code gezeigt:

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a>Suchen von lokalen Deklarationen, die „const“ lauten könnten

Es ist Zeit, die erste Version der `AnalyzeNode`-Methode zu schreiben. Sie soll nach einer einzelnen lokalen Deklaration suchen, die `const` sein könnte, es aber nicht ist, wie der folgende Code:

```csharp
int x = 0;
Console.WriteLine(x);
```

Der erste Schritt besteht darin, nach lokalen Deklarationen zu suchen. Fügen Sie in **MakeConstAnalyzer.cs** den folgenden Code zu `AnalyzeNode` hinzu:

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

Diese Umwandlung funktioniert immer, da Ihr Analysetool für Änderungen an lokalen Deklarationen und nur an lokalen Deklarationen registriert wurde. Kein anderer Knotentyp löst einen Aufruf Ihrer `AnalyzeNode`-Methode aus. Überprüfen Sie als Nächstes die Deklaration für alle `const`-Modifizierer. Wenn Sie sie finden, geben Sie sofort zurück. Der folgende Code sucht nach allen `const`-Modifizierern in der lokalen Deklaration:

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

Schließlich müssen Sie überprüfen, ob die Variable `const` sein könnte. Das bedeutet, sicherzustellen, dass sie nach der Initialisierung nie zugewiesen wird.

Sie führen semantische Analysen mithilfe von <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext> durch. Sie verwenden das `context`-Argument, um festzustellen, ob die lokale Variablendeklaration als `const` festgelegt werden kann. Ein <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> stellt sämtliche semantischen Informationen in einer einzelnen Quelldatei dar. Mehr können Sie im Artikel über [semantische Modelle](../work-with-semantics.md) erfahren. Sie verwenden das <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> zum Durchführen einer Datenflussanalyse für die lokale Deklarationsanweisung. Anschließend nutzen Sie die Ergebnisse dieser Datenflussanalyse, um sicherzustellen, dass zu keiner Zeit irgendwo ein neuer Wert in die lokale Variable geschrieben wird. Rufen Sie die <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A>-Erweiterungsmethode auf, um das <xref:Microsoft.CodeAnalysis.ILocalSymbol> für die Variable abzurufen und zu sicherzustellen, dass sie nicht in der <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType>-Sammlung der Datenflussanalyse enthalten ist. Fügen Sie am Ende der `AnalyzeNode`-Methode den folgenden Code hinzu:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

Der Code, den Sie soeben hinzugefügt haben, stellt sicher, dass die Variable nicht verändert wird und daher als `const` deklariert werden kann. Es ist Zeit, die Diagnose zu stellen. Fügen Sie in `AnalyzeNode` den folgenden Code als letzte Zeile hinzu:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

Sie können Ihren Fortschritt überprüfen, indem Sie <kbd>F5</kbd> drücken, um Ihr Analysetool auszuführen. Sie können die Konsolenanwendung laden, die Sie zuvor erstellt haben, und dann den folgenden Testcode hinzufügen:

```csharp
int x = 0;
Console.WriteLine(x);
```

Die Glühbirne sollte angezeigt werden, und Ihr Analysetool sollte eine Diagnose melden. Allerdings verwendet die Glühbirne noch den aus der Vorlage erzeugten Codefix und informiert Sie, dass die Variable in Großbuchstaben geschrieben werden kann. Im nächsten Abschnitt erfahren Sie, wie der Codefix geschrieben wird.

## <a name="write-the-code-fix"></a>Schreiben des Codefixes

Ein Analysetool kann einen Codefix oder mehrere zur Verfügung stellen. Ein Codefix definiert eine Bearbeitung, die das gemeldete Problem angeht. Für das Analysetool, das Sie erstellt haben, können Sie einen Codefix bereitstellen, der das Schlüsselwort „const“ einfügt:

```csharp
const int x = 0;
Console.WriteLine(x);
```

Der Benutzer wählt es im Editor in der Benutzeroberfläche der Glühbirne aus, und Visual Studio ändert den Code.

Öffnen Sie die von der Vorlage hinzugefügte Datei **MakeConstCodeFixProvider.cs** .  Dieser Codefix ist bereits mit der Diagnose-ID verschaltet, die von Ihrem Diagnoseanalysetool erzeugt wird, er implementiert jedoch noch nicht die gewünschte Codetransformation. Zunächst sollten Sie einen Teil des Vorlagencodes entfernen. Ändern Sie die Titelzeichenfolge in „Als Konstante deklarieren“:

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

Löschen Sie als Nächstes die `MakeUppercaseAsync`-Methode. Sie trifft nicht mehr zu.

Alle Codefixanbieter werden von <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider> abgeleitet. Sie alle überschreiben <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType>, um verfügbare Codefixe zu melden. Ändern Sie in `RegisterCodeFixesAsync` den Typ des Vorgängerknotens, nach dem Sie suchen, in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, damit er mit der Diagnose übereinstimmt:

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

Ändern Sie dann die letzte Zeile, um einen Codefix zu registrieren. Ihr Fix erstellt ein neues Dokument, das sich daraus ergibt, dass einer vorhandenen Deklaration der `const`-Modifizierer hinzugefügt wird:

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

Sie werden rote Wellenlinien in dem soeben hinzugefügten Code unter dem Symbol `MakeConstAsync` bemerken. Fügen Sie eine Deklaration für `MakeConstAsync` hinzu, wie etwa den folgenden Code:

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

Ihre neue `MakeConstAsync`-Methode transformiert das <xref:Microsoft.CodeAnalysis.Document>, das die Quelldatei des Benutzers darstellt, in ein neues <xref:Microsoft.CodeAnalysis.Document>, das jetzt eine `const`-Deklaration enthält.

Sie erstellen ein neues `const`-Schlüsselworttoken, um es am Anfang der Deklarationsanweisung einzufügen. Achten Sie darauf, zuerst alle führenden Trivia aus dem ersten Token der Deklarationsanweisung zu entfernen und sie an das `const`-Token anzufügen. Fügen Sie der `MakeConstAsync`-Methode folgenden Code hinzu:

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

Fügen Sie als Nächstes der Deklaration das `const`-Token mithilfe des folgenden Codes hinzu:

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

Formatieren Sie anschließend die neue Deklaration gemäß den C#-Formatierungsregeln. Das Formatieren Ihrer Änderungen in Anlehnung an den vorhandenen Code macht einen besseren Eindruck. Fügen Sie unmittelbar hinter dem vorhandenen Code die folgende Anweisung hinzu:

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

Für diesen Code ist ein neuer Namespace erforderlich. Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu:

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

Der letzte Schritt besteht im Ausführen Ihrer Bearbeitung. Dieser Prozess besteht aus drei Schritten:

1. Abrufen eines Handles zu dem vorhandenen Dokument.
1. Erstellen eines neuen Dokuments durch Ersetzen der vorhandenen Deklaration durch die neue Deklaration.
1. Zurückgeben des neuen Dokuments.

Fügen Sie den folgenden Code am Ende der `MakeConstAsync`-Methode hinzu:

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

Ihr Codefix ist nun bereit, ausprobiert zu werden.  Drücken Sie <kbd>F5</kbd>, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio auszuführen. Erstellen Sie in der zweiten Visual Studio-Instanz ein neues Konsolenanwendungsprojekt in C#, und fügen Sie der Methode „Main“ einige lokale Variablendeklarationen hinzu, die mit konstanten Werten initialisiert sind. Sie sehen, dass sie als Warnungen gemeldet werden, wie unten dargestellt.

![Warnungen „Kann als ‚const‘ deklariert werden“](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

Sie haben große Fortschritte erzielt. Unter den Deklarationen, die in `const` umgewandelt werden können, werden Wellenlinien angezeigt. Aber die Arbeit ist noch nicht abgeschlossen. Alles hier funktioniert, wenn Sie `const` den Deklarationen beginnend bei `i`, dann weiter mit `j` und schließlich `k` hinzufügen. Wenn Sie den `const`-Modifizierer aber in einer anderen Reihenfolge zu i zuweisen, beginnend mit `k`, erzeugt Ihr Analysetool Fehler: `k` kann nicht `const` deklariert werden, sofern nicht `i` und `j` beide bereits `const` sind. Sie müssen weitere Analysen durchführen, um sicherzustellen, dass Sie mit den verschiedenen Weisen umgehen können, in denen Variablen deklariert und initialisiert werden können.

## <a name="build-data-driven-tests"></a>Erstellen von datengesteuerten Tests

Ihr Analysetool und der Codefix funktionieren beim einfachen Fall einer einzelnen Deklaration, die als „const“ deklariert werden kann. Es gibt eine Vielzahl von möglichen Deklarationsanweisungen, bei denen diese Implementierung zu Fehlern führt. Sie tragen diesen Fällen Rechnung, indem Sie mit der Komponententestbibliothek arbeiten, die von der Vorlage erstellt wurde. Das funktioniert viel schneller, als wiederholt eine zweite Instanz von Visual Studio zu öffnen.

Öffnen Sie die **MakeConstUnitTests.cs** -Datei im Komponententestprojekt. Die Vorlage hat zwei Tests erstellt, die den zwei allgemeinen Mustern für einen Komponententest für Analysetools und Codefixe folgen. `TestMethod1` zeigt das Muster für einen Test, der sicherstellt, dass das Analysetool keine Diagnose meldet, wenn es das nicht sollte. `TestMethod2` zeigt das Muster für das Melden einer Diagnose und das Ausführen des Codefixes.

Der Code nahezu jedes Tests für Ihr Analysetool folgt einem dieser beiden Muster. Im ersten Schritt können Sie diese Tests als datengesteuerte Tests umarbeiten. Anschließend wird es einfach, neue Tests zu erstellen, indem Sie neue Zeichenfolgenkonstanten hinzufügen, um verschiedene Testeingaben darzustellen.

Aus Effizienzgründen besteht der erste Schritt in der Umgestaltung der beiden Tests in datengesteuerte Tests. Anschließend müssen Sie lediglich ein paar Zeichenfolgenkonstanten für jeden neuen Test definieren. Benennen Sie im Rahmen der Umgestaltung beide Methoden mit besseren Namen um. Ersetzen Sie `TestMethod1` durch diesen Test, der sicherstellt, dass keine Diagnose ausgelöst wird:

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

Sie können für diesen Test eine neue Datenzeile erstellen, indem Sie jedes Codefragment definieren, das keine Warnung von Ihrer Diagnose auslösen soll. Diese Überladung von `VerifyCSharpDiagnostic` besteht den Test, wenn für das Quellcodefragment keine Diagnose ausgelöst wird.

Ersetzen Sie als Nächstes `TestMethod2` durch diesen Test, der sicherstellt, dass für das Quellcodefragment eine Diagnose ausgelöst und ein Codefix angewendet wird:

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

Im vorstehenden Code wurden außerdem ein paar Änderungen an dem Code vorgenommen, der das erwartete Diagnoseergebnis erzeugt. Er verwendet die im `MakeConst`-Analysetool registrierten öffentlichen Konstanten. Außerdem verwendet er zwei Zeichenfolgenkonstanten für die Eingabe und die feste Quelle. Fügen Sie der `UnitTest`-Klasse die folgenden Zeichenfolgenkonstanten hinzu:

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

Führen Sie diese zwei Tests aus, um sicherzustellen, dass sie bestanden werden. Öffnen Sie in Visual Studio den **Test-Explorer** , indem Sie **Test** > **Windows** > **Test-Explorer** auswählen. Wählen Sie dann den Link **Alle ausführen** aus.

## <a name="create-tests-for-valid-declarations"></a>Erstellen von Tests für gültige Deklarationen

Ganz allgemein sollten Analysetool so schnell wie möglich beendet werden und nur minimale Arbeit verrichten. Visual Studio ruft registrierte Analysetools auf, während der Benutzer den Code bearbeitet. Reaktionsfähigkeit ist eine wichtige Anforderung. Es gibt mehrere Testfälle für Code, der Ihre Diagnose nicht auslösen soll. Ihr Analysetool verarbeitet bereits einen dieser Tests, den Fall, in dem eine Variable nach der Initialisierung zugewiesen wird. Fügen Sie Ihren Tests die folgende Zeichenfolgenkonstante hinzu, um diesem Fall darzustellen:

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

Fügen Sie anschließend eine Datenzeile für diesen Test hinzu, wie im Codeausschnitt unten zu sehen:

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Dieser Test wird ebenfalls bestanden. Fügen Sie als Nächstes Konstanten für Bedingungen hinzu, die Sie noch nicht behandelt haben:

- Deklarationen, die bereits `const` sind, da sie bereits Konstanten sind:

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- Deklarationen, die keinen Initialisierer besitzen, weil es keinen zu verwendenden Wert gibt:

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- Deklarationen, bei denen der Initialisierer keine Konstante ist, da sie zur Kompilierzeit keine Konstanten sein können:

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

Es kann sogar noch komplizierter sein, da C# mehrere Deklarationen in Form einer Anweisung zulässt. Betrachten Sie die folgende Zeichenfolgenkonstante aus einem Testfall:

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

Die Variable `i` kann als Konstante deklariert werden, die Variable `j` jedoch nicht. Daher kann aus dieser Anweisung keine const-Deklaration gemacht werden. Fügen Sie die `DataRow`-Deklarationen für alle diese Tests hinzu:

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Führen Sie Ihre Tests erneut aus – Sie werden feststellen, dass bei den neuen Testfällen Fehler auftreten.

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a>Aktualisieren Ihres Analysetools, damit korrekte Deklarationen ignoriert werden

Sie benötigen noch einige Verbesserungen an der `AnalyzeNode`-Methode Ihres Analysetools, um Code herauszufiltern, der den Bedingungen entspricht. Es handelt sich bei allen um verwandte Bedingungen, daher lassen sich auch alle mit ähnlichen Änderungen beheben. Nehmen Sie an `AnalyzeNode` die folgenden Änderungen vor:

- Ihre semantische Analyse hat eine einzelne Variablendeklaration untersucht. Dieser Code muss sich in einer `foreach`-Schleife befinden, die alle innerhalb der gleichen Anweisung deklarierten Variablen untersucht.
- Jede deklarierte Variable muss über einen Initialisierer verfügen.
- Der Initialisierer jeder deklarierten Variable muss zur Kompilierzeit eine Konstante sein.

Ersetzen Sie in Ihrer `AnalyzeNode`-Methode die ursprüngliche semantische Analyse:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

durch den folgenden Codeausschnitt:

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

Die erste `foreach`-Schleife untersucht jede Variablendeklaration mithilfe der Syntaxanalyse. Die erste Prüfung stellt sicher, dass die Variable einen Initialisierer aufweist. Die zweite Prüfung stellt sicher, dass der Initialisierer eine Konstante ist. Die zweite Schleife enthält die ursprüngliche semantische Analyse. Die semantischen Prüfungen befinden sich in einer separaten Schleife, da sie einen größeren Einfluss auf die Leistung haben. Führen Sie Ihre Tests erneut aus – sie sollten alle bestanden werden.

## <a name="add-the-final-polish"></a>Der letzte Schliff

Sie haben es fast geschafft! Es gibt noch ein paar weitere Bedingungen, mit denen Ihr Analysetool umgehen muss. Visual Studio ruft Analysetools auf, während der Benutzer Code schreibt. Es tritt häufig der Fall ein, dass Ihr Analysetool für Code aufgerufen wird, der sich nicht kompilieren lässt. Die Methode `AnalyzeNode` des Diagnoseanalysetools überprüft nicht, ob der Konstantenwert in den Variablentyp konvertiert werden kann. Daher konvertiert die aktuelle Implementierung eine falsche Deklaration wie int i = "abc"' unbedarft in eine lokale Konstante. Fügen Sie für diese Bedingung eine Quellzeichenfolgenkonstante hinzu:

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

Darüber hinaus werden Verweistypen nicht ordnungsgemäß behandelt. Der einzige Konstantenwert, die für einen Verweistyp zulässig ist, ist `null`, abgesehen von dem Fall <xref:System.String?displayProperty=nameWithType>, der Zeichenfolgenliterale zulässt. Das heißt, `const string s = "abc"` ist zulässig, `const object s = "abc"` aber nicht. Diese Bedingung wird mit diesem Codeausschnitt überprüft:

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

Wenn Sie gründlich sein wollen, müssen Sie einen weiteren Test hinzufügen, um sicherzustellen, dass Sie für eine Zeichenfolge eine Konstantendeklaration erstellen können. Der folgende Codeausschnitt definiert sowohl den Code, der die Diagnose auslöst, als auch den Code nach der Anwendung des Fixes:

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

Schließlich ergreift bei einer Variablen, die mit dem Schlüsselwort `var` deklariert ist, der Codefix die falsche Aktion und generiert eine `const var`-Deklaration, was von der Sprache C# nicht unterstützt wird. Um diesen Fehler zu beheben, muss der Codefix das Schlüsselwort `var` durch den Namen des abgeleiteten Typs ersetzen:

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

Durch diese Änderungen werden die Datenzeilendeklarationen für beide Tests aktualisiert. Der folgende Code zeigt diese Tests mit allen Datenzeilenattributen:

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

Glücklicherweise lassen sich alle oben aufgeführten Fehler mithilfe genau der Techniken beheben, die Sie gerade gelernt haben.

Zum Beheben des ersten Fehlers öffnen Sie zuerst **DiagnosticAnalyzer.cs** und suchen die foreach-Schleife, in der jeder der Initialisierer der lokalen Deklaration überprüft wird, um sicherzustellen, dass allen konstante Werte zugewiesen wurden. Rufen Sie unmittelbar _vor_ der ersten foreach-Schleife `context.SemanticModel.GetTypeInfo()` auf, um Detailinformationen über den deklarierten Typ der lokalen Deklaration abzurufen:

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

Überprüfen Sie anschließend innerhalb Ihrer `foreach`-Schleife jeden Initialisierer, um sicherzustellen, dass er in den Variablentyp konvertiert werden kann. Fügen Sie die folgende Überprüfung hinzu, nachdem sichergestellt wurde, dass der Initialisierer eine Konstante ist:

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

Die nächste Änderung baut auf der letzten auf. Fügen Sie vor der schließenden geschweiften Klammer der ersten foreach-Schleife den folgenden Code hinzu, um den Typ der lokalen Deklaration zu überprüfen, wenn die Konstante eine Zeichenfolge oder NULL ist.

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

Sie müssen etwas mehr Code in Ihrem Codefixanbieter schreiben, um das Schlüsselwort `var` durch den korrekten Typnamen zu ersetzen. Wechseln Sie zu **CodeFixProvider.cs** zurück. Der Code, den Sie hinzufügen, führt die folgenden Schritte aus:

- Überprüft, ob die Deklaration eine `var`-Deklaration ist, und wenn dies zutrifft:
- Erstellt einen neuen Typ für den abgeleiteten Typ.
- Vergewissert sich, dass die Typdeklaration kein Alias ist. Ist das der Fall, ist eine Deklaration als `const var` zulässig.
- Stellt sicher, dass `var` kein Typname in diesem Programm ist. (In dem Fall ist `const var` zulässig).
- Vereinfacht den vollständigen Typnamen

Das hört sich nach ziemlich viel Code an. Ist es aber nicht. Ersetzen Sie die Zeile, in der `newLocal` deklariert und initialisiert wird, durch den folgenden Code. Er gehört direkt hinter die Initialisierung von `newModifiers`:

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

Sie müssen eine `using`-Anweisung hinzufügen, um den <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>-Typ zu verwenden:

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

Führen Sie Ihre Tests aus – sie sollten alle bestanden werden. Gratulieren Sie sich, indem Sie Ihr fertiges Analysetool ausführen. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio mit geladener Roslyn-Vorschauerweiterung auszuführen.

- Erstellen Sie in der zweiten Visual Studio-Instanz ein neues C#-Konsolenanwendungsprojekt, und fügen Sie `int x = "abc";` zur Methode „Main“ hinzu. Dank der ersten Fehlerbehebung sollte keine Warnung für diese lokale Variablendeklaration gemeldet werden (obwohl es erwartungsgemäß einen Compilerfehler gibt).
- Fügen Sie als Nächstes `object s = "abc";` zur Methode „Main“ hinzu. Aufgrund der zweiten Fehlerbehebung sollte keine Warnung gemeldet werden.
- Fügen Sie schließlich eine weitere lokale Variable hinzu, die das Schlüsselwort `var` verwendet. Sie sehen, dass eine Warnung gemeldet und ein Vorschlag links unterhalb der Meldung angezeigt wird.
- Bewegen Sie den Textcursor des Editors über die Wellenlinien-Unterstreichung, und drücken Sie <kbd>STRG</kbd>+<kbd>.</kbd>, um den vorgeschlagenen Codefix anzuzeigen. Beachten Sie beim Auswählen des Codefixes, dass das Schlüsselwort `var` jetzt ordnungsgemäß verarbeitet wird.

Fügen Sie schließlich den folgenden Code hinzu:

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

Nach diesen Änderungen erhalten Sie rote Wellenlinien nur unter den ersten zwei Variablen. Fügen Sie `const` sowohl zu `i` als auch zu `j` hinzu, und Sie erhalten eine neue Warnung zu `k`, da das nun als `const` deklariert werden kann.

Herzlichen Glückwunsch! Sie haben Ihre erste Erweiterung für die .NET Compiler Platform erstellt, die dynamische Codeanalyse durchführt, um ein Problem zu erkennen, und eine schnelle Problembehebung zu seiner Korrektur bereitstellt. Auf diesem Weg haben Sie viele der Code-APIs kennengelernt, die Teil der .NET Compiler Platform SDKs sind (Roslyn-APIs). Sie können Ihre Arbeit anhand des [fertiggestellten Beispiels](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in unserem GitHub-Beispielrepository überprüfen.

## <a name="other-resources"></a>Weitere Ressourcen

- [Erste Schritte mit der Syntaxanalyse](../get-started/syntax-analysis.md)
- [Erste Schritte mit der semantischen Analyse](../get-started/semantic-analysis.md)
