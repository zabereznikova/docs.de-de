---
title: Entwerfen mit Verweistypen, die NULL-Werte zulassen
description: Dieses erweiterte Tutorial enthält eine Einführung zu Verweistypen, die NULL-Werte zulassen. Sie erfahren, wie Sie Ihre Entwurfsabsicht ausdrücken, wenn die Verweiswerte Null sein können, und wie Sie den Compiler durchsetzen, wenn sie nicht NULL sein können.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: bd575b226a2ff61e938719b064ff5ede0cf66013
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805179"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a>Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen

C# 8.0 führt [Nullable-Verweistypen](../nullable-references.md) ein, die Verweistypen auf die gleiche Weise ergänzen, wie Nullable-Werttypen Werttypen ergänzen. Sie deklarieren eine Variable zu einem **Verweistyp, der NULL-Werte zulässt**, indem Sie `?` an den Typen anfügen. Beispielsweise stellt `string?` eine `string` dar, die NULL-Werte zulässt. Mit diesen neuen Typen können Sie Ihre Entwurfsabsicht besser zum Ausdruck bringen: Einige Variablen *müssen immer einen Wert* haben, bei anderen  *kann ein Wert fehlen*.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Integrieren von Verweistypen, die NULL-Werte zulassen und nicht zulassen, in Ihre Entwürfe.
> - Aktivieren von Überprüfungen Ihres Verweistypen, der NULL-Werte zulässt, anhand Ihres Codes.
> - Schreiben von Code, bei dem ein Compiler diese Entwurfsentscheidungen erzwingt.
> - Verwenden des Verweisfeatures, das NULL-Werte zulässt, in Ihren eigenen Entwürfen.

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8.0-Compiler ist mit [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) verfügbar.

In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.

## <a name="incorporate-nullable-reference-types-into-your-designs"></a>Integrieren von Verweistypen, die NULL-Werte zulassen, in Ihre Entwürfe

In diesem Tutorial erstellen Sie eine Bibliothek, die die Ausführung einer Umfrage modelliert. Der Code verwendet Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen, zur Darstellung der realen Konzepte. Die Fragen in der Umfrage können nie NULL sein. Ein Befragter möchte eine Frage möglicherweise nicht beantworten. In diesem Fall können die Antworten `null` sein.

Der Code, den Sie für dieses Beispiel schreiben, drückt diese Absicht aus, und der Compiler setzt sie durch.

## <a name="create-the-application-and-enable-nullable-reference-types"></a>Erstellen der Anwendung und Aktivieren der Verweistypen, die NULL-Werte zulassen

Erstellen Sie eine neue Konsolenanwendung in Visual Studio oder über die Befehlszeile mit `dotnet new console`. Nennen Sie die Anwendung `NullableIntroduction`. Nachdem Sie die Anwendung erstellt haben, müssen Sie angeben, dass das gesamte Projekt in einem aktivierten **Nullable-Anmerkungskontext** kompiliert wird. Öffnen Sie die *CSPROJ*-Datei, und fügen Sie dem `PropertyGroup`-Element ein `Nullable`-Element hinzu. Legen Sie den Wert der Eigenschaft auf `enable`fest. Selbst in C# 8.0-Projekten müssen Sie das Feature für **Nullable-Verweistypen** aktivieren. Grund dafür ist, dass bestehende Verweisvariablendeklarationen nach dem Aktivieren des Features zu **Verweistypen werden, die NULL-Werte nicht zulassen**. Diese Entscheidung ist zwar hilfreich, um Probleme zu finden, bei denen bestehender Code möglicherweise keine ordnungsgemäßen NULL-Überprüfungen aufweist, aber möglicherweise spiegelt sie nicht genau Ihre ursprüngliche Entwurfsabsicht wider.

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a>Entwerfen der Typen für die Anwendung

Für diese Umfrageanwendung müssen einige Klassen erstellt werden:

- Eine Klasse, die die Liste der Fragen modelliert.
- Eine Klasse, die eine Liste der Personen modelliert, die für die Umfrage kontaktiert werden.
- Eine Klasse, die die Antworten einer Person modelliert, die an der Umfrage teilgenommen hat.

Diese Typen verwenden Verweistypen, die NULL-Werte sowohl zulassen als auch nicht zulassen, um auszudrücken, welche Member erforderlich und welche optional sind. Verweistypen, die NULL-Werte zulassen, kommunizieren diese Entwurfsabsicht eindeutig:

- Die Fragen, die Teil der Umfrage sind, können nie NULL sein. Es ist nicht sinnvoll, eine leere Frage zu stellen.
- Die Befragten können nie NULL sein. Sie werden sicher die Personen nachverfolgen wollen, mit denen Sie Kontakt aufgenommen haben, sogar die Personen, die die Teilnahme abgelehnt haben.
- Jede Antwort auf eine Frage darf NULL sein. Befragten können es ablehnen, einige oder alle Fragen zu beantworten.

Wenn Sie in C# programmiert haben, sind Sie vielleicht so sehr an Verweistypen gewöhnt, die `null`-Werte zulassen, dass Sie andere Möglichkeiten verpasst haben, Instanzen zu deklarieren, die NULL-Werte nicht zulassen:

- Die Auflistung der Fragen sollte keine NULL-Werte zulassen.
- Die Auflistung der Antworten sollte keine NULL-Werte zulassen.

Wenn Sie den Code schreiben, werden Sie Folgendes feststellen: Indem Sie für Verweise standardmäßig einen Verweistyp verwenden, der keine NULL-Werte zulässt, lassen sich häufige Fehler vermeiden, die zu <xref:System.NullReferenceException>-Ergebnissen führen können. Eine Lektion aus diesem Tutorial ist, dass Sie entschieden haben, welche Variablen `null` sein könnten oder nicht. Die Sprache bot keine Syntax, um diese Entscheidungen auszudrücken. Jetzt ist es möglich.

Die von Ihnen erstellte App führt die folgenden Schritte aus:

1. Erstellen einer Umfrage und Hinzufügen von Fragen.
1. Erstellen eines pseudozufälligen Satzes von Befragten für die Umfrage.
1. Kontaktieren der Befragten, bis die Anzahl der abgeschlossen Umfragen den Zielwert erreicht hat.
1. Erstellen wichtiger Statistiken zu den Antworten.

## <a name="build-the-survey-with-nullable-and-non-nullable-reference-types"></a>Erstellen der Umfrage mit Nullable- und Nicht-Nullable-Verweistypen

Mit dem ersten geschriebenen Code erstellen Sie die Umfrage. Sie schreiben die Klassen, um eine Frage der Umfrage und eine Ausführung zu modellieren. Ihre Umfrage umfasst drei Arten von Fragen, die sich durch das Format der Antwort unterscheiden: Ja/Nein-Antworten, Zahlenantworten und Textantworten. Erstellen Sie eine `public SurveyQuestion`-Klasse:

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

Der Compiler interpretiert jede Verweistyp-Variablendeklaration für Code in einem aktivierten Nullable-Anmerkungskontext als **Nicht-Nullable-Verweistyp**. Sie können Ihre erste Warnung sehen, indem Sie Eigenschaften für den Fragetext und die Art der Frage hinzufügen, wie im folgenden Code gezeigt:

```csharp
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

Da Sie `QuestionText` noch nicht initialisiert haben, gibt der Compiler eine Warnung aus, dass noch keine Eigenschaft initialisiert wurde, nicht keine NULL-Werte zulässt. Ihr Entwurf verlangt, dass der Fragetext nicht null ist. Also fügen Sie einen Konstruktor zur Initialisierung und den Wert `QuestionType` hinzu. Die fertige Klassendefinition sieht wie im folgenden Code aus:

[!code-csharp[DefineQuestion](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

Durch das Hinzufügen des Konstruktors wird die Warnung entfernt. Das Konstruktorargument ebenfalls ein Verweistyp, der keine NULL-Werte zulässt. Der Compiler gibt also keine Warnungen aus.

Erstellen Sie eine `public`-Klasse mit dem Namen `SurveyRun`. Diese Klasse enthält eine Liste von `SurveyQuestion`-Objekten und Methoden, um Fragen zur Umfrage hinzuzufügen, wie im folgenden Code gezeigt:

```csharp
using System.Collections.Generic;

namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

Wie bisher müssen Sie das Listenobjekt Wert initialisieren, der keine NULL-Werte zulässt, oder der Compiler gibt eine Warnung aus. Es gibt keine NULL-Überprüfungen in der zweiten Überladung von `AddQuestion`, da sie nicht benötigt werden: Sie haben diese Variable als Typ deklariert, der keine NULL-Werte zulässt. Der Wert kann nicht `null` sein.

Wechseln Sie in Ihrem Editor zu *Program.cs*, und ersetzen Sie den Inhalt von `Main` durch die folgenden Codezeilen:

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

Da sich das gesamte Projekt in einem aktivierten Nullable-Anmerkungskontext befindet, erhalten Sie Warnungen, wenn Sie `null` in Erwartung eines Nicht-Nullable-Verweistyps an eine Methode übergeben. Probieren Sie es aus, indem Sie die folgende Zeile zu `Main` hinzufügen:

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a>Erstellen von Befragten und Erhalten von Antworten zur Umfrage

Schreiben Sie als Nächstes den Code, der Antworten für die Umfrage generiert. Dieser Prozess umfasst mehrere kleine Aufgaben:

1. Erstellen Sie eine Methode, die Antwortobjekte generiert. Diese repräsentieren die Personen, die um das Ausfüllen der Umfrage gebeten werden.
1. Erstellen Sie eine Logik, um zu simulieren, dass Sie die Fragen an einen Befragten stellen und Antworten sammeln, oder feststellen, dass ein Befragter nicht geantwortet hat.
1. Wiederholen Sie den Vorgang, bis genügend Befragten an der Umfrage teilgenommen haben.

Sie benötigen eine Klasse zum Darstellen einer Umfrageantwort. Fügen Sie diese jetzt hinzu. Aktivieren Sie Support für NULL-Werte. Fügen Sie eine `Id`-Eigenschaft und einen Konstruktor hinzu, der diese initialisiert, wie in folgendem Code dargestellt:

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

Fügen Sie als Nächstes eine `static`-Methode hinzu, um neuen Teilnehmer zu erstellen, indem Sie eine Zufalls-ID generieren:

[!code-csharp[GenerateRespondents](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

Die Hauptaufgabe dieser Klasse besteht darin, die Antworten für einen Teilnehmer auf die Fragen der Umfrage zu generieren. Diese Aufgabe umfasst einige Schritte:

1. Bitten Sie um die Teilnahme an der Umfrage. Wenn eine Person nicht einverstanden ist, geben Sie eine fehlende (oder Null) Antwort zurück.
1. Stellen Sie die einzelnen Fragen, und notieren Sie die Antwort. Jede Antwort kann auch nicht vorhanden (oder null) sein.

Fügen Sie der `SurveyResponse`-Klasse den folgenden Code hinzu:

[!code-csharp[AnswerSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

Der Speicher für Umfrageantworten ist eine `Dictionary<int, string>?`. Damit wird angegeben, dass auch NULL zulässig ist. Sie verwenden das neue Sprachfeature, um Ihre Entwurfsabsicht zu deklarieren, sowohl gegenüber dem Compiler als auch gegenüber allen, die Ihren Code später lesen. Wenn Sie jemals `surveyResponses` dereferenzieren, ohne zuerst nach dem `null`-Wert zu suchen, erhalten Sie eine Compilerwarnung. Sie erhalten keine Warnung in der `AnswerSurvey`-Methode, da der Compiler bestimmen kann, dass die Variable `surveyResponses` oben auf einen Wert gesetzt wurde, der NULL-Werte zulässt.

Die Verwendung von `null` für fehlende Antworten hebt einen wichtigen Punkt für die Arbeit mit NULL-Werte zulassenden Verweistypen hervor: Ihr Ziel ist nicht, alle `null`-Werte aus Ihrem Programm zu entfernen. Ihr Ziel ist eher, sicherzustellen, dass der Code, den Sie schreiben, Ihre Entwurfsabsicht ausdrückt. Fehlende Werte sind ein notwendiges in Ihrem Code auszudrückendes Konzept. Der `null`-Wert ist eine klare Möglichkeit, diese fehlenden Werte auszudrücken. Der Versuch, alle `null`-Werte zu entfernen, führt nur zum Definieren einer anderen Möglichkeit, diese fehlenden Werte ohne `null` auszudrücken.

Als Nächstes müssen Sie die `PerformSurvey`-Methode in der `SurveyRun`-Klasse schreiben. Fügen Sie den folgenden Code der `SurveyRun`-Klasse hinzu:

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

Auch hier geben Sie durch Ihre Auswahl von `List<SurveyResponse>?`, die NULL-Werte zulässt, dass die Antwort Null sein kann. Damit wird angegeben, dass die Umfrage noch keinem Befragten zugewiesen wurde. Beachten Sie, dass Personen hinzugefügt werden, bis genügend zugestimmt haben.

Der letzte Schritt zum Ausführen der Umfrage besteht darin, einen Aufruf zur Durchführung der Umfrage am Ende der `Main`-Methode hinzuzufügen:

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a>Untersuchen von Umfrageantworten

Der letzte Schritt ist das Anzeigen von Umfrageergebnissen. Sie fügen Code zu vielen der Klassen hinzu, die Sie geschrieben haben. Dieser Code demonstriert den Wert der Unterscheidung von Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen. Beginnen Sie, indem Sie die zwei folgenden Ausdruckskörpermember zur `SurveyResponse`-Klasse hinzufügen:

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

Da `surveyResponses` ein Verweistyp ist, der NULL-Werte zulässt, sind vor dem Dereferenzieren NULL-Überprüfungen erforderlich. Die `Answer`-Methode gibt eine Zeichenfolge zurück, die keine NULL-Werte zulässt. Daher müssen wir durch die Verwendung des NULL-Sammeloperators den Fall abdecken, dass eine Antwort fehlt.

Fügen Sie diese drei Ausdruckskörpermember zur `SurveyRun`-Klasse hinzu:

[!code-csharp[ReportResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

Das `AllParticipants` Member muss berücksichtigen, dass die `respondents`-Variable Null sein kann, der zurückgegebene Wert aber nicht Null sein darf. Wenn Sie diesen Ausdruck ändern, indem Sie `??` und die folgende leere Sequenz entfernen, warnt Sie der Compiler, dass die Methode `null` zurückgeben könnte, und ihre Rückgabesignatur gibt einen Typen zurück, der keine NULL-Werte zulässt.

Fügen Sie abschließend die folgende Schleife am Ende der `Main`-Methode hinzu:

[!code-csharp[DisplaySurveyResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

Sie benötigen keine `null`-Überprüfungen in diesem Code, das Sie die darunter liegenden Schnittstellen so entworfen haben, dass sie alle einen Verweistypen zurückgeben, der keine NULL-Werte zulässt.

## <a name="get-the-code"></a>Abrufen des Codes

Sie können den Code für das abgeschlossene Tutorial aus unserem [samples](https://github.com/dotnet/samples)-Repository im Ordner [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) abrufen.

Experimentieren Sie, indem Sie bei der Typdeklaration zwischen Verweistypen wechseln, die NULL-Werte zulassen bzw. nicht zulassen. Sehen Sie sich an, wie dabei verschiedene Warnungen erzeugt werden, um sicherzustellen, dass Sie nicht versehentlich`null` dereferenzieren.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen erhalten Sie durch die Migration einer vorhandenen Anwendung zur Verwendung NULL-Werte zulassender Verweistypen:
> [!div class="nextstepaction"]
> [Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen](upgrade-to-nullable-references.md)

Hier erfahren Sie, wie Sie Nullable-Verweistypen bei Verwendung von Entity Framework nutzen:
> [Grundlagen von Entity Framework Core: Verwenden von Nullable-Verweistypen](/ef/core/miscellaneous/nullable-reference-types)
