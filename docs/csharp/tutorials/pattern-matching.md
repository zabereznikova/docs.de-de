---
title: Verwenden von Features für den Musterabgleich, um Datentypen zu erweitern
description: Dieses fortgeschrittene Tutorial veranschaulicht die Verwendung von Musterabgleichverfahren zum Erstellen von Funktionen mit Daten und Algorithmen, die separat erstellt werden.
ms.date: 03/13/2019
ms-technology: csharp-whats-new
ms.custom: mvc
ms.openlocfilehash: df1054d8e0ec2b2539e6a1d00bf353d8ca927397
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156531"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="9613a-103">Tutorial: Verwenden von Features für den Musterabgleich, um Datentypen zu erweitern</span><span class="sxs-lookup"><span data-stu-id="9613a-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="9613a-104">Mit C# 7 wurden einfache Funktionen für den Musterabgleich eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9613a-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="9613a-105">Diese Funktionen werden in C# 8 mit neuen Ausdrücken und Mustern erweitert.</span><span class="sxs-lookup"><span data-stu-id="9613a-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="9613a-106">Sie können Funktionen schreiben, die sich verhalten, als würden Sie Typen erweitern, die sich möglicherweise in anderen Bibliotheken befinden.</span><span class="sxs-lookup"><span data-stu-id="9613a-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="9613a-107">Ein weiterer Verwendungszweck für Muster ist die Erstellung von Funktionalität, die Ihre Anwendung erfordert, und die keine grundlegende Funktion des erweiterten Typs ist.</span><span class="sxs-lookup"><span data-stu-id="9613a-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="9613a-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9613a-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9613a-109">Erkennen von Situationen, in denen ein Musterabgleich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9613a-109">Recognize situations where pattern matching should be used.</span></span>
> - <span data-ttu-id="9613a-110">Verwenden von Musterabgleichausdrücken, um Verhalten auf Grundlage von Typen und Eigenschaftswerten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9613a-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> - <span data-ttu-id="9613a-111">Kombinieren des Musterabgleichs mit anderen Verfahren, um vollständige Algorithmen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9613a-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9613a-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9613a-112">Prerequisites</span></span>

<span data-ttu-id="9613a-113">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers.</span><span class="sxs-lookup"><span data-stu-id="9613a-113">You’ll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="9613a-114">Der C# 8-Compiler steht ab [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9613a-114">The C# 8 compiler is available starting with [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="9613a-115">In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.</span><span class="sxs-lookup"><span data-stu-id="9613a-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="9613a-116">Szenarien für den Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="9613a-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="9613a-117">Moderne Entwicklung umfasst häufig die Integration von Daten aus mehreren Quellen und die Darstellung von aus diesen Daten gewonnenen Informationen und Einblicken in einer einzelnen zusammenhängenden Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9613a-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="9613a-118">Sie und Ihr Team haben nicht die Kontrolle über oder den Zugriff auf alle Typen, die die eingehenden Daten darstellen.</span><span class="sxs-lookup"><span data-stu-id="9613a-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="9613a-119">Der klassische objektorientierte Entwurf würde das Erstellen von Typen in Ihrer Anwendung fordern, die alle Datentypen aus diesen unterschiedlichen Quellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="9613a-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="9613a-120">Dann würde Ihre Anwendung mit diesen neuen Typen arbeiten, Vererbungshierarchien erstellen, virtuelle Methoden erstellen und Abstraktionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="9613a-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="9613a-121">Diese Verfahren funktionieren, und manchmal sind sie die besten Tools.</span><span class="sxs-lookup"><span data-stu-id="9613a-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="9613a-122">In anderen Fällen können Sie weniger Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="9613a-122">Other times you can write less code.</span></span> <span data-ttu-id="9613a-123">Sie können mehr klaren Code mithilfe von Verfahren schreiben, die die Daten von den Vorgängen trennen, die diese Daten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9613a-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="9613a-124">In diesem Tutorial erstellen und untersuchen Sie eine Anwendung, die eingehende Daten aus mehreren externen Quellen für ein einzelnes Szenario entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="9613a-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="9613a-125">Sie sehen, wie **Musterabgleich** eine effiziente Möglichkeit bietet, diese Daten auf Arten zu nutzen und zu verarbeiten, die nicht Teil des ursprünglichen Systems waren.</span><span class="sxs-lookup"><span data-stu-id="9613a-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="9613a-126">Stellen Sie sich eine bedeutende Metropolenregion vor, die für die Verwaltung des Verkehrs Mautgebühren und spezielle Preise für Spitzenzeiten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9613a-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="9613a-127">Sie schreiben eine Anwendung, die Mautgebühren für ein Fahrzeug basierend auf seinem Typ berechnet.</span><span class="sxs-lookup"><span data-stu-id="9613a-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="9613a-128">In späteren Verbesserungen wird die Preisgestaltung auf Basis der Anzahl der Fahrzeuginsassen integriert.</span><span class="sxs-lookup"><span data-stu-id="9613a-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="9613a-129">Bei weiteren Verbesserungen kommt die Preisgestaltung auf Basis der Tageszeit und des Wochentages hinzu.</span><span class="sxs-lookup"><span data-stu-id="9613a-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="9613a-130">Vielleicht haben Sie aufgrund dieser kurzen Beschreibung schnell eine Objekthierarchie skizziert, mit der Sie ein Modell dieses System erstellen würden.</span><span class="sxs-lookup"><span data-stu-id="9613a-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="9613a-131">Allerdings kommen Ihre Daten aus mehreren Quellen, z.B. anderen Verwaltungssystemen zur Fahrzeugregistrierung.</span><span class="sxs-lookup"><span data-stu-id="9613a-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="9613a-132">Diese Systeme bieten verschiedene Klassen zum Erstellen eines Modells aus diesen Daten, und Sie haben kein einzelnes Objektmodell, das Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9613a-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="9613a-133">In diesem Tutorial werden Sie mit diesen vereinfachten Klassen ein Modell für die Fahrzeugdaten aus diesen externen Systemen erstellen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9613a-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="9613a-134">Sie können den Startercode aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) auf GitHub herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9613a-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="9613a-135">Sie sehen, dass die Fahrzeugklassen aus verschiedenen Systemen stammen und sich in verschiedenen Namespaces befinden.</span><span class="sxs-lookup"><span data-stu-id="9613a-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="9613a-136">Keine gemeinsame Basisklasse außer `System.Object` kann genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="9613a-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="9613a-137">Musterabgleichentwürfe</span><span class="sxs-lookup"><span data-stu-id="9613a-137">Pattern matching designs</span></span>

<span data-ttu-id="9613a-138">Das Szenario in diesem Tutorial hebt die Arten von Problemen hervor, für deren Lösung Musterabgleiche gut geeignet sind:</span><span class="sxs-lookup"><span data-stu-id="9613a-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well-suited to solve:</span></span>

- <span data-ttu-id="9613a-139">Die Objekte, mit denen Sie arbeiten müssen, befinden sich nicht in einer Objekthierarchie, die Ihren Zielen entspricht.</span><span class="sxs-lookup"><span data-stu-id="9613a-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="9613a-140">Sie arbeiten möglicherweise mit Klassen, die zu nicht verbundenen Systemen gehören.</span><span class="sxs-lookup"><span data-stu-id="9613a-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="9613a-141">Die Funktionalität, die Sie hinzufügen, ist nicht Teil der Kernabstraktion für diese Klassen.</span><span class="sxs-lookup"><span data-stu-id="9613a-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="9613a-142">Die für ein Fahrzeug gezahlte Maut *ändert sich* für verschiedene Arten von Fahrzeugen, aber die Maut ist keine Kernfunktion des Fahrzeugs.</span><span class="sxs-lookup"><span data-stu-id="9613a-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="9613a-143">Wenn die *Form* der Daten und die mit diesen Daten durchgeführten *Vorgänge* nicht zusammen beschrieben werden, erleichtern die Musterabgleichfunktionen in C# die Arbeit mit ihnen.</span><span class="sxs-lookup"><span data-stu-id="9613a-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="9613a-144">Implementieren der grundlegenden Mautberechnungen</span><span class="sxs-lookup"><span data-stu-id="9613a-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="9613a-145">Die grundlegendsten Mautberechnungen basieren nur auf dem Fahrzeugtyp:</span><span class="sxs-lookup"><span data-stu-id="9613a-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="9613a-146">Ein `Car` zahlt 2,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="9613a-147">Ein `Taxi` zahlt 3,50 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="9613a-148">Ein `Bus` zahlt 5,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="9613a-149">Ein `DeliveryTruck` zahlt 10,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="9613a-150">Erstellen Sie eine neue `TollCalculator`-Klasse, und implementieren Sie einen Musterabgleich nach dem Fahrzeugtyp, um den Mautbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="9613a-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="9613a-151">Im folgenden Codebeispiel wird die ursprüngliche Implementierung der `TollCalculator`-Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9613a-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="9613a-152">Der vorherige Code verwendet einen **Switch-Ausdruck** (nicht zu verwechseln mit einer [`switch`](../language-reference/keywords/switch.md)-Anweisung), der das **Typmuster** testet.</span><span class="sxs-lookup"><span data-stu-id="9613a-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="9613a-153">Ein **Switch-Ausdruck** beginnt mit der Variablen – `vehicle` im vorangehenden Code – gefolgt vom `switch`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9613a-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="9613a-154">Als Nächstes folgen alle **Switch-Arme** in geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="9613a-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="9613a-155">Der `switch`-Ausdruck nimmt andere Überarbeitungen an der Syntax vor, die die `switch`-Anweisung umgibt.</span><span class="sxs-lookup"><span data-stu-id="9613a-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="9613a-156">Das `case`-Schlüsselwort wird ausgelassen, und das Ergebnis jedes einzelnen Arms ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9613a-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="9613a-157">Die letzten beiden Arme zeigen eine neue Sprachfunktion.</span><span class="sxs-lookup"><span data-stu-id="9613a-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="9613a-158">Der `{ }`-Fall entspricht jedem Objekt ungleich NULL, das nicht mit einem früheren Arm übereinstimmte.</span><span class="sxs-lookup"><span data-stu-id="9613a-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="9613a-159">Diese Arm fängt alle an diese Methode übergebenen falschen Typen ab.</span><span class="sxs-lookup"><span data-stu-id="9613a-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="9613a-160">Der `{ }`-Fall muss den Fällen für jeden Fahrzeugtyp folgen.</span><span class="sxs-lookup"><span data-stu-id="9613a-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="9613a-161">Wenn die Reihenfolge umgekehrt werden würde, hätte der `{ }`-Fall Vorrang.</span><span class="sxs-lookup"><span data-stu-id="9613a-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="9613a-162">Zum Schluss erkennt das `null`-Muster die Übergabe von `null` an diese Methode.</span><span class="sxs-lookup"><span data-stu-id="9613a-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="9613a-163">Das `null`-Muster kann an letzter Stelle stehen, da die anderen Typmuster nur mit einem Objekt ungleich NULL des richtigen Typs übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9613a-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="9613a-164">Sie können diesen Code mit folgendem Code in `Program.cs` testen:</span><span class="sxs-lookup"><span data-stu-id="9613a-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="9613a-165">Dieser Code befindet sich im Startprojekt, ist aber auskommentiert. Entfernen Sie die Kommentarmarkierungen, und Sie können testen, was Sie geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="9613a-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="9613a-166">Sie sehen jetzt, wie Muster Ihnen helfen können, Algorithmen zu erstellen, bei denen Code und Daten getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="9613a-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="9613a-167">Der `switch`-Ausdruck testet den Typ und produziert auf der Grundlage der Ergebnisse unterschiedliche Werte.</span><span class="sxs-lookup"><span data-stu-id="9613a-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="9613a-168">Aber das ist nur der Anfang.</span><span class="sxs-lookup"><span data-stu-id="9613a-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="9613a-169">Hinzufügen der Preisgestaltung nach Belegung</span><span class="sxs-lookup"><span data-stu-id="9613a-169">Add occupancy pricing</span></span>

<span data-ttu-id="9613a-170">Die Mautbehörde möchte, dass die Fahrzeuge maximal ausgelastet werden.</span><span class="sxs-lookup"><span data-stu-id="9613a-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="9613a-171">Sie hat entschieden, mehr zu verlangen, wenn sich weniger Fahrgäste in Fahrzeugen befinden, und bei vollständig gefüllten Fahrzeugen reduzierte Preise zu bieten:</span><span class="sxs-lookup"><span data-stu-id="9613a-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="9613a-172">PKWs und Taxis ohne Fahrgäste zahlen einen Aufschlag von 0,50 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="9613a-173">PKWs und Taxis mit zwei Fahrgästen erhalten einen Rabatt von 0,50 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-173">Cars and taxis with two passengers get a $0.50 discount.</span></span>
- <span data-ttu-id="9613a-174">PKWs und Taxis mit mindestens drei Fahrgästen erhalten einen Rabatt von 1,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="9613a-175">Busse, die zu weniger als 50% gefüllt sind, zahlen einen Aufschlag von 2,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="9613a-176">Busse, die zu mehr als 90% ausgelastet sind, erhalten einen Rabatt von 1,00 US-Dollar.</span><span class="sxs-lookup"><span data-stu-id="9613a-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="9613a-177">Diese Regeln können mit dem **Eigenschaftenmuster** im gleichen Switch-Ausdruck implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9613a-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="9613a-178">Das Eigenschaftenmuster untersucht Eigenschaften des Objekts, nachdem der Typ bestimmt wurde.</span><span class="sxs-lookup"><span data-stu-id="9613a-178">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="9613a-179">Der einzelne Fall eines `Car` wird auf vier verschiedene Fälle erweitert:</span><span class="sxs-lookup"><span data-stu-id="9613a-179">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="9613a-180">Die ersten drei Fällen testen den Typ als `Car` und überprüfen dann den Wert der `Passengers`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9613a-180">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="9613a-181">Wenn beide übereinstimmen, wird dieser Ausdruck ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9613a-181">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="9613a-182">Sie würden auch die Fälle für Taxis auf ähnliche Weise erweitern:</span><span class="sxs-lookup"><span data-stu-id="9613a-182">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="9613a-183">Im vorherigen Beispiel wurde die `when`-Klausel im letzten Fall weggelassen.</span><span class="sxs-lookup"><span data-stu-id="9613a-183">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="9613a-184">Implementieren Sie als Nächstes die Belegungsregeln durch Erweitern der Fälle für Busse, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9613a-184">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="9613a-185">Die Mautbehörde interessiert sich nicht für die Anzahl der Fahrgäste in Lieferwagen.</span><span class="sxs-lookup"><span data-stu-id="9613a-185">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="9613a-186">Stattdessen passt sie die Mauthöhe basierend auf der Gewichtsklasse der Lieferwagen wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="9613a-186">Instead, they adjust the toll amount based on the weight class of the trucks as follows:</span></span>

- <span data-ttu-id="9613a-187">Lieferwagen über 2,3 t wird ein Aufschlag von 5,00 US-Dollar berechnet.</span><span class="sxs-lookup"><span data-stu-id="9613a-187">Trucks over 5000 lbs are charged an extra $5.00.</span></span>
- <span data-ttu-id="9613a-188">Leichte Lieferwagen unter 1,35 t (3.000 Pfund) erhalten einen Rabatt von 2,00 USD.</span><span class="sxs-lookup"><span data-stu-id="9613a-188">Light trucks under 3000 lbs are given a $2.00 discount.</span></span>

<span data-ttu-id="9613a-189">Diese Regel wird mit folgendem Code implementiert:</span><span class="sxs-lookup"><span data-stu-id="9613a-189">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="9613a-190">Im vorherigen Code sehen Sie die `when`-Klausel eines switch-Arms.</span><span class="sxs-lookup"><span data-stu-id="9613a-190">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="9613a-191">Mit der `when`-Klausel testen Sie andere Bedingungen einer Eigenschaft als Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="9613a-191">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="9613a-192">Wenn Sie damit fertig sind, haben Sie eine Methode, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="9613a-192">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,

    { }     => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
    null    => throw new ArgumentNullException(nameof(vehicle))
};
```

<span data-ttu-id="9613a-193">Viele dieser Switch-Arme sind Beispiele für **rekursive Muster**.</span><span class="sxs-lookup"><span data-stu-id="9613a-193">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="9613a-194">`Car { Passengers: 1}` zeigt z.B. ein konstantes Muster in einem Eigenschaftenmuster an.</span><span class="sxs-lookup"><span data-stu-id="9613a-194">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="9613a-195">Sie können mit geschachtelten Switches die Wiederholungen in diesem Code reduzieren.</span><span class="sxs-lookup"><span data-stu-id="9613a-195">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="9613a-196">`Car` und `Taxi` weisen in den vorherigen Beispielen jeweils vier verschiedene Arme auf.</span><span class="sxs-lookup"><span data-stu-id="9613a-196">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="9613a-197">In beiden Fällen können Sie ein Typmuster erstellen, das in einem Eigenschaftenmuster mündet.</span><span class="sxs-lookup"><span data-stu-id="9613a-197">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="9613a-198">Dieses Verfahren wird im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9613a-198">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="9613a-199">Im vorherigen Beispiel folgt aus der Verwendung eines rekursiven Ausdrucks, dass Sie nicht die Arme `Car` und `Taxi` wiederholen, die untergeordnete Arme enthalten, die den Wert der Eigenschaft testen.</span><span class="sxs-lookup"><span data-stu-id="9613a-199">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="9613a-200">Dieses Verfahren wird nicht für die Arme `Bus` und `DeliveryTruck` verwendet, da diese Arme Bereiche für die Eigenschaft testen, nicht diskrete Werte.</span><span class="sxs-lookup"><span data-stu-id="9613a-200">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="9613a-201">Hinzufügen der Preisgestaltung für Spitzenzeiten</span><span class="sxs-lookup"><span data-stu-id="9613a-201">Add peak pricing</span></span>

<span data-ttu-id="9613a-202">Für das letzte Feature möchte die Mautbehörde die zeitabhängige Preisgestaltung für Spitzenzeiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9613a-202">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="9613a-203">Während der morgendlichen und abendlichen Hauptverkehrszeiten werden die Mautgebühren verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="9613a-203">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="9613a-204">Diese Regel betrifft nur den Verkehr in einer Richtung: am Morgen den stadteinwärts und am Abend den stadtauswärts gehenden Verkehr.</span><span class="sxs-lookup"><span data-stu-id="9613a-204">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="9613a-205">Während anderer Zeiten werden die Mautgebühren werktags um 50% heraufgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9613a-205">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="9613a-206">Am späten Abend und frühen Morgen werden die Mautgebühren um 25% verringert.</span><span class="sxs-lookup"><span data-stu-id="9613a-206">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="9613a-207">Am Wochenende gelten unabhängig von der Zeit die normalen Gebühren.</span><span class="sxs-lookup"><span data-stu-id="9613a-207">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="9613a-208">Sie verwenden den Musterabgleich für dieses Feature, aber Sie integrieren es mit anderen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="9613a-208">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="9613a-209">Sie könnten einen einzelnen Musterabgleichausdruck erstellen, der alle Kombinationen von Richtung, Wochentag und Zeit berücksichtigen würde.</span><span class="sxs-lookup"><span data-stu-id="9613a-209">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="9613a-210">Das Ergebnis wäre ein komplizierter Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9613a-210">The result would be a complicated expression.</span></span> <span data-ttu-id="9613a-211">Er wäre schwierig zu lesen und schwer zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="9613a-211">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="9613a-212">Dies erschwert, die Richtigkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="9613a-212">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="9613a-213">Kombinieren Sie stattdessen diese Methoden, um ein Tupel von Werten zu erstellen, das alle diese Zustände präzise beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9613a-213">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="9613a-214">Berechnen Sie mithilfe des Musterabgleichs einen Multiplikator für die Maut.</span><span class="sxs-lookup"><span data-stu-id="9613a-214">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="9613a-215">Das Tupel enthält drei diskrete Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="9613a-215">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="9613a-216">Der Tag ist entweder ein Wochentag oder fällt auf ein Wochenende.</span><span class="sxs-lookup"><span data-stu-id="9613a-216">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="9613a-217">Der Zeitbereich, in dem die Maut erhoben wird.</span><span class="sxs-lookup"><span data-stu-id="9613a-217">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="9613a-218">Die Richtung – stadteinwärts oder stadtauswärts.</span><span class="sxs-lookup"><span data-stu-id="9613a-218">The direction is into the city or out of the city</span></span>

<span data-ttu-id="9613a-219">Die folgende Tabelle zeigt die Kombinationen von Eingabewerten und des Multiplikators für die Preisgestaltung für Spitzenzeiten:</span><span class="sxs-lookup"><span data-stu-id="9613a-219">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="9613a-220">Day</span><span class="sxs-lookup"><span data-stu-id="9613a-220">Day</span></span>        | <span data-ttu-id="9613a-221">zeit</span><span class="sxs-lookup"><span data-stu-id="9613a-221">Time</span></span>         | <span data-ttu-id="9613a-222">Richtung</span><span class="sxs-lookup"><span data-stu-id="9613a-222">Direction</span></span> | <span data-ttu-id="9613a-223">Aufschlag/Rabatt</span><span class="sxs-lookup"><span data-stu-id="9613a-223">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="9613a-224">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-224">Weekday</span></span>    | <span data-ttu-id="9613a-225">morgendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-225">morning rush</span></span> | <span data-ttu-id="9613a-226">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-226">inbound</span></span>   | <span data-ttu-id="9613a-227">x 2,00</span><span class="sxs-lookup"><span data-stu-id="9613a-227">x 2.00</span></span>  |
| <span data-ttu-id="9613a-228">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-228">Weekday</span></span>    | <span data-ttu-id="9613a-229">morgendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-229">morning rush</span></span> | <span data-ttu-id="9613a-230">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-230">outbound</span></span>  | <span data-ttu-id="9613a-231">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-231">x 1.00</span></span>  |
| <span data-ttu-id="9613a-232">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-232">Weekday</span></span>    | <span data-ttu-id="9613a-233">tagsüber</span><span class="sxs-lookup"><span data-stu-id="9613a-233">daytime</span></span>      | <span data-ttu-id="9613a-234">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-234">inbound</span></span>   | <span data-ttu-id="9613a-235">x 1,50</span><span class="sxs-lookup"><span data-stu-id="9613a-235">x 1.50</span></span>  |
| <span data-ttu-id="9613a-236">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-236">Weekday</span></span>    | <span data-ttu-id="9613a-237">tagsüber</span><span class="sxs-lookup"><span data-stu-id="9613a-237">daytime</span></span>      | <span data-ttu-id="9613a-238">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-238">outbound</span></span>  | <span data-ttu-id="9613a-239">x 1,50</span><span class="sxs-lookup"><span data-stu-id="9613a-239">x 1.50</span></span>  |
| <span data-ttu-id="9613a-240">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-240">Weekday</span></span>    | <span data-ttu-id="9613a-241">abendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-241">evening rush</span></span> | <span data-ttu-id="9613a-242">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-242">inbound</span></span>   | <span data-ttu-id="9613a-243">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-243">x 1.00</span></span>  |
| <span data-ttu-id="9613a-244">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-244">Weekday</span></span>    | <span data-ttu-id="9613a-245">abendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-245">evening rush</span></span> | <span data-ttu-id="9613a-246">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-246">outbound</span></span>  | <span data-ttu-id="9613a-247">x 2,00</span><span class="sxs-lookup"><span data-stu-id="9613a-247">x 2.00</span></span>  |
| <span data-ttu-id="9613a-248">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-248">Weekday</span></span>    | <span data-ttu-id="9613a-249">nachts</span><span class="sxs-lookup"><span data-stu-id="9613a-249">overnight</span></span>    | <span data-ttu-id="9613a-250">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-250">inbound</span></span>   | <span data-ttu-id="9613a-251">x 0,75</span><span class="sxs-lookup"><span data-stu-id="9613a-251">x 0.75</span></span>  |
| <span data-ttu-id="9613a-252">Wochentag</span><span class="sxs-lookup"><span data-stu-id="9613a-252">Weekday</span></span>    | <span data-ttu-id="9613a-253">nachts</span><span class="sxs-lookup"><span data-stu-id="9613a-253">overnight</span></span>    | <span data-ttu-id="9613a-254">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-254">outbound</span></span>  | <span data-ttu-id="9613a-255">x 0,75</span><span class="sxs-lookup"><span data-stu-id="9613a-255">x 0.75</span></span>  |
| <span data-ttu-id="9613a-256">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-256">Weekend</span></span>    | <span data-ttu-id="9613a-257">morgendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-257">morning rush</span></span> | <span data-ttu-id="9613a-258">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-258">inbound</span></span>   | <span data-ttu-id="9613a-259">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-259">x 1.00</span></span>  |
| <span data-ttu-id="9613a-260">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-260">Weekend</span></span>    | <span data-ttu-id="9613a-261">morgendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-261">morning rush</span></span> | <span data-ttu-id="9613a-262">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-262">outbound</span></span>  | <span data-ttu-id="9613a-263">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-263">x 1.00</span></span>  |
| <span data-ttu-id="9613a-264">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-264">Weekend</span></span>    | <span data-ttu-id="9613a-265">tagsüber</span><span class="sxs-lookup"><span data-stu-id="9613a-265">daytime</span></span>      | <span data-ttu-id="9613a-266">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-266">inbound</span></span>   | <span data-ttu-id="9613a-267">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-267">x 1.00</span></span>  |
| <span data-ttu-id="9613a-268">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-268">Weekend</span></span>    | <span data-ttu-id="9613a-269">tagsüber</span><span class="sxs-lookup"><span data-stu-id="9613a-269">daytime</span></span>      | <span data-ttu-id="9613a-270">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-270">outbound</span></span>  | <span data-ttu-id="9613a-271">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-271">x 1.00</span></span>  |
| <span data-ttu-id="9613a-272">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-272">Weekend</span></span>    | <span data-ttu-id="9613a-273">abendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-273">evening rush</span></span> | <span data-ttu-id="9613a-274">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-274">inbound</span></span>   | <span data-ttu-id="9613a-275">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-275">x 1.00</span></span>  |
| <span data-ttu-id="9613a-276">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-276">Weekend</span></span>    | <span data-ttu-id="9613a-277">abendliche Hauptverkehrszeit</span><span class="sxs-lookup"><span data-stu-id="9613a-277">evening rush</span></span> | <span data-ttu-id="9613a-278">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-278">outbound</span></span>  | <span data-ttu-id="9613a-279">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-279">x 1.00</span></span>  |
| <span data-ttu-id="9613a-280">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-280">Weekend</span></span>    | <span data-ttu-id="9613a-281">nachts</span><span class="sxs-lookup"><span data-stu-id="9613a-281">overnight</span></span>    | <span data-ttu-id="9613a-282">stadteinwärts</span><span class="sxs-lookup"><span data-stu-id="9613a-282">inbound</span></span>   | <span data-ttu-id="9613a-283">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-283">x 1.00</span></span>  |
| <span data-ttu-id="9613a-284">Wochenende</span><span class="sxs-lookup"><span data-stu-id="9613a-284">Weekend</span></span>    | <span data-ttu-id="9613a-285">nachts</span><span class="sxs-lookup"><span data-stu-id="9613a-285">overnight</span></span>    | <span data-ttu-id="9613a-286">stadtauswärts</span><span class="sxs-lookup"><span data-stu-id="9613a-286">outbound</span></span>  | <span data-ttu-id="9613a-287">x 1,00</span><span class="sxs-lookup"><span data-stu-id="9613a-287">x 1.00</span></span>  |

<span data-ttu-id="9613a-288">Es gibt 16 verschiedene Kombinationen der drei Variablen.</span><span class="sxs-lookup"><span data-stu-id="9613a-288">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="9613a-289">Durch Kombinieren einiger Bedingungen vereinfachen Sie den endgültigen Switch-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9613a-289">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="9613a-290">Das System, das die Maut erhebt, verwendet eine <xref:System.DateTime>-Struktur für die Uhrzeit, zu der die Maut erhoben wurde.</span><span class="sxs-lookup"><span data-stu-id="9613a-290">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="9613a-291">Erstellen Sie die Membermethoden, die die Variablen aus der obigen Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="9613a-291">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="9613a-292">Die folgende Funktion verwendet einen switch-Ausdruck für den Musterabgleich, um auszudrücken, ob eine <xref:System.DateTime>-Struktur ein Wochenende oder einen Wochentag darstellt:</span><span class="sxs-lookup"><span data-stu-id="9613a-292">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="9613a-293">Diese Methode funktioniert, aber sie enthält Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="9613a-293">That method works, but it's repetitious.</span></span> <span data-ttu-id="9613a-294">Sie können sie vereinfachen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9613a-294">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="9613a-295">Fügen Sie als Nächstes eine ähnliche Funktion hinzu, um die Zeit in den Blöcken zu kategorisieren:</span><span class="sxs-lookup"><span data-stu-id="9613a-295">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="9613a-296">Die vorherige Methode verwendet den Musterabgleich nicht.</span><span class="sxs-lookup"><span data-stu-id="9613a-296">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="9613a-297">Es ist klarer, eine vertraute Kaskade von `if`-Anweisungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9613a-297">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="9613a-298">Sie fügen eine private `enum`-Variable hinzu, um jeden Zeitbereich in einen diskreten Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9613a-298">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="9613a-299">Nachdem Sie diese Methoden erstellt haben, können Sie einen anderen `switch`-Ausdruck mit dem **Tupelmuster** zum Berechnen des Aufschlags bzw. Rabatts auf den Preis verwenden.</span><span class="sxs-lookup"><span data-stu-id="9613a-299">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="9613a-300">Sie könnten einen `switch`-Ausdruck mit allen 16 Armen erstellen:</span><span class="sxs-lookup"><span data-stu-id="9613a-300">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="9613a-301">Der obige Code funktioniert, aber er kann vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="9613a-301">The above code works, but it can be simplified.</span></span> <span data-ttu-id="9613a-302">Alle acht Kombinationen für das Wochenende haben die gleiche Maut.</span><span class="sxs-lookup"><span data-stu-id="9613a-302">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="9613a-303">Sie können alle acht mit der folgenden Zeile ersetzen:</span><span class="sxs-lookup"><span data-stu-id="9613a-303">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="9613a-304">Sowohl stadteinwärts als auch stadtauswärts gehender Verkehr haben an Wochentagen tagsüber und nachts den gleichen Multiplikator.</span><span class="sxs-lookup"><span data-stu-id="9613a-304">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="9613a-305">Diese vier switch-Arme können durch die folgenden zwei Zeilen ersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="9613a-305">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="9613a-306">Der Code sollte nach diesen beiden Änderungen folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="9613a-306">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="9613a-307">Schließlich können Sie die zwei Hauptverkehrszeiten entfernen, zu denen der reguläre Preis gezahlt wird.</span><span class="sxs-lookup"><span data-stu-id="9613a-307">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="9613a-308">Wenn Sie diese Arme entfernen, können Sie im letzten Switch-Arm `false` mit einem Verwerfen (`_`) ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9613a-308">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="9613a-309">So sieht die abgeschlossene Methode aus:</span><span class="sxs-lookup"><span data-stu-id="9613a-309">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="9613a-310">Dieses Beispiel verdeutlicht einen der Vorteile von Musterabgleich: Die Musterverzweigungen werden der Reihe nach ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9613a-310">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="9613a-311">Wenn Sie sie neu anordnen, sodass eine frühere Verzweigung einen Ihrer späteren Fälle verarbeitet, gibt der Compiler einen Warnhinweis zum unerreichbaren Code aus.</span><span class="sxs-lookup"><span data-stu-id="9613a-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="9613a-312">Diese Sprachregeln haben die Durchführung der vorherigen Vereinfachungen erleichtert mit der Zuversicht, dass der Code sich nicht geändert hat.</span><span class="sxs-lookup"><span data-stu-id="9613a-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="9613a-313">Ein Musterabgleich führt dazu, dass einige Codetypen leichter lesbar sind, und bietet eine Alternative zu objektorientierten Verfahren, wenn Ihren Klassen kein Code hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9613a-313">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="9613a-314">Die Cloud sorgt dafür, dass Daten und Funktionen getrennt bleiben.</span><span class="sxs-lookup"><span data-stu-id="9613a-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="9613a-315">Die *Form* der Daten und die daran ausgeführten *Vorgänge* werden nicht notwendigerweise zusammen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9613a-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="9613a-316">In diesem Tutorial haben Sie vorhandene Daten auf von ihrer ursprünglichen Funktion völlig unterschiedliche Arten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9613a-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="9613a-317">Der Musterabgleich ermöglichte Ihnen, Funktionalitäten zu erstellen, die diese Typen überschrieben haben, obwohl Sie sie nicht erweitern konnten.</span><span class="sxs-lookup"><span data-stu-id="9613a-317">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9613a-318">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9613a-318">Next steps</span></span>

<span data-ttu-id="9613a-319">Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) auf GitHub herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9613a-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="9613a-320">Untersuchen Sie Muster auf eigene Faust, und nehmen Sie dieses Verfahren in Ihre Codierungsgewohnheiten auf.</span><span class="sxs-lookup"><span data-stu-id="9613a-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="9613a-321">Wenn Sie diese Verfahren lernen, eröffnet sich Ihnen ein anderer Weg, Probleme anzugehen und neue Funktionalität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9613a-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
