---
title: Klassen und Objekte – Tutorial zur Einführung in C#
description: Erstellen Ihres ersten C#-Programms und Erforschen objektorientierter Konzepte
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 0955b0ac33b346b9880c8af70bd73cb458120f35
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434886"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="b08dd-103">Erkunden der objektorientierten Programmierung mit Klassen und Objekten</span><span class="sxs-lookup"><span data-stu-id="b08dd-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="b08dd-104">Für dieses Tutorial wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="b08dd-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="b08dd-105">Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS.</span><span class="sxs-lookup"><span data-stu-id="b08dd-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="b08dd-106">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie im Artikel [Einführung in Entwicklungstools](local-environment.md), der Links zu weiteren Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="b08dd-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="b08dd-107">Erstellen Ihrer Anwendung</span><span class="sxs-lookup"><span data-stu-id="b08dd-107">Create your application</span></span>

<span data-ttu-id="b08dd-108">Erstellen Sie in einem Terminalfenster ein Verzeichnis namens *classes* .</span><span class="sxs-lookup"><span data-stu-id="b08dd-108">Using a terminal window, create a directory named *classes* .</span></span> <span data-ttu-id="b08dd-109">Dort werden Sie Ihre Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-109">You'll build your application there.</span></span> <span data-ttu-id="b08dd-110">Wechseln Sie in dieses Verzeichnis, und geben Sie `dotnet new console` im Konsolenfenster ein.</span><span class="sxs-lookup"><span data-stu-id="b08dd-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="b08dd-111">Dieser Befehl erstellt die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b08dd-111">This command creates your application.</span></span> <span data-ttu-id="b08dd-112">Öffnen Sie *Program.cs* .</span><span class="sxs-lookup"><span data-stu-id="b08dd-112">Open *Program.cs* .</span></span> <span data-ttu-id="b08dd-113">Es sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b08dd-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
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

<span data-ttu-id="b08dd-114">In diesem Tutorial erstellen Sie neue Typen, die ein Bankkonto darstellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="b08dd-115">Entwickler definieren jede Klasse in der Regel in einer anderen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="b08dd-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="b08dd-116">Dies erleichtert die Verwaltung bei zunehmender Programmgröße.</span><span class="sxs-lookup"><span data-stu-id="b08dd-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="b08dd-117">Erstellen Sie eine neue Datei mit dem Namen *BankAccount.cs* im Verzeichnis *classes* .</span><span class="sxs-lookup"><span data-stu-id="b08dd-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="b08dd-118">Diese Datei enthält die Definition eines \* **Bankkontos** _.</span><span class="sxs-lookup"><span data-stu-id="b08dd-118">This file will contain the definition of a \* **bank account** _.</span></span> <span data-ttu-id="b08dd-119">In der objektorientierten Programmierung wird der Code organisiert, indem Typen in Form von _*_Klassen_*_ erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b08dd-119">Object Oriented programming organizes code by creating types in the form of _*_classes_*_ .</span></span> <span data-ttu-id="b08dd-120">Diese Klassen enthalten den Code, der eine bestimmte Entität darstellt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="b08dd-121">Die `BankAccount`-Klasse stellt ein Bankkonto dar.</span><span class="sxs-lookup"><span data-stu-id="b08dd-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="b08dd-122">Der Code implementiert bestimmte Vorgänge mittels Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b08dd-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="b08dd-123">In diesem Tutorial unterstützt das Bankkonto dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="b08dd-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="b08dd-124">Es enthält eine 10-stellige Zahl, die das Bankkonto eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b08dd-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="b08dd-125">Es enthält eine Zeichenfolge, die den bzw. die Namen des Besitzers speichert.</span><span class="sxs-lookup"><span data-stu-id="b08dd-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="b08dd-126">Der Kontostand kann abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b08dd-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="b08dd-127">Es akzeptiert Einzahlungen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-127">It accepts deposits.</span></span>
1. <span data-ttu-id="b08dd-128">Es akzeptiert Abbuchungen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="b08dd-129">Der anfängliche Kontostand muss positiv sein.</span><span class="sxs-lookup"><span data-stu-id="b08dd-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="b08dd-130">Abbuchungen dürfen nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="b08dd-131">Definieren des Bankkontotyps</span><span class="sxs-lookup"><span data-stu-id="b08dd-131">Define the bank account type</span></span>

<span data-ttu-id="b08dd-132">Sie können beginnen, indem Sie die Grundlagen einer Klasse erstellen, die dieses Verhalten definiert.</span><span class="sxs-lookup"><span data-stu-id="b08dd-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="b08dd-133">Erstellen Sie eine neue Datei mit dem Befehl _ *File:New* \*.</span><span class="sxs-lookup"><span data-stu-id="b08dd-133">Create a new file using the _ *File:New* \* command.</span></span> <span data-ttu-id="b08dd-134">Nennen Sie sie *BankAccount.cs* .</span><span class="sxs-lookup"><span data-stu-id="b08dd-134">Name it *BankAccount.cs* .</span></span> <span data-ttu-id="b08dd-135">Fügen Sie der Datei *BankAccount.cs* folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-135">Add the following code to your *BankAccount.cs* file:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="b08dd-136">Bevor wir fortfahren, lassen Sie uns anschauen, was Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b08dd-136">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="b08dd-137">Die `namespace`-Deklaration ist eine Möglichkeit, Ihren Code logisch zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-137">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="b08dd-138">Da dieses Tutorial relativ klein ist, platzieren Sie den gesamten Code in einen einzigen Namespace.</span><span class="sxs-lookup"><span data-stu-id="b08dd-138">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="b08dd-139">`public class BankAccount` definiert die Klasse oder den Typ, die/den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-139">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="b08dd-140">Sämtliche Inhalte zwischen `{` und `}`, die der Klassendeklaration folgen, definieren den Zustand und das Verhalten der Klasse.</span><span class="sxs-lookup"><span data-stu-id="b08dd-140">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="b08dd-141">Die `BankAccount`-Klasse verfügt über fünf \* **Member** _.</span><span class="sxs-lookup"><span data-stu-id="b08dd-141">There are five \* **members** _ of the `BankAccount` class.</span></span> <span data-ttu-id="b08dd-142">Die ersten drei sind _*_Eigenschaften_*_ .</span><span class="sxs-lookup"><span data-stu-id="b08dd-142">The first three are _*_properties_*_ .</span></span> <span data-ttu-id="b08dd-143">Eigenschaften sind Datenelemente und können Code aufweisen, der eine Überprüfung oder andere Regeln erzwingt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-143">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="b08dd-144">Die letzten beiden sind _*_Methoden_*_ .</span><span class="sxs-lookup"><span data-stu-id="b08dd-144">The last two are _*_methods_*_ .</span></span> <span data-ttu-id="b08dd-145">Methoden sind Codeblöcke, die eine einzelne Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-145">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="b08dd-146">Das Lesen der Namen der einzelnen Member sollte Ihnen oder anderen Entwicklern genug Informationen liefern, um zu verstehen, welche Aufgabe die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="b08dd-146">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="b08dd-147">Eröffnen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="b08dd-147">Open a new account</span></span>

<span data-ttu-id="b08dd-148">Die erste zu implementierende Funktion ist das Eröffnen eines Bankkontos.</span><span class="sxs-lookup"><span data-stu-id="b08dd-148">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="b08dd-149">Wenn ein Kunde ein Konto eröffnet, muss er einen anfänglichen Kontostand bereitstellen und Informationen über den/die Besitzer dieses Kontos angeben.</span><span class="sxs-lookup"><span data-stu-id="b08dd-149">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="b08dd-150">Das Erstellen eines neuen Objekts des Typs `BankAccount` bedeutet, einen _*_Konstruktor_*_ zu definieren, der diese Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="b08dd-150">Creating a new object of the `BankAccount` type means defining a _*_constructor_*_ that assigns those values.</span></span> <span data-ttu-id="b08dd-151">Ein _*_Konstruktor_*_ ist ein Member, der den gleichen Namen wie die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="b08dd-151">A _*_constructor_*_ is a member that has the same name as the class.</span></span> <span data-ttu-id="b08dd-152">Er wird verwendet, um Objekte dieses Klassentyps zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-152">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="b08dd-153">Fügen Sie dem `BankAccount`-Typ den folgenden Konstruktor hinzu,.</span><span class="sxs-lookup"><span data-stu-id="b08dd-153">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="b08dd-154">Platzieren Sie folgenden Code oberhalb der Deklaration von `MakeDeposit`:</span><span class="sxs-lookup"><span data-stu-id="b08dd-154">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="b08dd-155">Konstruktoren werden bei der Erstellung eines Objekts mit [`new`](../../language-reference/operators/new-operator.md) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-155">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="b08dd-156">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` in _Program.cs\* durch den folgende Code (ersetzen Sie `<name>` durch Ihren Namen):</span><span class="sxs-lookup"><span data-stu-id="b08dd-156">Replace the line `Console.WriteLine("Hello World!");` in _Program.cs\* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="b08dd-157">Wir führen nun aus, was wir bisher erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b08dd-157">Let's run what you've built so far.</span></span> <span data-ttu-id="b08dd-158">Wenn Sie Visual Studio verwenden, wählen Sie **Ohne Debuggen starten** im Menü **Ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="b08dd-158">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="b08dd-159">Wenn Sie eine Befehlszeile verwenden, geben Sie `dotnet run` in dem Verzeichnis ein, wo Sie das Projekt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b08dd-159">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="b08dd-160">Haben Sie bemerkt, dass die Kontonummer leer ist?</span><span class="sxs-lookup"><span data-stu-id="b08dd-160">Did you notice that the account number is blank?</span></span> <span data-ttu-id="b08dd-161">Es ist höchste Zeit, dies zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b08dd-161">It's time to fix that.</span></span> <span data-ttu-id="b08dd-162">Die Kontonummer sollten zugewiesen werden, wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b08dd-162">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="b08dd-163">Jedoch sollte nicht der Aufrufende für das Erstellen verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="b08dd-163">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="b08dd-164">Der `BankAccount`-Klassencode sollte wissen, wie neue Kontonummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b08dd-164">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="b08dd-165">Eine einfache Möglichkeit hierzu ist, mit einer 10-stelligen Zahl zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-165">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="b08dd-166">Lassen Sie sie bei jeder Erstellung eines neuen Kontos erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-166">Increment it when each new account is created.</span></span> <span data-ttu-id="b08dd-167">Speichern Sie schließlich die aktuelle Kontonummer, wenn ein Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b08dd-167">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="b08dd-168">Fügen Sie der `BankAccount`-Klasse eine Memberdeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="b08dd-168">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="b08dd-169">Platzieren Sie die folgende Codezeile nach der öffnenden geschweiften Klammer `{` am Anfang der `BankAccount`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="b08dd-169">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="b08dd-170">Dies ist ein Datenelement.</span><span class="sxs-lookup"><span data-stu-id="b08dd-170">This is a data member.</span></span> <span data-ttu-id="b08dd-171">Es ist `private`, d.h. der Zugriff darauf ist nur über Code in der `BankAccount`-Klasse möglich.</span><span class="sxs-lookup"><span data-stu-id="b08dd-171">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="b08dd-172">Dies ist eine Möglichkeit, die öffentlichen Verantwortlichkeiten (z. B. Besitz einer Kontonummer) von der privaten Implementierung (wie Kontonummern generiert werden) zu trennen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-172">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="b08dd-173">Es ist auch als `static` definiert, wird also von allen `BankAccount`-Objekten gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-173">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="b08dd-174">Der Wert einer nicht statischen Variable ist für jede Instanz des `BankAccount`-Objekts eindeutig.</span><span class="sxs-lookup"><span data-stu-id="b08dd-174">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="b08dd-175">Fügen Sie dem Konstruktor die folgenden zwei Zeilen hinzu, um die Kontonummer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-175">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="b08dd-176">Platzieren Sie sie nach der Zeile, die `this.Balance = initialBalance` enthält:</span><span class="sxs-lookup"><span data-stu-id="b08dd-176">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="b08dd-177">Geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-177">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="b08dd-178">Erstellen von Einzahlungen und Abbuchungen</span><span class="sxs-lookup"><span data-stu-id="b08dd-178">Create deposits and withdrawals</span></span>

<span data-ttu-id="b08dd-179">Um ordnungsgemäß zu funktionieren, muss Ihre Bankkontoklasse Einzahlungen und Abbuchungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-179">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="b08dd-180">Einzahlungen und Abbuchungen implementieren Sie, indem Sie eine Erfassung jeder Transaktion für das Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-180">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="b08dd-181">Dies ist vorteilhafter, als den Kontostand bei jeder Transaktion einfachen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-181">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="b08dd-182">Der Verlauf kann zum Überwachen aller Transaktionen und Verwalten täglicher Kontostände verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b08dd-182">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="b08dd-183">Indem der Kontostand ggf. aus dem Verlauf aller Transaktionen berechnet wird, werden etwaige Korrekturen von Fehlern in einer einzelnen Transaktion bei der nächsten Berechnung im Kontostand ordnungsgemäß widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-183">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="b08dd-184">Zunächst erstellen wir einen neuen Typ, um eine Transaktion darzustellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-184">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="b08dd-185">Dies ist ein einfacher Typ, der keine Verantwortlichkeiten hat.</span><span class="sxs-lookup"><span data-stu-id="b08dd-185">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="b08dd-186">Er benötigt einige Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b08dd-186">It needs a few properties.</span></span> <span data-ttu-id="b08dd-187">Erstellen Sie eine neue Datei mit dem Namen *Transaction.cs* .</span><span class="sxs-lookup"><span data-stu-id="b08dd-187">Create a new file named *Transaction.cs* .</span></span> <span data-ttu-id="b08dd-188">Fügen Sie ihr folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-188">Add the following code to it:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

<span data-ttu-id="b08dd-189">Nun fügen wir eine <xref:System.Collections.Generic.List%601> von `Transaction`-Objekten der `BankAccount`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="b08dd-189">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="b08dd-190">Fügen Sie die folgende Deklaration nach dem Konstruktor in ihrer *BankAccount.cs* -Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-190">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

<span data-ttu-id="b08dd-191">Die <xref:System.Collections.Generic.List%601>-Klasse erfordert, dass Sie einen anderen Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-191">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="b08dd-192">Fügen Sie am Anfang von *BankAccount.cs* Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-192">Add the following at the beginning of *BankAccount.cs* :</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="b08dd-193">Nun werden Sie `Balance` korrekt berechnen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-193">Now, let's correctly compute the `Balance`.</span></span> <span data-ttu-id="b08dd-194">Der aktuelle Saldo kann durch Summieren der Werte aller Transaktionen ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="b08dd-194">The current balance can be found by summing the values of all transactions.</span></span> <span data-ttu-id="b08dd-195">Mit dem aktuellen Code können Sie nur den anfänglichen Saldo des Kontos abrufen. Sie müssen daher die Eigenschaft `Balance` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-195">As the code is currently, you can only get the initial balance of the account, so you'll have to update the `Balance` property.</span></span> <span data-ttu-id="b08dd-196">Ersetzen Sie die Zeile `public decimal Balance { get; }` in *BankAccount.cs* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b08dd-196">Replace the line `public decimal Balance { get; }` in *BankAccount.cs* with the following code:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

<span data-ttu-id="b08dd-197">Dieses Beispiel zeigt einen wichtigen Aspekt von \* **Eigenschaften** _.</span><span class="sxs-lookup"><span data-stu-id="b08dd-197">This example shows an important aspect of \* **properties** _.</span></span> <span data-ttu-id="b08dd-198">Jetzt berechnen Sie den Kontostand, wenn ein anderer Programmierer den Wert anfordert.</span><span class="sxs-lookup"><span data-stu-id="b08dd-198">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="b08dd-199">Die Berechnung zählt alle Transaktionen auf und gibt die Summe als aktuellen Kontostand zurück.</span><span class="sxs-lookup"><span data-stu-id="b08dd-199">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="b08dd-200">Implementieren Sie nun die `MakeDeposit`- und `MakeWithdrawal`-Methode.</span><span class="sxs-lookup"><span data-stu-id="b08dd-200">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="b08dd-201">Diese Methoden erzwingen die letzten beiden Regeln: Der anfängliche Kontostand muss positiv sein, und eine Abbuchung darf nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-201">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="b08dd-202">Dies führt das Konzept der _*_Ausnahmen_*_ ein.</span><span class="sxs-lookup"><span data-stu-id="b08dd-202">This introduces the concept of _*_exceptions_*_ .</span></span> <span data-ttu-id="b08dd-203">Standardmäßig wird eine Ausnahme ausgelöst, um anzuzeigen, dass eine Methode ihre Aufgabe nicht erfolgreich ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="b08dd-203">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="b08dd-204">Der Typ der Ausnahme und die zugeordnete Nachricht beschreiben den Fehler.</span><span class="sxs-lookup"><span data-stu-id="b08dd-204">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="b08dd-205">Hier löst die `MakeDeposit`-Methode eine Ausnahme aus, wenn der Einzahlungsbetrag negativ ist.</span><span class="sxs-lookup"><span data-stu-id="b08dd-205">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="b08dd-206">Die `MakeWithdrawal`-Methode löst eine Ausnahme aus, wenn der Abbuchungsbetrag negativ ist, oder wenn aus der Abbuchung ein negativer Kontostand resultiert.</span><span class="sxs-lookup"><span data-stu-id="b08dd-206">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="b08dd-207">Fügen Sie nach der Deklaration der `allTransactions`-Liste den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-207">Add the following code after the declaration of the `allTransactions` list:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

<span data-ttu-id="b08dd-208">Die [`throw`](../../language-reference/keywords/throw.md)-Anweisung _ *löst* \* eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="b08dd-208">The [`throw`](../../language-reference/keywords/throw.md) statement _ *throws* \* an exception.</span></span> <span data-ttu-id="b08dd-209">Die Ausführung des aktuellen Block wird beendet, und die Steuerung wird an den ersten übereinstimmenden `catch`-Block übertragen, der in der Aufrufliste gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="b08dd-209">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="b08dd-210">Sie fügen einen `catch`-Block hinzu, um diesen Code etwas später zu testen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-210">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="b08dd-211">Der Konstruktor sollte so geändert werden, dass er eine anfängliche Transaktion hinzufügt, anstatt den Kontostand direkt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-211">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="b08dd-212">Da Sie die `MakeDeposit`-Methode bereits geschrieben haben, rufen Sie sie aus dem Konstruktor auf.</span><span class="sxs-lookup"><span data-stu-id="b08dd-212">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="b08dd-213">Der fertige Konstruktor sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b08dd-213">The finished constructor should look like this:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<span data-ttu-id="b08dd-214"><xref:System.DateTime.Now?displayProperty=nameWithType> ist eine Eigenschaft, die das aktuelle Datum und die Uhrzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-214"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="b08dd-215">Testen Sie dies durch Hinzufügen von ein paar Einzahlungen und Abbuchungen in Ihrer `Main`-Methode und verfolgen Sie den Code, der einen neuen `BankAccount` erstellt:</span><span class="sxs-lookup"><span data-stu-id="b08dd-215">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="b08dd-216">Testen Sie anschließend, ob Sie Fehlerbedingungen abfangen, indem Sie versuchen, ein Konto mit einem negativen Kontostand zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-216">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="b08dd-217">Fügen Sie den folgenden Code nach dem vorhergehenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-217">Add the following code after the preceding code you just added:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="b08dd-218">Sie verwenden die [Anweisungen `try` und `catch`](../../language-reference/keywords/try-catch.md), um einen Codeblock zu markieren, der Ausnahmen auslösen kann, und um die erwarteten Fehler abzufangen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-218">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="b08dd-219">Mit dem gleichen Verfahren können Sie den Code testen, der bei einem negativen Kontostand eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="b08dd-219">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="b08dd-220">Fügen Sie den folgenden Code am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-220">Add the following code at the end of your `Main` method:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="b08dd-221">Speichern Sie die Datei, und geben Sie `dotnet run` zum Testen ein.</span><span class="sxs-lookup"><span data-stu-id="b08dd-221">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="b08dd-222">Herausforderung – Protokollieren aller Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b08dd-222">Challenge - log all transactions</span></span>

<span data-ttu-id="b08dd-223">Um dieses Tutorial abzuschließen, können Sie die `GetAccountHistory`-Methode schreiben, die eine Zeichenfolge (`string`) für den Transaktionsverlauf erstellt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-223">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="b08dd-224">Fügen Sie diese Methode dem `BankAccount`-Typ hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-224">Add this method to the `BankAccount` type:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

<span data-ttu-id="b08dd-225">Hier wird die <xref:System.Text.StringBuilder>-Klasse zum Formatieren einer Zeichenfolge verwendet, die eine Zeile für jede Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="b08dd-225">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="b08dd-226">Sie haben den Zeichenfolgen-Formatierungscode in diesen Tutorials bereits gesehen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-226">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="b08dd-227">`\t` ist ein neues Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-227">One new character is `\t`.</span></span> <span data-ttu-id="b08dd-228">Damit wird ein Tabulator zum Formatieren der Ausgabe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b08dd-228">That inserts a tab to format the output.</span></span>

<span data-ttu-id="b08dd-229">Fügen Sie diese Zeile *Program.cs* zum Testen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b08dd-229">Add this line to test it in *Program.cs* :</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="b08dd-230">Führen Sie das Programm aus, um die Ergebnisse zu sehen.</span><span class="sxs-lookup"><span data-stu-id="b08dd-230">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b08dd-231">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b08dd-231">Next steps</span></span>

<span data-ttu-id="b08dd-232">Wenn Sie nicht weiterkommen, sehen Sie sich die Quelle für dieses Tutorial [in unserem GitHub-Repository](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes) an.</span><span class="sxs-lookup"><span data-stu-id="b08dd-232">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span></span>

<span data-ttu-id="b08dd-233">Sie können mit dem Tutorial zur [objektorientierten Programmierung](object-oriented-programming.md) fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b08dd-233">You can continue with the [object oriented programming](object-oriented-programming.md) tutorial.</span></span>

<span data-ttu-id="b08dd-234">Weitere Informationen zu diesen Begriffen finden Sie in diesen Artikeln:</span><span class="sxs-lookup"><span data-stu-id="b08dd-234">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="b08dd-235">if- und else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b08dd-235">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="b08dd-236">while-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b08dd-236">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="b08dd-237">do-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b08dd-237">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="b08dd-238">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b08dd-238">For statement</span></span>](../../language-reference/keywords/for.md)
