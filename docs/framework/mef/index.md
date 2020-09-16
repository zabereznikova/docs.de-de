---
title: Managed Extensibility Framework (MEF)
description: Erkunden Sie das Managed Extensibility Framework (MEF), mit dem Anwendungsentwickler Erweiterungen ohne Konfiguration in .NET 4 oder höher ermitteln und verwenden können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
ms.openlocfilehash: b743a26dd401e7015c588be2a197551aa891a687
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555574"
---
# <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

Dieses Thema bietet eine Übersicht über das in .NET Framework 4 eingeführte Managed Extensibility Framework.

## <a name="what-is-mef"></a>Was ist MEF?

Das Managed Extensibility Framework oder MEF ist eine Bibliothek zum Erstellen von einfachen und erweiterbaren Anwendungen. Es ermöglicht Anwendungsentwicklern, Erweiterungen ohne Konfiguration zu ermitteln und zu verwenden. Das Framework ermöglicht Erweiterungsentwicklern, Code leicht zu kapseln und zerbrechliche harte Abhängigkeiten zu vermeiden. MEF ermöglicht nicht nur die Wiederverwendung von Erweiterungen innerhalb von Anwendungen, sondern auch anwendungsübergreifend.

## <a name="the-problem-of-extensibility"></a>Das Problem der Erweiterbarkeit

Angenommen, Sie entwickeln eine komplexe erweiterungsfähige Anwendung. Die Anwendung umfasst eine große Anzahl kleinerer Komponenten und ist gleichzeitig für das Erstellen und Ausführen der Komponenten zuständig.

Der einfachste Lösungsansatz ist, die Komponenten als Quellcode in die Anwendung zu integrieren und sie direkt vom Code aufzurufen. Hierbei ergeben sich allerdings mehrere offensichtliche Nachteile. Zunächst einmal können keine neuen Komponenten hinzugefügt werden, ohne dabei den Quellcode zu ändern. Dies wäre zwar für eine Webanwendung, jedoch nicht für eine Clientanwendung akzeptabel. Außerdem kann möglicherweise nicht auf den Quellcode der Komponenten zugegriffen werden, da diese eventuell von Drittanbietern entwickelt wurden. Aus dem gleichen Grund darf den Komponenten auch nicht der Zugriff auf Ihren Quellcode gestattet werden.

Eine elegantere Möglichkeit wäre die Bereitstellung eines Erweiterungspunkts oder einer Schnittstelle, um die Komponenten von der Anwendung zu entkoppeln. Bei diesem Modell kann eine Schnittstelle zur Implementierung einer Komponente und eine API zur Interaktion mit der Anwendung bereitgestellt werden. So ist die Gewährung von Quellcodezugriff nicht mehr erforderlich, allerdings müssen hier andere Schwierigkeiten beachtet werden.

Da von der Anwendung Komponenten nicht selbständig ermittelt werden können, müssen die verfügbaren und zu ladenden Komponenten exakt angegeben werden. Hierfür werden in der Regel die verfügbaren Komponenten in einer Konfigurationsdatei genau registriert. Das Gewährleisten der Verwendung der richtigen Komponenten kann also zu einem Wartungsproblem werden, insbesondere, wenn die Aktualisierung vom Endbenutzer und nicht vom Entwickler durchgeführt werden muss.

Außerdem können Komponenten nicht untereinander kommunizieren, außer durch die fest definierten Channels der Anwendung selbst. Wurde vom Anwendungsentwickler eine bestimmte Kommunikation nicht eingeplant, kann sie normalerweise nicht stattfinden.

Schließlich müssen sich Komponentenentwickler für harte Abhängigkeiten zwischen Assemblys und den implementierten Schnittstellen entscheiden. Dies kann bei der Verwendung einer Komponente in mehr als einer Anwendung und der Erstellung eines Testframeworks für Komponenten Schwierigkeiten bereiten.

## <a name="what-mef-provides"></a>Dies wird von MEF bereitgestellt

Mit MEF ist die explizite Registrierung verfügbarer Komponenten nicht mehr erforderlich, da sie mithilfe von *Komposition* implizit ermittelt werden können. Durch eine MEF-Komponente (*Teil*) werden sowohl die Abhängigkeiten (*Importe*) als auch die verfügbaren Funktionen (*Exporte*) deklarativ angegeben. Bei der Erstellung eines Teils werden von der MEF-Kompositions-Engine die von anderen Teilen verfügbaren Komponenten für die Importe bereitgestellt.

Auf diese Weise können die im vorherigen Abschnitt erläuterten Probleme vermieden werden. Da die Funktionen von den MEF-Teilen deklarativ angegeben werden, sind sie zur Laufzeit auffindbar. Eine Anwendung kann Teile also ohne hartcodierte Verweise oder instabile Konfigurationsdateien nutzen. Mit dem MEF können Anwendungen Teile anhand von Metadaten ermitteln und untersuchen. Dabei müssen die Teile nicht instanziiert oder ihre Assemblys geladen werden. Daher muss nicht genau angegeben werden, wann und auf welche Weise Erweiterungen geladen werden sollen.

Zusätzlich zu den bereitgestellten Exporten können von einem Teil seine Importe angegeben werden, die von anderen Teilen ausgefüllt werden. Dies ermöglicht die einfache Kommunikation zwischen Teilen und die optimale Verarbeitung von Code. Gemeinsame Dienste von Komponenten können z. B. separat aufgeteilt und leicht geändert oder ersetzt werden.

Da im MEF-Modell keine harten Abhängigkeiten für Anwendungsassemblys erforderlich sind, können Erweiterungen in mehreren Anwendungen wiederverwendet werden. So können anwendungsunabhängig auch mühelos Testumgebungen für Erweiterungskomponenten entwickelt werden.

Eine erweiterbare, mithilfe des MEF erstellte Anwendung deklariert einen Import, der von Erweiterungskomponenten ausgefüllt werden kann und kann ebenfalls Exporte deklarieren, um Anwendungsdienste für Erweiterungen verfügbar zu machen. Von jeder Erweiterungskomponente wird ein Export deklariert. Importe können ebenfalls deklariert werden. Auf diese Weise sind Erweiterungskomponenten selbst automatisch erweiterbar.

## <a name="where-mef-is-available"></a>Verfügbarkeit von MEF

Das MEF ist ein wesentlicher Bestandteil vom .NET Framework 4 und ist überall dort verfügbar, wo das .NET Framework verwendet wird. Sie können MEF in Clientanwendungen verwenden, egal ob bei diesen Windows Forms, WPF oder eine andere Technologie zum Einsatz kommt, oder in Serveranwendungen, die ASP.NET verwenden.

## <a name="mef-and-maf"></a>MEF und MAF

In früheren Versionen von .NET Framework wurde das Managed Add-in Framework (MAF) eingeführt, das für die Isolation und Verwaltung von Erweiterungen innerhalb von Anwendungen entworfen wurde. Bei MAF befindet sich der Fokus auf einer etwas höheren Ebene als bei MEF und liegt auf der Erweiterungsisolation und dem Laden und Entladen von Assemblys, während bei MEF der Fokus auf Erkennbarkeit, Erweiterbarkeit und Portabilität gerichtet ist. Die zwei Frameworks arbeiten optimal zusammen, und beide können von Einzelanwendungen verwendet werden.

## <a name="simplecalculator-an-example-application"></a>SimpleCalculator: Eine Beispielanwendung

Die einfachste Möglichkeit zur Entdeckung der Möglichkeiten von MEF ist das Erstellen einer einfachen MEF-Anwendung. In diesem Beispiel erstellen Sie einen einfachen Rechner namens SimpleCalculator. Das Ziel von SimpleCalculator ist die Erstellung einer Konsolenanwendung, die grundlegende arithmetische Befehle wie "5+3" oder "6-2" verarbeiten kann und korrekte Ergebnisse liefert. Mit MEF können mühelos neue Operatoren hinzugefügt werden, ohne dabei den Anwendungscode ändern zu müssen.

Der vollständige Code für dieses Beispiel kann unter [SimpleCalculator-Beispiel (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/) heruntergeladen werden.

> [!NOTE]
> Mit SimpleCalculator sollen die Konzepte und die Syntax des MEF veranschaulicht werden. Auf ein realistisches Verwendungsszenario wird in diesem Fall kein Wert gelegt. Viele der Anwendungen, die am meisten von der Leistungsfähigkeit von MEF profitieren würden, sind komplexer als SimpleCalculator. Ausführlichere Beispiele finden Sie unter [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) auf GitHub.

- Erstellen Sie zum Einstieg in Visual Studio ein neues Konsolenanwendungsprojekt, und nennen Sie es `SimpleCalculator`.

- Fügen Sie der Assembly `System.ComponentModel.Composition` einen Verweis hinzu, wo sich MEF befindet.

- Öffnen Sie *Module1.vb* oder *Program.cs*, und fügen Sie die Anweisung `Imports` oder `using` für `System.ComponentModel.Composition` und `System.ComponentModel.Composition.Hosting` hinzu. Diese zwei Namespaces enthalten MEF-Typen, die zur Entwicklung einer erweiterbaren Anwendung erforderlich sind.

- Wenn Sie Visual Basic verwenden, fügen Sie das `Public`-Schlüsselwort der Zeile hinzu, die das `Module1`-Modul deklariert.

## <a name="composition-container-and-catalogs"></a>Kompositionscontainer und Kataloge

Der Kern des MEF-Kompositionsmodells ist der *Kompositionscontainer*, der alle verfügbaren Teile enthält und die Komposition ausführt. Mit Komposition ist das Zuweisen von Importen zu Exporten gemeint. Der gängigste Kompositionscontainertyp ist <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, den wir auch für SimpleCalculator verwenden werden.

Wenn Sie Visual Basic verwenden, fügen Sie in der Datei *Module1.vb* die öffentliche Klasse `Program` hinzu.

Fügen Sie der `Program`-Klasse in *Module1.vb* bzw. *Program.cs* die folgende Zeile hinzu:

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

Zur Ermittlung der verfügbaren Teile verwenden Kompositionscontainern einen *Katalog*. Ein Katalog ist ein Objekt, durch das ermittelte, aus einer beliebigen Quelle stammende Teile verfügbar gemacht werden. MEF stellt zur Ermittlung von Teilen in bereitgestellten Typen, Assemblys oder Verzeichnissen Kataloge bereit. Anwendungsentwickler können leicht neue Kataloge zur Ermittlung von Teilen aus anderen Quellen erstellen, z. B. aus einem Webdienst.

Fügen Sie der `Program`-Klasse den folgenden Konstruktor hinzu:

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

Durch den Aufruf von <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> wird der Kompositionscontainer angewiesen, einen bestimmten Satz von Teilen zu verfassen (in diesem Fall die aktuelle Instanz von `Program`). Zu diesem Zeitpunkt wird jedoch keine Aktion ausgeführt, da `Program` über keine Importe zum Füllen verfügt.

## <a name="imports-and-exports-with-attributes"></a>Importe und Exporte mit Attributen

Importieren Sie zunächst mithilfe von `Program` einen Rechner. Dies ermöglicht die Trennung von Benutzeroberflächenkomponenten, z. B. der Konsolenein- und -ausgabe, die an `Program` geleitet werden, von der Logik des Rechners.

Fügen Sie der `Program`-Klasse folgenden Code hinzu:

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

Beachten Sie, dass die Deklaration des `calculator`-Objekts nicht ungewöhnlich ist, aber durch das <xref:System.ComponentModel.Composition.ImportAttribute>-Attribut ergänzt wird. Durch das Attribut wird ein Import deklariert, d. h., bei der Komposition des Objekts wird es von der Kompositions-Engine ausgefüllt.

Jeder Import weist einen *Vertrag* auf, der bestimmt, welche Exporte dem Import zugewiesen werden können. Der Vertrag kann eine explizit angegebene Zeichenfolge sein oder von MEF aus einem angegebenen Typ, in diesem Fall die `ICalculator`-Schnittstelle, automatisch generiert werden. Jeder mit einem entsprechenden Vertrag deklarierte Export kann diesem Import zugewiesen werden. Der Typ des `calculator`-Objekts ist zwar tatsächlich `ICalculator`, allerdings ist dies nicht erforderlich. Der Vertrag ist unabhängig vom Typ des Importobjekts. (In diesem Fall kann `typeof(ICalculator)` ausgelassen werden. Sofern nicht anders angeben, wird von MEF automatisch angenommen, dass es sich um einen importtypbasierten Vertrag handelt.)

Fügen Sie dem Modul oder dem `SimpleCalculator`-Namespace diese sehr einfache Schnittstelle hinzu:

```vb
Public Interface ICalculator
    Function Calculate(input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

Nach der Definition von `ICalculator` benötigen wir eine Klasse für die Implementierung. Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu:

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

Dieser Export entspricht dem Import in `Program`. Damit eine Übereinstimmung zwischen Export und Import vorliegt, muss der Export den gleichen Vertragstyp aufweisen. Beim Export unter einem Vertrag auf Grundlage von `typeof(MySimpleCalculator)` wäre ein Konflikt die Folge, und der Import würde nicht ausgefüllt werden. Der Vertrag muss genau übereinstimmen.

Da der Kompositionscontainer alle in dieser Assembly verfügbaren Teilen enthält, ist der `MySimpleCalculator`-Teil verfügbar. Wenn der Konstruktor für `Program` eine Komposition für das `Program`-Objekt ausführt, wird der entsprechende Import mit einem zu diesem Zweck erstellten `MySimpleCalculator`-Objekt ausgefüllt.

Für die Benutzeroberflächenebene (`Program`) müssen keine weiteren Informationen bereitgestellt werden. Sie können daher den Rest der Benutzeroberflächenlogik in der `Main`-Methode ausfüllen.

Fügen Sie der `Main`-Methode folgenden Code hinzu:

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    string s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 Durch diesen Code wird lediglich eine Eingabezeile gelesen und die `Calculate`-Funktion von `ICalculator` für das Ergebnis aufgerufen, das an die Konsole zurückgegeben wird. Mehr Code ist in `Program` nicht erforderlich. Die restlichen Aufgaben werden in den Teilen ausgeführt.

## <a name="further-imports-and-importmany"></a>Weitere Importe und ImportMany

Zur Gewährleistung der Erweiterbarkeit von SimpleCalculator muss eine Reihe von Vorgängen importiert werden. Ein gewöhnliches <xref:System.ComponentModel.Composition.ImportAttribute>-Attribut wird von ausschließlich einem <xref:System.ComponentModel.Composition.ExportAttribute> ausgefüllt. Sind mehrere Exporte verfügbar, wird von der Kompositions-Engine ein Fehler ausgegeben. Zur Erstellung eines Imports, der mit einer beliebigen Anzahl von Exporten ausgefüllt werden kann, verwenden Sie das <xref:System.ComponentModel.Composition.ImportManyAttribute>-Attribut.

Fügen Sie der `MySimpleCalculator`-Klasse die folgende Eigenschaft für Vorgänge hinzu:

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

<xref:System.Lazy%602> ist ein von MEF bereitgestellter Typ für indirekte Verweise auf Exporte. Zusätzlich zum exportierten Objekt selbst können hier auch *Exportmetadaten* oder Informationen abgerufen werden, die das exportierte Objekt beschreiben. Jeder <xref:System.Lazy%602> enthält ein `IOperation`-Objekt, das eine tatsächliche Operation darstellt, und ein `IOperationData`-Objekt, das die Metadaten darstellt.

Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgenden einfachen Schnittstellen hinzu:

```vb
Public Interface IOperation
    Function Operate(left As Integer, right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 In diesem Fall handelt es sich bei den Metadaten für die einzelnen Vorgänge um das Symbol, das diese Operation darstellt, z. B. +, -, \* usw. Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu, um die Additionsoperation verfügbar zu machen:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

An der Funktionsweise des <xref:System.ComponentModel.Composition.ExportAttribute>-Attributs hat sich nichts geändert. Das <xref:System.ComponentModel.Composition.ExportMetadataAttribute>-Attribut fügt dem Export Metadaten in Form eines Name-Wert-Paars hinzu. `Add` wird zwar von der `IOperation`-Klasse implementiert; eine Klasse, die `IOperationData` implementiert, wurde jedoch nicht explizit definiert. Stattdessen wird eine Klasse, deren Eigenschaften auf den Namen der bereitgestellten Metadaten basieren, implizit von MEF erstellt. (Dies ist eine von mehreren Möglichkeiten für den Zugriff auf Metadaten in MEF.)

Die Komposition in MEF ist *rekursiv*. Sie haben das `Program`-Objekt, durch das ein `ICalculator` vom Typ `MySimpleCalculator` importiert wurde, explizit zusammengesetzt. Von `MySimpleCalculator` wird wiederum eine Auflistung von `IOperation`-Objekten importiert. Dieser Import wird zur gleichen Zeit wie die Importe von `MySimpleCalculator` bei der Erstellung von `Program` ausgefüllt. Würde von der `Add`-Klasse ein weiterer Import deklariert werden, würde dieser ebenfalls ausgefüllt werden müssen usw. Jeder nicht ausgefüllte Import führt zu einem Fehler bei der Komposition. (Es ist jedoch möglich, Importe als optional zu deklarieren oder ihnen Standardwerte zuzuweisen.)

## <a name="calculator-logic"></a>Rechnerlogik

Sind diese Teile bereitgestellt, bleibt nun noch die Rechnerlogik selbst. Fügen Sie der `MySimpleCalculator`-Klasse den folgenden Code hinzu, um die `Calculate`-Methode zu implementieren:

```vb
Public Function Calculate(input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(string input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input);
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

Durch die anfänglichen Schritte wird die Eingabezeichenfolge analysiert und in linke und rechte Operanden sowie in ein Operatorzeichen eingeteilt. In der `foreach`-Schleife wird jeder Member der `operations`-Auflistung untersucht. Diese Objekte sind vom Typ <xref:System.Lazy%602>, und der Zugriff auf die Metadatenwerte und das exportierte Objekt ist mit der <xref:System.Lazy%602.Metadata%2A>- bzw. <xref:System.Lazy%601.Value%2A>-Eigenschaft möglich. Wird in diesem Fall festgestellt, dass es sich bei der `Symbol`-Eigenschaft des `IOperationData`-Objekts um eine Übereinstimmung handelt, ruft der Rechner die `Operate`-Methode des `IOperation`-Objekts auf und gibt das Ergebnis zurück.

Zur Fertigstellung des Rechners benötigen Sie auch eine Hilfsmethode, die die Position des ersten Zeichens einer Zeichenfolge zurückgibt, bei dem es sich nicht um eine Ziffer handelt. Fügen Sie der `MySimpleCalculator`-Klasse die folgende Hilfsmethode hinzu:

```vb
Private Function FindFirstNonDigit(s As String) As Integer
    For i = 0 To s.Length - 1
        If Not Char.IsDigit(s(i)) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!Char.IsDigit(s[i])) return i;
    }
    return -1;
}
```

Sie sollten das Datenbankprojekt jetzt kompilieren und ausführen können. In Visual Basic müssen Sie sicherstellen, dass Sie `Public` das Schlüsselwort `Module1` hinzugefügt haben. Geben Sie im Konsolenfenster eine Addition ein, z. B. "5+3", und der Rechner gibt das entsprechende Ergebnis aus. Ein beliebiger anderer Operator führt zu einer Meldung, die anzeigt, dass der Vorgang nicht gefunden werden konnte.

## <a name="extending-simplecalculator-using-a-new-class"></a>Erweitern von SimpleCalculator mithilfe einer neuen Klasse

Da der Rechner nun funktioniert, kann ganz leicht eine neue Rechenoperation hinzugefügt werden. Fügen Sie dem Modul oder `SimpleCalculator`-Namespace die folgende Klasse hinzu:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

Kompilieren Sie das Projekt und führen Sie es aus. Geben Sie eine Subtraktion ein, z. B. "5-3". Der Rechner unterstützt jetzt Subtraktionen ebenso sowie Additionen.

## <a name="extending-simplecalculator-using-a-new-assembly"></a>Erweitern von SimpleCalculator mithilfe einer neuen Assembly

Das Hinzufügen von Klassen zum Quellcode ist einfach, aber mit MEF kann auch außerhalb des Quellcodes einer Anwendung nach Teilen gesucht werden. Zur Veranschaulichung muss SimpleCalculator für die Suche nach Teilen in Verzeichnissen und in seinen eigenen Assemblys durch das Hinzufügen eines <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> angepasst werden.

Fügen Sie dem SimpleCalculator-Projekt ein neues Verzeichnis mit dem Namen `Extensions` hinzu. Das Verzeichnis muss auf der Projektebene und nicht auf der Projektmappenebene hinzugefügt werden. Fügen Sie der Projektmappe anschließend ein neues ClassLibrary-Projekt mit dem Namen `ExtendedOperations` hinzu. Das neue Projekt wird in eine separate Assembly kompiliert.

Öffnen Sie den Projekteigenschaften-Designer für das ExtendedOperations-Projekt, und klicken Sie auf die Registerkarte **Erstellen** oder auf die Registerkarte **Kompilieren**. Ändern Sie den **Buildausgabepfad** oder den **Ausgabepfad**, sodass dieser auf das Erweiterungsverzeichnis im SimpleCalculator-Projektverzeichnis zeigt ( *..\SimpleCalculator\Extensions\\* ).

 Fügen Sie anschließend dem `Program`-Konstruktor in der Datei *Module1.vb* oder in der Datei *Program.cs* die folgende Zeile hinzu:

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

Ersetzen Sie den Beispielpfad durch den Pfad zum Verzeichnis "Erweiterungen". (Dieser absolute Pfad ist nur für Debugzwecke bestimmt. In einer Produktionsanwendung würde ein relativer Pfad verwendet werden.) Vom <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> werden jetzt alle in den Assemblys im Verzeichnis "Erweiterungen" enthaltenen Teile dem Kompositionscontainer hinzugefügt.

Fügen Sie im ExtendedOperations-Projekt Verweise auf SimpleCalculator und System.ComponentModel.Composition hinzu. Fügen Sie in der ExtendedOperations-Klassendatei eine `Imports`- oder eine `using`-Anweisung für System.ComponentModel.Composition hinzu. Fügen Sie in Visual Basic die `Imports`-Anweisung für SimpleCalculator hinzu. Fügen Sie der ExtendedOperations-Klassendatei anschließend den folgenden Code hinzu:

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

Das <xref:System.ComponentModel.Composition.ExportAttribute>-Attribut muss vom gleichen Typ sein wie <xref:System.ComponentModel.Composition.ImportAttribute>, damit der Vertrag als Übereinstimmung betrachtet wird.

Kompilieren Sie das Projekt und führen Sie es aus. Testen Sie den neuen MOD (%)-Operator.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Thema wurden die grundlegenden Konzepte des MEF behandelt.

- Teile, Kataloge und der Kompositionscontainer

     Die Teile und der Kompositionscontainer sind die Grundbausteine einer MEF-Anwendung. Ein Teil ist jedes Objekt, durch das ein Wert importiert oder exportiert wird, einschließlich des Objekts selbst. Ein Katalog stellt eine Auflistung der Teile einer bestimmten Quelle bereit. Der Kompositionscontainer verwendet die von einem Katalog bereitgestellten Teile, um eine Komposition (die Bindung von Importen an Exporte) durchzuführen.

- Importe und Exporte

     Durch Importe und Exporte kommunizieren Komponenten miteinander. Durch einen Import fordert eine Komponente einen bestimmten Wert oder ein Objekt an. Mit einem Export wird die Verfügbarkeit eines Werts angezeigt. Jeder Import wird anhand seines Vertrags mit einer Reihe von Exporten verglichen.

## <a name="next-steps"></a>Nächste Schritte

Der vollständige Code für dieses Beispiel kann unter [SimpleCalculator-Beispiel (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/) heruntergeladen werden.

 Weitere Informationen und Codebeispiele finden Sie unter [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef). Eine Liste der MEF-Typen finden Sie unter dem <xref:System.ComponentModel.Composition?displayProperty=nameWithType>-Namespace.
