---
title: Entwerfen mit Verweistypen, die NULL-Werte zulassen
description: Dieses erweiterte Tutorial enthält eine Einführung zu Verweistypen, die NULL-Werte zulassen. Sie erfahren, wie Sie Ihre Entwurfsabsicht ausdrücken, wenn die Verweiswerte Null sein können, und wie Sie den Compiler durchsetzen, wenn sie nicht NULL sein können.
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: eec0c54c041db98595202ab982494df6ae3f743c
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204768"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="86311-104">Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="86311-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="86311-105">C# 8 führt **Verweistypen, die NULL-Werte zulassen** ein, die Verweistypen auf die gleiche Weise ergänzen, wie NULL-Werte zulassenden Werttypen Werttypen ergänzen.</span><span class="sxs-lookup"><span data-stu-id="86311-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="86311-106">Sie deklarieren eine Variable zu einem **Verweistyp, der NULL-Werte zulässt**, indem Sie `?` an den Typen anfügen.</span><span class="sxs-lookup"><span data-stu-id="86311-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="86311-107">Beispielsweise stellt `string?` eine `string` dar, die NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="86311-108">Mit diesen neuen Typen können Sie Ihre Entwurfsabsicht besser zum Ausdruck bringen: Einige Variablen *müssen immer einen Wert* haben, bei anderen  *kann ein Wert fehlen*.</span><span class="sxs-lookup"><span data-stu-id="86311-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="86311-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="86311-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="86311-110">Integrieren von Verweistypen, die NULL-Werte zulassen und nicht zulassen, in Ihre Entwürfe.</span><span class="sxs-lookup"><span data-stu-id="86311-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="86311-111">Aktivieren von Überprüfungen Ihres Verweistypen, der NULL-Werte zulässt, anhand Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="86311-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="86311-112">Schreiben von Code, bei dem ein Compiler diese Entwurfsentscheidungen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="86311-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="86311-113">Verwenden des Verweisfeatures, das NULL-Werte zulässt, in Ihren eigenen Entwürfen.</span><span class="sxs-lookup"><span data-stu-id="86311-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86311-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="86311-114">Prerequisites</span></span>

<span data-ttu-id="86311-115">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich dem C# 8.0-Beta-Compiler.</span><span class="sxs-lookup"><span data-stu-id="86311-115">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="86311-116">Der C# 8 Beta-Compiler ist mit [2019 für Visual Studio Vorschauversion 1](https://visualstudio.microsoft.com/vs/preview/) oder [.NET Core 3.0 Vorschauversion 1](https://dotnet.microsoft.com/download/dotnet-core/3.0) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86311-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="86311-117">In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.</span><span class="sxs-lookup"><span data-stu-id="86311-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="86311-118">Integrieren von Verweistypen, die NULL-Werte zulassen, in Ihre Entwürfe</span><span class="sxs-lookup"><span data-stu-id="86311-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="86311-119">In diesem Tutorial erstellen Sie eine Bibliothek, die die Ausführung einer Umfrage modelliert.</span><span class="sxs-lookup"><span data-stu-id="86311-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="86311-120">Der Code verwendet Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen, zur Darstellung der realen Konzepte.</span><span class="sxs-lookup"><span data-stu-id="86311-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="86311-121">Die Fragen in der Umfrage können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="86311-121">The survey questions can never be null.</span></span> <span data-ttu-id="86311-122">Ein Befragter möchte eine Frage möglicherweise nicht beantworten.</span><span class="sxs-lookup"><span data-stu-id="86311-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="86311-123">In diesem Fall können die Antworten NULL sein.</span><span class="sxs-lookup"><span data-stu-id="86311-123">The responses might be null in this case.</span></span>

<span data-ttu-id="86311-124">Der Code, den Sie für dieses Beispiel schreiben, drückt diese Absicht aus, und der Compiler setzt sie durch.</span><span class="sxs-lookup"><span data-stu-id="86311-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="86311-125">Erstellen der Anwendung und Aktivieren der Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="86311-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="86311-126">Erstellen Sie eine neue Konsolenanwendung in Visual Studio oder über die Befehlszeile mit `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="86311-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="86311-127">Nennen Sie die Anwendung `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="86311-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="86311-128">Nachdem Sie die Anwendung erstellt haben, müssen Sie C# 8 Betafeatures aktivieren.</span><span class="sxs-lookup"><span data-stu-id="86311-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="86311-129">Öffnen Sie die `csproj`-Datei, und fügen Sie dem `LangVersion`-Element ein `PropertyGroup`-Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="86311-129">Open the `csproj` file, and add a `LangVersion` element to the `PropertyGroup` element:</span></span>

```xml
<LangVersion>8.0</LangVersion>
```

<span data-ttu-id="86311-130">Alternativ können Sie die Visual Studio-Projekteigenschaften zum Aktivieren von C# 8 verwenden.</span><span class="sxs-lookup"><span data-stu-id="86311-130">Alternatively, you can use the Visual Studio project properties to enable C# 8.</span></span> <span data-ttu-id="86311-131">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="86311-131">In Solution Explorer, right click on the project node, select **Properties**.</span></span> <span data-ttu-id="86311-132">Wählen Sie dann die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste für die Sprachversion  **C# 8.0 (Beta)** aus.</span><span class="sxs-lookup"><span data-stu-id="86311-132">Then, select the **build** tab, and click **Advanced...**. In the dropdown for language version, select **C# 8.0 (beta)**.</span></span>

<span data-ttu-id="86311-133">Auch in C# 8-Projekten müssen Sie das Feature für **Verweistypen, die NULL-Werte zulassen** abonnieren.</span><span class="sxs-lookup"><span data-stu-id="86311-133">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="86311-134">Grund dafür ist, dass bestehende Verweisvariablendeklarationen nach dem Aktivieren des Features zu **Verweistypen werden, die NULL-Werte nicht zulassen**.</span><span class="sxs-lookup"><span data-stu-id="86311-134">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="86311-135">Diese Entscheidung ist zwar hilfreich, um Probleme zu finden, bei denen bestehender Code möglicherweise keine ordnungsgemäßen NULL-Überprüfungen aufweist, aber möglicherweise nicht genau Ihre ursprüngliche Entwurfsabsicht widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="86311-135">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="86311-136">Sie aktivieren das Feature mit einem neuen Pragma:</span><span class="sxs-lookup"><span data-stu-id="86311-136">You turn on the feature with a new pragma:</span></span>

```csharp
#nullable enable
```

<span data-ttu-id="86311-137">Sie können das vorhergehende Pragma überall in einer Quelldatei hinzufügen, und das Feature für den Verweistyp, der NULL-Werte zulässt, wird aktiviert.</span><span class="sxs-lookup"><span data-stu-id="86311-137">You can add the preceding pragma anywhere in a source file, and the nullable reference type feature is turned on from that point.</span></span> <span data-ttu-id="86311-138">Das Pragma unterstützt auch das `disable`-Argument zum Deaktivieren des Features.</span><span class="sxs-lookup"><span data-stu-id="86311-138">The pragma also supports the `disable` argument to turn off the feature.</span></span>

<span data-ttu-id="86311-139">Sie können **Verweistypen, die NULL-Werte zulassen** auch für ein ganzes Projekt aktivieren, indem Sie beispielsweise das folgende Element zu Ihrer .csproj-Datei hinzufügen, das unmittelbar auf das `LangVersion`-Element folgt, das C# 8.0 aktiviert hat:</span><span class="sxs-lookup"><span data-stu-id="86311-139">You can also turn on **nullable reference types** for an entire project by adding the following element to your .csproj file, for example, immediately following the `LangVersion` element that enabled C# 8.0:</span></span>

```xml
<NullableReferenceTypes>true</NullableReferenceTypes>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="86311-140">Entwerfen der Typen für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="86311-140">Design the types for the application</span></span>

<span data-ttu-id="86311-141">Für diese Umfrageanwendung müssen einige Klassen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="86311-141">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="86311-142">Eine Klasse, die die Liste der Fragen modelliert.</span><span class="sxs-lookup"><span data-stu-id="86311-142">A class that models the list of questions.</span></span>
- <span data-ttu-id="86311-143">Eine Klasse, die eine Liste der Personen modelliert, die für die Umfrage kontaktiert werden.</span><span class="sxs-lookup"><span data-stu-id="86311-143">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="86311-144">Eine Klasse, die die Antworten einer Person modelliert, die an der Umfrage teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="86311-144">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="86311-145">Diese Typen verwenden Verweistypen, die NULL-Werte sowohl zulassen als auch nicht zulassen, um auszudrücken, welche Member erforderlich und welche optional sind.</span><span class="sxs-lookup"><span data-stu-id="86311-145">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="86311-146">Verweistypen, die NULL-Werte zulassen, kommunizieren diese Entwurfsabsicht eindeutig:</span><span class="sxs-lookup"><span data-stu-id="86311-146">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="86311-147">Die Fragen, die Teil der Umfrage sind, können nie NULL sein. Es ist nicht sinnvoll, eine leere Frage zu stellen.</span><span class="sxs-lookup"><span data-stu-id="86311-147">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="86311-148">Die Befragten können nie NULL sein.</span><span class="sxs-lookup"><span data-stu-id="86311-148">The respondents can never be null.</span></span> <span data-ttu-id="86311-149">Sie werden sicher die Personen nachverfolgen wollen, mit denen Sie Kontakt aufgenommen haben, sogar die Personen, die die Teilnahme abgelehnt haben.</span><span class="sxs-lookup"><span data-stu-id="86311-149">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="86311-150">Jede Antwort auf eine Frage darf NULL sein.</span><span class="sxs-lookup"><span data-stu-id="86311-150">Any response to a question may be null.</span></span> <span data-ttu-id="86311-151">Befragten können es ablehnen, einige oder alle Fragen zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="86311-151">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="86311-152">Wenn Sie in C# programmiert haben, sind Sie vielleicht so sehr an gewöhnt, die NULL-Werte zulassen, dass Sie andere Möglichkeiten verpasst haben, Instanzen zu deklarieren, die NULL-Werte nicht zulassen:</span><span class="sxs-lookup"><span data-stu-id="86311-152">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="86311-153">Die Auflistung der Fragen sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-153">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="86311-154">Die Auflistung der Antworten sollte keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-154">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="86311-155">Wenn Sie den Code schreiben, werden Sie sehen, dass durch die standardmäßige Verwendung eines Verweistypen, der NULL-Werte nicht zulässt, für Referenzen, häufige Fehler vermieden werden, die zu Nullverweisausnahmen führen können.</span><span class="sxs-lookup"><span data-stu-id="86311-155">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="86311-156">Eine Lektion aus diesem Tutorial ist, dass Sie entschieden haben, welche Variablen NULL sein könnten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="86311-156">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="86311-157">Die Sprache bot keine Syntax, um diese Entscheidungen auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="86311-157">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="86311-158">Jetzt ist es möglich.</span><span class="sxs-lookup"><span data-stu-id="86311-158">Now it does.</span></span>

<span data-ttu-id="86311-159">Die von Ihnen erstellte Anwendung führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="86311-159">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="86311-160">Erstellen einer Umfrage und Hinzufügen von Fragen.</span><span class="sxs-lookup"><span data-stu-id="86311-160">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="86311-161">Erstellen eines pseudozufälligen Satzes von Befragten für die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="86311-161">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="86311-162">Kontaktieren der Befragten bis die Anzahl der abgeschlossen Umfragen den Zielwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="86311-162">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="86311-163">Aufstellen wichtiger Statistiken zu den Antworten.</span><span class="sxs-lookup"><span data-stu-id="86311-163">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="86311-164">Erstellen einer Umfrage mit Typen, die NULL-Werte zulassen und nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-164">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="86311-165">Mit dem ersten geschriebenen Code erstellen Sie die Umfrage.</span><span class="sxs-lookup"><span data-stu-id="86311-165">The first code you'll write creates the survey.</span></span> <span data-ttu-id="86311-166">Sie schreiben die Klassen, um eine Frage der Umfrage und eine Ausführung zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="86311-166">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="86311-167">Ihre Umfrage umfasst drei Arten von Fragen, die sich durch das Format der Antwort unterscheiden: Ja/Nein-Antworten, Zahlenantworten und Textantworten.</span><span class="sxs-lookup"><span data-stu-id="86311-167">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="86311-168">Erstellen Sie eine `public` `SurveyQuestion`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="86311-168">Create a `public` `SurveyQuestion` class.</span></span> <span data-ttu-id="86311-169">Binden Sie das `#nullable enable`-Pragma unmittelbar nach der `using`-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="86311-169">Include the `#nullable enable` pragma immediately after the `using` statements:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="86311-170">Das Hinzufügen des `#nullable enable`-Pragmas bedeutet, dass der Compiler jede Variablendeklaration des Verweistyps als Verweistyp interpretiert, der **NULL-Werte nicht zulässt**.</span><span class="sxs-lookup"><span data-stu-id="86311-170">Adding the `#nullable enable` pragma means the compiler interprets every reference type variable declaration as a **non-nullable** reference type.</span></span> <span data-ttu-id="86311-171">Sie können Ihre erste Warnung sehen, indem Sie Eigenschaften für den Fragetext und die Art der Frage hinzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="86311-171">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
#nullable enable
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

<span data-ttu-id="86311-172">Da Sie `QuestionText` noch nicht initialisiert haben, gibt der Compiler eine Warnung aus, dass noch keine Eigenschaft initialisiert wurde, nicht keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-172">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="86311-173">Ihr Entwurf verlangt, dass der Fragetext nicht null ist. Also fügen Sie einen Konstruktor zur Initialisierung und den Wert `QuestionType` hinzu.</span><span class="sxs-lookup"><span data-stu-id="86311-173">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="86311-174">Die fertige Klassendefinition sieht wie im folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="86311-174">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="86311-175">Durch das Hinzufügen des Konstruktors wird die Warnung entfernt.</span><span class="sxs-lookup"><span data-stu-id="86311-175">Adding the constructor removes the warning.</span></span> <span data-ttu-id="86311-176">Das Konstruktorargument ebenfalls ein Verweistyp, der keine NULL-Werte zulässt. Der Compiler gibt also keine Warnungen aus.</span><span class="sxs-lookup"><span data-stu-id="86311-176">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="86311-177">Erstellen Sie eine `public`-Klasse mit dem Namen `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="86311-177">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="86311-178">Binden Sie das `#nullable enable`-Pragma nach der `using`-Anweisungen ein.</span><span class="sxs-lookup"><span data-stu-id="86311-178">Include the `#nullable enable` pragma following the `using` statements.</span></span> <span data-ttu-id="86311-179">Diese Klasse enthält eine Liste von `SurveyQuestion`-Objekten und Methoden, um Fragen zur Umfrage hinzuzufügen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="86311-179">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

#nullable enable
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

<span data-ttu-id="86311-180">Wie bisher müssen Sie das Listenobjekt Wert initialisieren, der keine NULL-Werte zulässt, oder der Compiler gibt eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="86311-180">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="86311-181">Es gibt keine NULL-Überprüfungen in der zweiten Überladung von `AddQuestion`, da sie nicht benötigt werden: Sie haben diese Variable als Typ deklariert, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-181">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="86311-182">Der Wert kann nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="86311-182">Its value can't be `null`.</span></span>

<span data-ttu-id="86311-183">Wechseln Sie in Ihrem Editor zu `Program.cs`, und ersetzen Sie den Inhalt von `Main` durch die folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="86311-183">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="86311-184">Ohne das `#nullable enable`-Pragma am Anfang der Datei gibt der Compiler keine Warnung aus, wenn Sie `null` als Text für das `AddQuestion`-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="86311-184">Without the `#nullable enable` pragma at the top of the file, the compiler doesn't issue a warning when you pass `null` as the text for the `AddQuestion` argument.</span></span> <span data-ttu-id="86311-185">Dieses Problem können Sie beheben, indem Sie `#nullable enable` nach der `using`-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86311-185">Fix that by adding `#nullable enable` following the `using` statement.</span></span> <span data-ttu-id="86311-186">Probieren Sie es aus, indem Sie die folgende Zeile zu `Main` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="86311-186">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="86311-187">Erstellen von Befragten und Erhalten von Antworten zur Umfrage</span><span class="sxs-lookup"><span data-stu-id="86311-187">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="86311-188">Schreiben Sie als Nächstes den Code, der Antworten für die Umfrage generiert.</span><span class="sxs-lookup"><span data-stu-id="86311-188">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="86311-189">Dies umfasst mehrere kleine Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="86311-189">This involves several small tasks:</span></span>

1. <span data-ttu-id="86311-190">Erstellen Sie eine Methode, die Antwortobjekte generiert.</span><span class="sxs-lookup"><span data-stu-id="86311-190">Build a method that generates respondent objects.</span></span> <span data-ttu-id="86311-191">Diese repräsentieren die Personen, die um das Ausfüllen der Umfrage gebeten werden.</span><span class="sxs-lookup"><span data-stu-id="86311-191">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="86311-192">Erstellen Sie eine Logik, um zu simulieren, dass Sie die Fragen an einen Befragten stellen und Antworten sammeln, oder feststellen, dass ein Befragter nicht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="86311-192">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="86311-193">Wiederholen Sie den Vorgang, bis genügend Befragten an der Umfrage teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="86311-193">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="86311-194">Sie benötigen eine Klasse zum Darstellen einer Umfrageantwort. Fügen Sie diese jetzt hinzu.</span><span class="sxs-lookup"><span data-stu-id="86311-194">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="86311-195">Aktivieren Sie Support für NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="86311-195">Enable nullable support.</span></span> <span data-ttu-id="86311-196">Fügen Sie eine `Id`-Eigenschaft und einen Konstruktor hinzu, der diese initialisiert, wie in folgendem Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="86311-196">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="86311-197">Fügen Sie als Nächstes eine `static`-Methode hinzu, um neuen Teilnehmer zu erstellen, indem Sie eine Zufalls-ID generieren:</span><span class="sxs-lookup"><span data-stu-id="86311-197">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="86311-198">Die Hauptaufgabe dieser Klasse besteht darin, die Antworten für einen Teilnehmer auf die Fragen der Umfrage zu generieren.</span><span class="sxs-lookup"><span data-stu-id="86311-198">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="86311-199">Diese Aufgabe umfasst einige Schritte:</span><span class="sxs-lookup"><span data-stu-id="86311-199">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="86311-200">Bitten Sie um die Teilnahme an der Umfrage.</span><span class="sxs-lookup"><span data-stu-id="86311-200">Ask for participation in the survey.</span></span> <span data-ttu-id="86311-201">Wenn eine Person nicht einverstanden ist, geben Sie eine fehlende (oder Null) Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="86311-201">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="86311-202">Stellen Sie die einzelnen Fragen, und notieren Sie die Antwort.</span><span class="sxs-lookup"><span data-stu-id="86311-202">Ask each question and record the answer.</span></span> <span data-ttu-id="86311-203">Jede Antwort kann auch nicht vorhanden (oder null) sein.</span><span class="sxs-lookup"><span data-stu-id="86311-203">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="86311-204">Fügen Sie der `SurveyResponse`-Klasse den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="86311-204">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="86311-205">Der Speicher für Umfrageantworten ist eine `Dictionary<int, string>?`. Damit wird angegeben, dass auch NULL zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="86311-205">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="86311-206">Sie verwenden das neue Sprachfeature, um Ihre Entwurfsabsicht zu deklarieren, sowohl gegenüber dem Compiler als auch gegenüber allen, die Ihren Code später lesen.</span><span class="sxs-lookup"><span data-stu-id="86311-206">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="86311-207">Wenn Sie jemals `surveyResponses` dereferenzieren, ohne zuerst nach dem NULL-Wert zu suchen, erhalten Sie eine Compiler-Warnung.</span><span class="sxs-lookup"><span data-stu-id="86311-207">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="86311-208">Sie erhalten keine Warnung in der `AnswerSurvey`-Methode, da der Compiler bestimmen kann, dass die Variable `surveyResponses` oben auf einen Wert gesetzt wurde, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-208">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="86311-209">Als Nächstes müssen Sie die `PerformSurvey`-Methode in der `SurveyRun`-Klasse schreiben.</span><span class="sxs-lookup"><span data-stu-id="86311-209">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="86311-210">Fügen Sie den folgenden Code der `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="86311-210">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="86311-211">Auch hier geben Sie durch Ihre Auswahl von `List<SurveyResponse>?`, die NULL-Werte zulässt, dass die Antwort Null sein kann.</span><span class="sxs-lookup"><span data-stu-id="86311-211">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="86311-212">Damit wird angegeben, dass die Umfrage noch keinem Befragten zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="86311-212">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="86311-213">Beachten Sie, dass Personen hinzugefügt werden, bis genügend zugestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="86311-213">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="86311-214">Der letzte Schritt zum Ausführen der Umfrage besteht darin, einen Aufruf zur Durchführung der Umfrage am Ende der `Main`-Methode hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="86311-214">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="86311-215">Untersuchen von Umfrageantworten</span><span class="sxs-lookup"><span data-stu-id="86311-215">Examine survey responses</span></span>

<span data-ttu-id="86311-216">Der letzte Schritt ist das Anzeigen von Umfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="86311-216">The last step is to display survey results.</span></span> <span data-ttu-id="86311-217">Sie fügen Code zu vielen der Klassen hinzu, die Sie geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="86311-217">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="86311-218">Dieser Code demonstriert den Wert der Unterscheidung von Verweistypen, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-218">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="86311-219">Beginnen Sie, indem Sie die zwei folgenden Ausdruckskörpermember zur `SurveyResponse`-Klasse hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="86311-219">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="86311-220">Da `surveyResponses` ein Verweistyp ist, der keine NULL-Werte zulässt, sind vor dem Dereferenzieren keine Überprüfungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86311-220">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="86311-221">Die `Answer`-Methode gibt eine Zeichenfolge zurück, die keine NULL-Werte zulässt. Wählen Sie also die Überladung von `GetValueOrDefault`, bei der ein zweites Argument für den Standardwert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86311-221">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="86311-222">Fügen Sie diese drei Ausdruckskörpermember zur `SurveyRun`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="86311-222">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="86311-223">Das `AllParticipants` Member muss berücksichtigen, dass die `respondents`-Variable Null sein kann, der zurückgegebene Wert aber nicht Null sein darf.</span><span class="sxs-lookup"><span data-stu-id="86311-223">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="86311-224">Wenn Sie diesen Ausdruck ändern, indem Sie `??` und die folgende leere Sequenz entfernen, warnt Sie der Compiler, dass die Methode `null` zurückgeben könnte, und ihre Rückgabesignatur gibt einen Typen zurück, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-224">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="86311-225">Fügen Sie abschließend die folgende Schleife am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="86311-225">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="86311-226">Sie benötigen keine `null`-Überprüfungen in diesem Code, das Sie die darunter liegenden Schnittstellen so entworfen haben, dass sie alle einen Verweistypen zurückgeben, der keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="86311-226">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="86311-227">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="86311-227">Get the code</span></span>

<span data-ttu-id="86311-228">Sie können den Code für das abgeschlossene Tutorial aus unserem [samples](https://github.com/dotnet/samples)-Repository im Ordner [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) abrufen.</span><span class="sxs-lookup"><span data-stu-id="86311-228">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="86311-229">Experimentieren Sie, indem Sie bei der Typdeklaration zwischen Verweistypen wechseln, die NULL-Werte zulassen bzw. nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-229">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="86311-230">Sehen Sie sich an, wie dabei verschiedene Warnungen erzeugt werden, um sicherzustellen, dass Sie nicht versehentlich`null` dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="86311-230">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="86311-231">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="86311-231">Next steps</span></span>

<span data-ttu-id="86311-232">Erfahren Sie mehr, indem Sie sich eine Übersicht zu Verweistypen ansehen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="86311-232">Learn more by reading an overview of nullable reference types..</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="86311-233"> Übersicht zu Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="86311-233">An overview of nullable references</span></span>](../nullable-references.md)
