---
title: Entwerfen mit Verweistypen, die NULL-Werte zulassen
description: Dieses erweiterte Tutorial enthält eine Einführung zu Verweistypen, die NULL-Werte zulassen. Sie erfahren, wie Sie Ihre Entwurfsabsicht ausdrücken, wenn die Verweiswerte Null sein können, und wie Sie den Compiler durchsetzen, wenn sie nicht NULL sein können.
ms.date: 02/19/2019
ms.custom: mvc
ms.openlocfilehash: 6b127cce66f2f9ced3cee29336b39e2976e03619
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332347"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="9706f-104">Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="9706f-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="9706f-105">C# 8 führt **Verweistypen, die NULL-Werte zulassen** ein, die Verweistypen auf die gleiche Weise ergänzen, wie NULL-Werte zulassenden Werttypen Werttypen ergänzen.</span><span class="sxs-lookup"><span data-stu-id="9706f-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="9706f-106">Sie deklarieren eine Variable zu einem **Verweistyp, der NULL-Werte zulässt**, indem Sie `?` an den Typen anfügen.</span><span class="sxs-lookup"><span data-stu-id="9706f-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="9706f-107">Beispielsweise stellt `string?` eine `string` dar, die NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="9706f-108">Mit diesen neuen Typen können Sie Ihre Entwurfsabsicht besser zum Ausdruck bringen: Einige Variablen *müssen immer einen Wert* haben, bei anderen  *kann ein Wert fehlen*.</span><span class="sxs-lookup"><span data-stu-id="9706f-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="9706f-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9706f-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9706f-110">Integrieren von Verweistypen, die NULL-Werte zulassen und nicht zulassen, in Ihre Entwürfe.</span><span class="sxs-lookup"><span data-stu-id="9706f-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> - <span data-ttu-id="9706f-111">Aktivieren von Überprüfungen Ihres Verweistypen, der NULL-Werte zulässt, anhand Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="9706f-111">Enable nullable reference type checks throughout your code.</span></span>
> - <span data-ttu-id="9706f-112">Schreiben von Code, bei dem ein Compiler diese Entwurfsentscheidungen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="9706f-112">Write code where the compiler enforces those design decisions.</span></span>
> - <span data-ttu-id="9706f-113">Verwenden des Verweisfeatures, das NULL-Werte zulässt, in Ihren eigenen Entwürfen.</span><span class="sxs-lookup"><span data-stu-id="9706f-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9706f-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="9706f-114">Prerequisites</span></span>

<span data-ttu-id="9706f-115">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0 Beta-Compilers.</span><span class="sxs-lookup"><span data-stu-id="9706f-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="9706f-116">Der C# 8 Beta-Compiler ist mit [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9706f-116">The C# 8 beta compiler is available with [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="9706f-117">In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.</span><span class="sxs-lookup"><span data-stu-id="9706f-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="9706f-118">Integrieren von Verweistypen, die NULL-Werte zulassen, in Ihre Entwürfe</span><span class="sxs-lookup"><span data-stu-id="9706f-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="9706f-119">In diesem Tutorial erstellen Sie eine Bibliothek, die die Ausführung einer Umfrage modelliert.</span><span class="sxs-lookup"><span data-stu-id="9706f-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="9706f-120">Der Code verwendet Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen, zur Darstellung der realen Konzepte.</span><span class="sxs-lookup"><span data-stu-id="9706f-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="9706f-121">Die Fragen in der Umfrage können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-121">The survey questions can never be null.</span></span> <span data-ttu-id="9706f-122">Ein Befragter möchte eine Frage möglicherweise nicht beantworten.</span><span class="sxs-lookup"><span data-stu-id="9706f-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="9706f-123">In diesem Fall können die Antworten NULL sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-123">The responses might be null in this case.</span></span>

<span data-ttu-id="9706f-124">Der Code, den Sie für dieses Beispiel schreiben, drückt diese Absicht aus, und der Compiler setzt sie durch.</span><span class="sxs-lookup"><span data-stu-id="9706f-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="9706f-125">Erstellen der Anwendung und Aktivieren der Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="9706f-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="9706f-126">Erstellen Sie eine neue Konsolenanwendung in Visual Studio oder über die Befehlszeile mit `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="9706f-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="9706f-127">Nennen Sie die Anwendung `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="9706f-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="9706f-128">Nachdem Sie die Anwendung erstellt haben, müssen Sie C# 8 Betafeatures aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9706f-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="9706f-129">Öffnen Sie die `csproj`-Datei, und fügen Sie dem `LangVersion`-Element ein `PropertyGroup`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="9706f-129">Open the `csproj` file and add a `LangVersion` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="9706f-130">Auch in C# 8-Projekten müssen Sie das Feature für **Verweistypen, die NULL-Werte zulassen** abonnieren.</span><span class="sxs-lookup"><span data-stu-id="9706f-130">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="9706f-131">Grund dafür ist, dass bestehende Verweisvariablendeklarationen nach dem Aktivieren des Features zu **Verweistypen werden, die NULL-Werte nicht zulassen**.</span><span class="sxs-lookup"><span data-stu-id="9706f-131">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="9706f-132">Diese Entscheidung ist zwar hilfreich, um Probleme zu finden, bei denen bestehender Code möglicherweise keine ordnungsgemäßen NULL-Überprüfungen aufweist, aber möglicherweise nicht genau Ihre ursprüngliche Entwurfsabsicht widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="9706f-132">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="9706f-133">Um das Feature zu aktivieren, legen Sie für das `Nullable`-Element `enable` fest:</span><span class="sxs-lookup"><span data-stu-id="9706f-133">You turn on the feature by setting the `Nullable` element to `enable`:</span></span>

```xml
<LangVersion>8.0</LangVersion>
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="9706f-134">Entwerfen der Typen für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="9706f-134">Design the types for the application</span></span>

<span data-ttu-id="9706f-135">Für diese Umfrageanwendung müssen einige Klassen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="9706f-135">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="9706f-136">Eine Klasse, die die Liste der Fragen modelliert.</span><span class="sxs-lookup"><span data-stu-id="9706f-136">A class that models the list of questions.</span></span>
- <span data-ttu-id="9706f-137">Eine Klasse, die eine Liste der Personen modelliert, die für die Umfrage kontaktiert werden.</span><span class="sxs-lookup"><span data-stu-id="9706f-137">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="9706f-138">Eine Klasse, die die Antworten einer Person modelliert, die an der Umfrage teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="9706f-138">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="9706f-139">Diese Typen verwenden Verweistypen, die NULL-Werte sowohl zulassen als auch nicht zulassen, um auszudrücken, welche Member erforderlich und welche optional sind.</span><span class="sxs-lookup"><span data-stu-id="9706f-139">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="9706f-140">Verweistypen, die NULL-Werte zulassen, kommunizieren diese Entwurfsabsicht eindeutig:</span><span class="sxs-lookup"><span data-stu-id="9706f-140">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="9706f-141">Die Fragen, die Teil der Umfrage sind, können nie NULL sein. Es ist nicht sinnvoll, eine leere Frage zu stellen.</span><span class="sxs-lookup"><span data-stu-id="9706f-141">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="9706f-142">Die Befragten können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-142">The respondents can never be null.</span></span> <span data-ttu-id="9706f-143">Sie werden sicher die Personen nachverfolgen wollen, mit denen Sie Kontakt aufgenommen haben, sogar die Personen, die die Teilnahme abgelehnt haben.</span><span class="sxs-lookup"><span data-stu-id="9706f-143">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="9706f-144">Jede Antwort auf eine Frage darf NULL sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-144">Any response to a question may be null.</span></span> <span data-ttu-id="9706f-145">Befragten können es ablehnen, einige oder alle Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="9706f-145">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="9706f-146">Wenn Sie in C# programmiert haben, sind Sie vielleicht so sehr an gewöhnt, die NULL-Werte zulassen, dass Sie andere Möglichkeiten verpasst haben, Instanzen zu deklarieren, die NULL-Werte nicht zulassen:</span><span class="sxs-lookup"><span data-stu-id="9706f-146">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="9706f-147">Die Auflistung der Fragen sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="9706f-147">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="9706f-148">Die Auflistung der Antworten sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="9706f-148">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="9706f-149">Wenn Sie den Code schreiben, werden Sie sehen, dass durch die standardmäßige Verwendung eines Verweistypen, der NULL-Werte nicht zulässt, für Referenzen, häufige Fehler vermieden werden, die zu Nullverweisausnahmen führen können.</span><span class="sxs-lookup"><span data-stu-id="9706f-149">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="9706f-150">Eine Lektion aus diesem Tutorial ist, dass Sie entschieden haben, welche Variablen NULL sein könnten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9706f-150">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="9706f-151">Die Sprache bot keine Syntax, um diese Entscheidungen auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="9706f-151">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="9706f-152">Jetzt ist es möglich.</span><span class="sxs-lookup"><span data-stu-id="9706f-152">Now it does.</span></span>

<span data-ttu-id="9706f-153">Die von Ihnen erstellte Anwendung führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9706f-153">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="9706f-154">Erstellen einer Umfrage und Hinzufügen von Fragen.</span><span class="sxs-lookup"><span data-stu-id="9706f-154">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="9706f-155">Erstellen eines pseudozufälligen Satzes von Befragten für die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="9706f-155">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="9706f-156">Kontaktieren der Befragten bis die Anzahl der abgeschlossen Umfragen den Zielwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="9706f-156">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="9706f-157">Aufstellen wichtiger Statistiken zu den Antworten.</span><span class="sxs-lookup"><span data-stu-id="9706f-157">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="9706f-158">Erstellen einer Umfrage mit Typen, die NULL-Werte zulassen und nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="9706f-158">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="9706f-159">Mit dem ersten geschriebenen Code erstellen Sie die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="9706f-159">The first code you'll write creates the survey.</span></span> <span data-ttu-id="9706f-160">Sie schreiben die Klassen, um eine Frage der Umfrage und eine Ausführung zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="9706f-160">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="9706f-161">Ihre Umfrage umfasst drei Arten von Fragen, die sich durch das Format der Antwort unterscheiden: Ja/Nein-Antworten, Zahlenantworten und Textantworten.</span><span class="sxs-lookup"><span data-stu-id="9706f-161">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="9706f-162">Erstellen Sie eine `public` `SurveyQuestion`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="9706f-162">Create a `public` `SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="9706f-163">Der Compiler interpretiert jede Verweistyp-Variablendeklaration als Verweistyp, der **NULL-Werte nicht zulässt**, für Code in einem NULL-Werte zulassenden Kontext.</span><span class="sxs-lookup"><span data-stu-id="9706f-163">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in a nullable enabled context.</span></span> <span data-ttu-id="9706f-164">Sie können Ihre erste Warnung sehen, indem Sie Eigenschaften für den Fragetext und die Art der Frage hinzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9706f-164">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

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

<span data-ttu-id="9706f-165">Da Sie `QuestionText` noch nicht initialisiert haben, gibt der Compiler eine Warnung aus, dass noch keine Eigenschaft initialisiert wurde, nicht keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-165">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="9706f-166">Ihr Entwurf verlangt, dass der Fragetext nicht null ist. Also fügen Sie einen Konstruktor zur Initialisierung und den Wert `QuestionType` hinzu.</span><span class="sxs-lookup"><span data-stu-id="9706f-166">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="9706f-167">Die fertige Klassendefinition sieht wie im folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="9706f-167">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="9706f-168">Durch das Hinzufügen des Konstruktors wird die Warnung entfernt.</span><span class="sxs-lookup"><span data-stu-id="9706f-168">Adding the constructor removes the warning.</span></span> <span data-ttu-id="9706f-169">Das Konstruktorargument ebenfalls ein Verweistyp, der keine NULL-Werte zulässt. Der Compiler gibt also keine Warnungen aus.</span><span class="sxs-lookup"><span data-stu-id="9706f-169">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="9706f-170">Erstellen Sie eine `public`-Klasse mit dem Namen `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="9706f-170">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="9706f-171">Diese Klasse enthält eine Liste von `SurveyQuestion`-Objekten und Methoden, um Fragen zur Umfrage hinzuzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9706f-171">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

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

<span data-ttu-id="9706f-172">Wie bisher müssen Sie das Listenobjekt Wert initialisieren, der keine NULL-Werte zulässt, oder der Compiler gibt eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="9706f-172">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="9706f-173">Es gibt keine NULL-Überprüfungen in der zweiten Überladung von `AddQuestion`, da sie nicht benötigt werden: Sie haben diese Variable als Typ deklariert, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-173">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="9706f-174">Der Wert kann nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-174">Its value can't be `null`.</span></span>

<span data-ttu-id="9706f-175">Wechseln Sie in Ihrem Editor zu `Program.cs`, und ersetzen Sie den Inhalt von `Main` durch die folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="9706f-175">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="9706f-176">Da das gesamte Projekt in einem NULL-Werte zulassenden Kontext aktiviert ist, erhalten Sie Warnungen, wenn Sie `null` in Erwartung eines NULL-Werte nicht zulassenden Verweistyps an eine Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="9706f-176">Because the entire project is in a nullable enabled context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="9706f-177">Probieren Sie es aus, indem Sie die folgende Zeile zu `Main` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9706f-177">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="9706f-178">Erstellen von Befragten und Erhalten von Antworten zur Umfrage</span><span class="sxs-lookup"><span data-stu-id="9706f-178">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="9706f-179">Schreiben Sie als Nächstes den Code, der Antworten für die Umfrage generiert.</span><span class="sxs-lookup"><span data-stu-id="9706f-179">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="9706f-180">Dieser Prozess umfasst mehrere kleine Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="9706f-180">This process involves several small tasks:</span></span>

1. <span data-ttu-id="9706f-181">Erstellen Sie eine Methode, die Antwortobjekte generiert.</span><span class="sxs-lookup"><span data-stu-id="9706f-181">Build a method that generates respondent objects.</span></span> <span data-ttu-id="9706f-182">Diese repräsentieren die Personen, die um das Ausfüllen der Umfrage gebeten werden.</span><span class="sxs-lookup"><span data-stu-id="9706f-182">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="9706f-183">Erstellen Sie eine Logik, um zu simulieren, dass Sie die Fragen an einen Befragten stellen und Antworten sammeln, oder feststellen, dass ein Befragter nicht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="9706f-183">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="9706f-184">Wiederholen Sie den Vorgang, bis genügend Befragten an der Umfrage teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="9706f-184">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="9706f-185">Sie benötigen eine Klasse zum Darstellen einer Umfrageantwort. Fügen Sie diese jetzt hinzu.</span><span class="sxs-lookup"><span data-stu-id="9706f-185">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="9706f-186">Aktivieren Sie Support für NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="9706f-186">Enable nullable support.</span></span> <span data-ttu-id="9706f-187">Fügen Sie eine `Id`-Eigenschaft und einen Konstruktor hinzu, der diese initialisiert, wie in folgendem Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9706f-187">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

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

<span data-ttu-id="9706f-188">Fügen Sie als Nächstes eine `static`-Methode hinzu, um neuen Teilnehmer zu erstellen, indem Sie eine Zufalls-ID generieren:</span><span class="sxs-lookup"><span data-stu-id="9706f-188">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="9706f-189">Die Hauptaufgabe dieser Klasse besteht darin, die Antworten für einen Teilnehmer auf die Fragen der Umfrage zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9706f-189">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="9706f-190">Diese Aufgabe umfasst einige Schritte:</span><span class="sxs-lookup"><span data-stu-id="9706f-190">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="9706f-191">Bitten Sie um die Teilnahme an der Umfrage.</span><span class="sxs-lookup"><span data-stu-id="9706f-191">Ask for participation in the survey.</span></span> <span data-ttu-id="9706f-192">Wenn eine Person nicht einverstanden ist, geben Sie eine fehlende (oder Null) Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="9706f-192">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="9706f-193">Stellen Sie die einzelnen Fragen, und notieren Sie die Antwort.</span><span class="sxs-lookup"><span data-stu-id="9706f-193">Ask each question and record the answer.</span></span> <span data-ttu-id="9706f-194">Jede Antwort kann auch nicht vorhanden (oder null) sein.</span><span class="sxs-lookup"><span data-stu-id="9706f-194">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="9706f-195">Fügen Sie der `SurveyResponse`-Klasse den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="9706f-195">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="9706f-196">Der Speicher für Umfrageantworten ist eine `Dictionary<int, string>?`. Damit wird angegeben, dass auch NULL zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9706f-196">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="9706f-197">Sie verwenden das neue Sprachfeature, um Ihre Entwurfsabsicht zu deklarieren, sowohl gegenüber dem Compiler als auch gegenüber allen, die Ihren Code später lesen.</span><span class="sxs-lookup"><span data-stu-id="9706f-197">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="9706f-198">Wenn Sie jemals `surveyResponses` dereferenzieren, ohne zuerst nach dem NULL-Wert zu suchen, erhalten Sie eine Compiler-Warnung.</span><span class="sxs-lookup"><span data-stu-id="9706f-198">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="9706f-199">Sie erhalten keine Warnung in der `AnswerSurvey`-Methode, da der Compiler bestimmen kann, dass die Variable `surveyResponses` oben auf einen Wert gesetzt wurde, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-199">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="9706f-200">Die Verwendung von `null` für fehlende Antworten hebt einen wichtigen Punkt für die Arbeit mit NULL-Werte zulassenden Verweistypen hervor: Ihr Ziel ist nicht, alle `null`-Werte aus Ihrem Programm zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9706f-200">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="9706f-201">Ihr Ziel ist eher, sicherzustellen, dass der Code, den Sie schreiben, Ihre Entwurfsabsicht ausdrückt.</span><span class="sxs-lookup"><span data-stu-id="9706f-201">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="9706f-202">Fehlende Werte sind ein notwendiges in Ihrem Code auszudrückendes Konzept.</span><span class="sxs-lookup"><span data-stu-id="9706f-202">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="9706f-203">Der `null`-Wert ist eine klare Möglichkeit, diese fehlenden Werte auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="9706f-203">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="9706f-204">Der Versuch, alle `null`-Werte zu entfernen, führt nur zum Definieren einer anderen Möglichkeit, diese fehlenden Werte ohne `null` auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="9706f-204">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="9706f-205">Als Nächstes müssen Sie die `PerformSurvey`-Methode in der `SurveyRun`-Klasse schreiben.</span><span class="sxs-lookup"><span data-stu-id="9706f-205">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="9706f-206">Fügen Sie den folgenden Code der `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="9706f-206">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="9706f-207">Auch hier geben Sie durch Ihre Auswahl von `List<SurveyResponse>?`, die NULL-Werte zulässt, dass die Antwort Null sein kann.</span><span class="sxs-lookup"><span data-stu-id="9706f-207">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="9706f-208">Damit wird angegeben, dass die Umfrage noch keinem Befragten zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9706f-208">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="9706f-209">Beachten Sie, dass Personen hinzugefügt werden, bis genügend zugestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="9706f-209">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="9706f-210">Der letzte Schritt zum Ausführen der Umfrage besteht darin, einen Aufruf zur Durchführung der Umfrage am Ende der `Main`-Methode hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="9706f-210">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="9706f-211">Untersuchen von Umfrageantworten</span><span class="sxs-lookup"><span data-stu-id="9706f-211">Examine survey responses</span></span>

<span data-ttu-id="9706f-212">Der letzte Schritt ist das Anzeigen von Umfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="9706f-212">The last step is to display survey results.</span></span> <span data-ttu-id="9706f-213">Sie fügen Code zu vielen der Klassen hinzu, die Sie geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="9706f-213">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="9706f-214">Dieser Code demonstriert den Wert der Unterscheidung von Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="9706f-214">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="9706f-215">Beginnen Sie, indem Sie die zwei folgenden Ausdruckskörpermember zur `SurveyResponse`-Klasse hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9706f-215">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="9706f-216">Da `surveyResponses` ein Verweistyp ist, der keine NULL-Werte zulässt, sind vor dem Dereferenzieren keine Überprüfungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9706f-216">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="9706f-217">Die `Answer`-Methode gibt eine Zeichenfolge zurück, die keine NULL-Werte zulässt. Wählen Sie also die Überladung von `GetValueOrDefault`, bei der ein zweites Argument für den Standardwert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9706f-217">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="9706f-218">Fügen Sie diese drei Ausdruckskörpermember zur `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="9706f-218">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="9706f-219">Das `AllParticipants` Member muss berücksichtigen, dass die `respondents`-Variable Null sein kann, der zurückgegebene Wert aber nicht Null sein darf.</span><span class="sxs-lookup"><span data-stu-id="9706f-219">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="9706f-220">Wenn Sie diesen Ausdruck ändern, indem Sie `??` und die folgende leere Sequenz entfernen, warnt Sie der Compiler, dass die Methode `null` zurückgeben könnte, und ihre Rückgabesignatur gibt einen Typen zurück, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-220">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="9706f-221">Fügen Sie abschließend die folgende Schleife am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="9706f-221">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="9706f-222">Sie benötigen keine `null`-Überprüfungen in diesem Code, das Sie die darunter liegenden Schnittstellen so entworfen haben, dass sie alle einen Verweistypen zurückgeben, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9706f-222">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="9706f-223">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="9706f-223">Get the code</span></span>

<span data-ttu-id="9706f-224">Sie können den Code für das abgeschlossene Tutorial aus unserem [samples](https://github.com/dotnet/samples)-Repository im Ordner [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) abrufen.</span><span class="sxs-lookup"><span data-stu-id="9706f-224">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="9706f-225">Experimentieren Sie, indem Sie bei der Typdeklaration zwischen Verweistypen wechseln, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="9706f-225">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="9706f-226">Sehen Sie sich an, wie dabei verschiedene Warnungen erzeugt werden, um sicherzustellen, dass Sie nicht versehentlich`null` dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="9706f-226">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9706f-227">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9706f-227">Next steps</span></span>

<span data-ttu-id="9706f-228">Weitere Informationen erhalten Sie durch die Migration einer vorhandenen Anwendung zur Verwendung NULL-Werte zulassender Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="9706f-228">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9706f-229">Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="9706f-229">Upgrade an application to use nullable reference types</span></span>](upgrade-to-nullable-references.md)
