---
title: Entwerfen mit Verweistypen, die NULL-Werte zulassen
description: Dieses erweiterte Tutorial enthält eine Einführung zu Verweistypen, die NULL-Werte zulassen. Sie erfahren, wie Sie Ihre Entwurfsabsicht ausdrücken, wenn die Verweiswerte Null sein können, und wie Sie den Compiler durchsetzen, wenn sie nicht NULL sein können.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 3ee5e50cf889dd0e02bf58f1e3471fc709b729cd
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039716"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="97e31-104">Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="97e31-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="97e31-105">C# 8.0 führt [Nullable-Verweistypen](../nullable-references.md) ein, die Verweistypen auf die gleiche Weise ergänzen, wie Nullable-Werttypen Werttypen ergänzen.</span><span class="sxs-lookup"><span data-stu-id="97e31-105">C# 8.0 introduces [nullable reference types](../nullable-references.md), which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="97e31-106">Sie deklarieren eine Variable zu einem **Verweistyp, der NULL-Werte zulässt**, indem Sie `?` an den Typen anfügen.</span><span class="sxs-lookup"><span data-stu-id="97e31-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="97e31-107">Beispielsweise stellt `string?` eine `string` dar, die NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="97e31-108">Mit diesen neuen Typen können Sie Ihre Entwurfsabsicht besser zum Ausdruck bringen: Einige Variablen *müssen immer einen Wert* haben, bei anderen  *kann ein Wert fehlen*.</span><span class="sxs-lookup"><span data-stu-id="97e31-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="97e31-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="97e31-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="97e31-110">Integrieren von Verweistypen, die NULL-Werte zulassen und nicht zulassen, in Ihre Entwürfe.</span><span class="sxs-lookup"><span data-stu-id="97e31-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> - <span data-ttu-id="97e31-111">Aktivieren von Überprüfungen Ihres Verweistypen, der NULL-Werte zulässt, anhand Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="97e31-111">Enable nullable reference type checks throughout your code.</span></span>
> - <span data-ttu-id="97e31-112">Schreiben von Code, bei dem ein Compiler diese Entwurfsentscheidungen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="97e31-112">Write code where the compiler enforces those design decisions.</span></span>
> - <span data-ttu-id="97e31-113">Verwenden des Verweisfeatures, das NULL-Werte zulässt, in Ihren eigenen Entwürfen.</span><span class="sxs-lookup"><span data-stu-id="97e31-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97e31-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="97e31-114">Prerequisites</span></span>

<span data-ttu-id="97e31-115">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers.</span><span class="sxs-lookup"><span data-stu-id="97e31-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="97e31-116">Der C# 8.0-Compiler ist mit [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="97e31-116">The C# 8.0 compiler is available with [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="97e31-117">In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.</span><span class="sxs-lookup"><span data-stu-id="97e31-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="97e31-118">Integrieren von Verweistypen, die NULL-Werte zulassen, in Ihre Entwürfe</span><span class="sxs-lookup"><span data-stu-id="97e31-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="97e31-119">In diesem Tutorial erstellen Sie eine Bibliothek, die die Ausführung einer Umfrage modelliert.</span><span class="sxs-lookup"><span data-stu-id="97e31-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="97e31-120">Der Code verwendet Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen, zur Darstellung der realen Konzepte.</span><span class="sxs-lookup"><span data-stu-id="97e31-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="97e31-121">Die Fragen in der Umfrage können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-121">The survey questions can never be null.</span></span> <span data-ttu-id="97e31-122">Ein Befragter möchte eine Frage möglicherweise nicht beantworten.</span><span class="sxs-lookup"><span data-stu-id="97e31-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="97e31-123">In diesem Fall können die Antworten `null` sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-123">The responses might be `null` in this case.</span></span>

<span data-ttu-id="97e31-124">Der Code, den Sie für dieses Beispiel schreiben, drückt diese Absicht aus, und der Compiler setzt sie durch.</span><span class="sxs-lookup"><span data-stu-id="97e31-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="97e31-125">Erstellen der Anwendung und Aktivieren der Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="97e31-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="97e31-126">Erstellen Sie eine neue Konsolenanwendung in Visual Studio oder über die Befehlszeile mit `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="97e31-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="97e31-127">Nennen Sie die Anwendung `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="97e31-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="97e31-128">Nachdem Sie die Anwendung erstellt haben, müssen Sie angeben, dass das gesamte Projekt in einem aktivierten **Nullable-Anmerkungskontext** kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="97e31-128">Once you've created the application, you'll need to specify that the entire project compiles in an enabled **nullable annotation context**.</span></span> <span data-ttu-id="97e31-129">Öffnen Sie die *CSPROJ*-Datei, und fügen Sie dem `PropertyGroup`-Element ein `Nullable`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="97e31-129">Open the *.csproj* file and add a `Nullable` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="97e31-130">Legen Sie den Wert der Eigenschaft auf `enable`fest.</span><span class="sxs-lookup"><span data-stu-id="97e31-130">Set its value to `enable`.</span></span> <span data-ttu-id="97e31-131">Selbst in C# 8.0-Projekten müssen Sie das Feature für **Nullable-Verweistypen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="97e31-131">You must opt into the **nullable reference types** feature, even in C# 8.0 projects.</span></span> <span data-ttu-id="97e31-132">Grund dafür ist, dass bestehende Verweisvariablendeklarationen nach dem Aktivieren des Features zu **Verweistypen werden, die NULL-Werte nicht zulassen**.</span><span class="sxs-lookup"><span data-stu-id="97e31-132">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="97e31-133">Diese Entscheidung ist zwar hilfreich, um Probleme zu finden, bei denen bestehender Code möglicherweise keine ordnungsgemäßen NULL-Überprüfungen aufweist, aber möglicherweise spiegelt sie nicht genau Ihre ursprüngliche Entwurfsabsicht wider.</span><span class="sxs-lookup"><span data-stu-id="97e31-133">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent:</span></span>

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="97e31-134">Entwerfen der Typen für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="97e31-134">Design the types for the application</span></span>

<span data-ttu-id="97e31-135">Für diese Umfrageanwendung müssen einige Klassen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="97e31-135">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="97e31-136">Eine Klasse, die die Liste der Fragen modelliert.</span><span class="sxs-lookup"><span data-stu-id="97e31-136">A class that models the list of questions.</span></span>
- <span data-ttu-id="97e31-137">Eine Klasse, die eine Liste der Personen modelliert, die für die Umfrage kontaktiert werden.</span><span class="sxs-lookup"><span data-stu-id="97e31-137">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="97e31-138">Eine Klasse, die die Antworten einer Person modelliert, die an der Umfrage teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="97e31-138">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="97e31-139">Diese Typen verwenden Verweistypen, die NULL-Werte sowohl zulassen als auch nicht zulassen, um auszudrücken, welche Member erforderlich und welche optional sind.</span><span class="sxs-lookup"><span data-stu-id="97e31-139">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="97e31-140">Verweistypen, die NULL-Werte zulassen, kommunizieren diese Entwurfsabsicht eindeutig:</span><span class="sxs-lookup"><span data-stu-id="97e31-140">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="97e31-141">Die Fragen, die Teil der Umfrage sind, können nie NULL sein. Es ist nicht sinnvoll, eine leere Frage zu stellen.</span><span class="sxs-lookup"><span data-stu-id="97e31-141">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="97e31-142">Die Befragten können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-142">The respondents can never be null.</span></span> <span data-ttu-id="97e31-143">Sie werden sicher die Personen nachverfolgen wollen, mit denen Sie Kontakt aufgenommen haben, sogar die Personen, die die Teilnahme abgelehnt haben.</span><span class="sxs-lookup"><span data-stu-id="97e31-143">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="97e31-144">Jede Antwort auf eine Frage darf NULL sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-144">Any response to a question may be null.</span></span> <span data-ttu-id="97e31-145">Befragten können es ablehnen, einige oder alle Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="97e31-145">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="97e31-146">Wenn Sie in C# programmiert haben, sind Sie vielleicht so sehr an Verweistypen gewöhnt, die `null`-Werte zulassen, dass Sie andere Möglichkeiten verpasst haben, Instanzen zu deklarieren, die NULL-Werte nicht zulassen:</span><span class="sxs-lookup"><span data-stu-id="97e31-146">If you've programmed in C#, you may be so accustomed to reference types that allow `null` values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="97e31-147">Die Auflistung der Fragen sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="97e31-147">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="97e31-148">Die Auflistung der Antworten sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="97e31-148">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="97e31-149">Wenn Sie den Code schreiben, werden Sie Folgendes feststellen: Indem Sie für Verweise standardmäßig einen Verweistyp verwenden, der keine NULL-Werte zulässt, lassen sich häufige Fehler vermeiden, die zu <xref:System.NullReferenceException>-Ergebnissen führen können.</span><span class="sxs-lookup"><span data-stu-id="97e31-149">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to <xref:System.NullReferenceException>s.</span></span> <span data-ttu-id="97e31-150">Eine Lektion aus diesem Tutorial ist, dass Sie entschieden haben, welche Variablen `null` sein könnten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="97e31-150">One lesson from this tutorial is that you made decisions about which variables could or could not be `null`.</span></span> <span data-ttu-id="97e31-151">Die Sprache bot keine Syntax, um diese Entscheidungen auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="97e31-151">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="97e31-152">Jetzt ist es möglich.</span><span class="sxs-lookup"><span data-stu-id="97e31-152">Now it does.</span></span>

<span data-ttu-id="97e31-153">Die von Ihnen erstellte App führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="97e31-153">The app you'll build does the following steps:</span></span>

1. <span data-ttu-id="97e31-154">Erstellen einer Umfrage und Hinzufügen von Fragen.</span><span class="sxs-lookup"><span data-stu-id="97e31-154">Creates a survey and adds questions to it.</span></span>
1. <span data-ttu-id="97e31-155">Erstellen eines pseudozufälligen Satzes von Befragten für die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="97e31-155">Creates a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="97e31-156">Kontaktieren der Befragten, bis die Anzahl der abgeschlossen Umfragen den Zielwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="97e31-156">Contacts respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="97e31-157">Erstellen wichtiger Statistiken zu den Antworten.</span><span class="sxs-lookup"><span data-stu-id="97e31-157">Writes out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="97e31-158">Erstellen einer Umfrage mit Typen, die NULL-Werte zulassen und nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="97e31-158">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="97e31-159">Mit dem ersten geschriebenen Code erstellen Sie die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="97e31-159">The first code you'll write creates the survey.</span></span> <span data-ttu-id="97e31-160">Sie schreiben die Klassen, um eine Frage der Umfrage und eine Ausführung zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="97e31-160">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="97e31-161">Ihre Umfrage umfasst drei Arten von Fragen, die sich durch das Format der Antwort unterscheiden: Ja/Nein-Antworten, Zahlenantworten und Textantworten.</span><span class="sxs-lookup"><span data-stu-id="97e31-161">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="97e31-162">Erstellen Sie eine `public SurveyQuestion`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="97e31-162">Create a `public SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="97e31-163">Der Compiler interpretiert jede Verweistyp-Variablendeklaration für Code in einem aktivierten Nullable-Anmerkungskontext als **Nicht-Nullable-Verweistyp**.</span><span class="sxs-lookup"><span data-stu-id="97e31-163">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in an enabled nullable annotation context.</span></span> <span data-ttu-id="97e31-164">Sie können Ihre erste Warnung sehen, indem Sie Eigenschaften für den Fragetext und die Art der Frage hinzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="97e31-164">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

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

<span data-ttu-id="97e31-165">Da Sie `QuestionText` noch nicht initialisiert haben, gibt der Compiler eine Warnung aus, dass noch keine Eigenschaft initialisiert wurde, nicht keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-165">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="97e31-166">Ihr Entwurf verlangt, dass der Fragetext nicht null ist. Also fügen Sie einen Konstruktor zur Initialisierung und den Wert `QuestionType` hinzu.</span><span class="sxs-lookup"><span data-stu-id="97e31-166">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="97e31-167">Die fertige Klassendefinition sieht wie im folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="97e31-167">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="97e31-168">Durch das Hinzufügen des Konstruktors wird die Warnung entfernt.</span><span class="sxs-lookup"><span data-stu-id="97e31-168">Adding the constructor removes the warning.</span></span> <span data-ttu-id="97e31-169">Das Konstruktorargument ebenfalls ein Verweistyp, der keine NULL-Werte zulässt. Der Compiler gibt also keine Warnungen aus.</span><span class="sxs-lookup"><span data-stu-id="97e31-169">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="97e31-170">Erstellen Sie eine `public`-Klasse mit dem Namen `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="97e31-170">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="97e31-171">Diese Klasse enthält eine Liste von `SurveyQuestion`-Objekten und Methoden, um Fragen zur Umfrage hinzuzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="97e31-171">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

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

<span data-ttu-id="97e31-172">Wie bisher müssen Sie das Listenobjekt Wert initialisieren, der keine NULL-Werte zulässt, oder der Compiler gibt eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="97e31-172">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="97e31-173">Es gibt keine NULL-Überprüfungen in der zweiten Überladung von `AddQuestion`, da sie nicht benötigt werden: Sie haben diese Variable als Typ deklariert, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-173">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="97e31-174">Der Wert kann nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-174">Its value can't be `null`.</span></span>

<span data-ttu-id="97e31-175">Wechseln Sie in Ihrem Editor zu *Program.cs*, und ersetzen Sie den Inhalt von `Main` durch die folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="97e31-175">Switch to *Program.cs* in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="97e31-176">Da sich das gesamte Projekt in einem aktivierten Nullable-Anmerkungskontext befindet, erhalten Sie Warnungen, wenn Sie `null` in Erwartung eines Nicht-Nullable-Verweistyps an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="97e31-176">Because the entire project is in an enabled nullable annotation context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="97e31-177">Probieren Sie es aus, indem Sie die folgende Zeile zu `Main` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="97e31-177">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="97e31-178">Erstellen von Befragten und Erhalten von Antworten zur Umfrage</span><span class="sxs-lookup"><span data-stu-id="97e31-178">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="97e31-179">Schreiben Sie als Nächstes den Code, der Antworten für die Umfrage generiert.</span><span class="sxs-lookup"><span data-stu-id="97e31-179">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="97e31-180">Dieser Prozess umfasst mehrere kleine Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="97e31-180">This process involves several small tasks:</span></span>

1. <span data-ttu-id="97e31-181">Erstellen Sie eine Methode, die Antwortobjekte generiert.</span><span class="sxs-lookup"><span data-stu-id="97e31-181">Build a method that generates respondent objects.</span></span> <span data-ttu-id="97e31-182">Diese repräsentieren die Personen, die um das Ausfüllen der Umfrage gebeten werden.</span><span class="sxs-lookup"><span data-stu-id="97e31-182">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="97e31-183">Erstellen Sie eine Logik, um zu simulieren, dass Sie die Fragen an einen Befragten stellen und Antworten sammeln, oder feststellen, dass ein Befragter nicht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="97e31-183">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="97e31-184">Wiederholen Sie den Vorgang, bis genügend Befragten an der Umfrage teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="97e31-184">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="97e31-185">Sie benötigen eine Klasse zum Darstellen einer Umfrageantwort. Fügen Sie diese jetzt hinzu.</span><span class="sxs-lookup"><span data-stu-id="97e31-185">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="97e31-186">Aktivieren Sie Support für NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="97e31-186">Enable nullable support.</span></span> <span data-ttu-id="97e31-187">Fügen Sie eine `Id`-Eigenschaft und einen Konstruktor hinzu, der diese initialisiert, wie in folgendem Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="97e31-187">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

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

<span data-ttu-id="97e31-188">Fügen Sie als Nächstes eine `static`-Methode hinzu, um neuen Teilnehmer zu erstellen, indem Sie eine Zufalls-ID generieren:</span><span class="sxs-lookup"><span data-stu-id="97e31-188">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="97e31-189">Die Hauptaufgabe dieser Klasse besteht darin, die Antworten für einen Teilnehmer auf die Fragen der Umfrage zu generieren.</span><span class="sxs-lookup"><span data-stu-id="97e31-189">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="97e31-190">Diese Aufgabe umfasst einige Schritte:</span><span class="sxs-lookup"><span data-stu-id="97e31-190">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="97e31-191">Bitten Sie um die Teilnahme an der Umfrage.</span><span class="sxs-lookup"><span data-stu-id="97e31-191">Ask for participation in the survey.</span></span> <span data-ttu-id="97e31-192">Wenn eine Person nicht einverstanden ist, geben Sie eine fehlende (oder Null) Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="97e31-192">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="97e31-193">Stellen Sie die einzelnen Fragen, und notieren Sie die Antwort.</span><span class="sxs-lookup"><span data-stu-id="97e31-193">Ask each question and record the answer.</span></span> <span data-ttu-id="97e31-194">Jede Antwort kann auch nicht vorhanden (oder null) sein.</span><span class="sxs-lookup"><span data-stu-id="97e31-194">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="97e31-195">Fügen Sie der `SurveyResponse`-Klasse den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="97e31-195">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="97e31-196">Der Speicher für Umfrageantworten ist eine `Dictionary<int, string>?`. Damit wird angegeben, dass auch NULL zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="97e31-196">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="97e31-197">Sie verwenden das neue Sprachfeature, um Ihre Entwurfsabsicht zu deklarieren, sowohl gegenüber dem Compiler als auch gegenüber allen, die Ihren Code später lesen.</span><span class="sxs-lookup"><span data-stu-id="97e31-197">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="97e31-198">Wenn Sie jemals `surveyResponses` dereferenzieren, ohne zuerst nach dem `null`-Wert zu suchen, erhalten Sie eine Compilerwarnung.</span><span class="sxs-lookup"><span data-stu-id="97e31-198">If you ever dereference `surveyResponses` without checking for the `null` value first, you'll get a compiler warning.</span></span> <span data-ttu-id="97e31-199">Sie erhalten keine Warnung in der `AnswerSurvey`-Methode, da der Compiler bestimmen kann, dass die Variable `surveyResponses` oben auf einen Wert gesetzt wurde, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-199">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="97e31-200">Die Verwendung von `null` für fehlende Antworten hebt einen wichtigen Punkt für die Arbeit mit NULL-Werte zulassenden Verweistypen hervor: Ihr Ziel ist nicht, alle `null`-Werte aus Ihrem Programm zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="97e31-200">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="97e31-201">Ihr Ziel ist eher, sicherzustellen, dass der Code, den Sie schreiben, Ihre Entwurfsabsicht ausdrückt.</span><span class="sxs-lookup"><span data-stu-id="97e31-201">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="97e31-202">Fehlende Werte sind ein notwendiges in Ihrem Code auszudrückendes Konzept.</span><span class="sxs-lookup"><span data-stu-id="97e31-202">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="97e31-203">Der `null`-Wert ist eine klare Möglichkeit, diese fehlenden Werte auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="97e31-203">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="97e31-204">Der Versuch, alle `null`-Werte zu entfernen, führt nur zum Definieren einer anderen Möglichkeit, diese fehlenden Werte ohne `null` auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="97e31-204">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="97e31-205">Als Nächstes müssen Sie die `PerformSurvey`-Methode in der `SurveyRun`-Klasse schreiben.</span><span class="sxs-lookup"><span data-stu-id="97e31-205">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="97e31-206">Fügen Sie den folgenden Code der `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="97e31-206">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="97e31-207">Auch hier geben Sie durch Ihre Auswahl von `List<SurveyResponse>?`, die NULL-Werte zulässt, dass die Antwort Null sein kann.</span><span class="sxs-lookup"><span data-stu-id="97e31-207">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="97e31-208">Damit wird angegeben, dass die Umfrage noch keinem Befragten zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="97e31-208">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="97e31-209">Beachten Sie, dass Personen hinzugefügt werden, bis genügend zugestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="97e31-209">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="97e31-210">Der letzte Schritt zum Ausführen der Umfrage besteht darin, einen Aufruf zur Durchführung der Umfrage am Ende der `Main`-Methode hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="97e31-210">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="97e31-211">Untersuchen von Umfrageantworten</span><span class="sxs-lookup"><span data-stu-id="97e31-211">Examine survey responses</span></span>

<span data-ttu-id="97e31-212">Der letzte Schritt ist das Anzeigen von Umfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="97e31-212">The last step is to display survey results.</span></span> <span data-ttu-id="97e31-213">Sie fügen Code zu vielen der Klassen hinzu, die Sie geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="97e31-213">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="97e31-214">Dieser Code demonstriert den Wert der Unterscheidung von Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="97e31-214">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="97e31-215">Beginnen Sie, indem Sie die zwei folgenden Ausdruckskörpermember zur `SurveyResponse`-Klasse hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="97e31-215">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="97e31-216">Da `surveyResponses` ein Verweistyp ist, der NULL-Werte zulässt, sind vor dem Dereferenzieren NULL-Überprüfungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97e31-216">Because `surveyResponses` is a nullable reference type, null checks are necessary before de-referencing it.</span></span> <span data-ttu-id="97e31-217">Die `Answer`-Methode gibt eine Zeichenfolge zurück, die keine NULL-Werte zulässt. Daher müssen wir durch die Verwendung des NULL-Sammeloperators den Fall abdecken, dass eine Antwort fehlt.</span><span class="sxs-lookup"><span data-stu-id="97e31-217">The `Answer` method returns a non-nullable string, so we have to cover the case of a missing answer by using the null-coalescing operator.</span></span>

<span data-ttu-id="97e31-218">Fügen Sie diese drei Ausdruckskörpermember zur `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="97e31-218">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](~/samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="97e31-219">Das `AllParticipants` Member muss berücksichtigen, dass die `respondents`-Variable Null sein kann, der zurückgegebene Wert aber nicht Null sein darf.</span><span class="sxs-lookup"><span data-stu-id="97e31-219">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="97e31-220">Wenn Sie diesen Ausdruck ändern, indem Sie `??` und die folgende leere Sequenz entfernen, warnt Sie der Compiler, dass die Methode `null` zurückgeben könnte, und ihre Rückgabesignatur gibt einen Typen zurück, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-220">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="97e31-221">Fügen Sie abschließend die folgende Schleife am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="97e31-221">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](~/samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="97e31-222">Sie benötigen keine `null`-Überprüfungen in diesem Code, das Sie die darunter liegenden Schnittstellen so entworfen haben, dass sie alle einen Verweistypen zurückgeben, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="97e31-222">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="97e31-223">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="97e31-223">Get the code</span></span>

<span data-ttu-id="97e31-224">Sie können den Code für das abgeschlossene Tutorial aus unserem [samples](https://github.com/dotnet/samples)-Repository im Ordner [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) abrufen.</span><span class="sxs-lookup"><span data-stu-id="97e31-224">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="97e31-225">Experimentieren Sie, indem Sie bei der Typdeklaration zwischen Verweistypen wechseln, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="97e31-225">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="97e31-226">Sehen Sie sich an, wie dabei verschiedene Warnungen erzeugt werden, um sicherzustellen, dass Sie nicht versehentlich`null` dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="97e31-226">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="97e31-227">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="97e31-227">Next steps</span></span>

<span data-ttu-id="97e31-228">Weitere Informationen erhalten Sie durch die Migration einer vorhandenen Anwendung zur Verwendung NULL-Werte zulassender Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="97e31-228">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="97e31-229">Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="97e31-229">Upgrade an application to use nullable reference types</span></span>](upgrade-to-nullable-references.md)
