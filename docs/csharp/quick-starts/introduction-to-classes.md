---
title: "Schnellstarts - Einführung in Klassen - C#-Handbuch"
description: Erstellen Sie erstes C#-Programm und untersuchen Sie objektorientierte Konzepte
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: c2b267562f78b359d5ceaa696ff9a9bdcffa5821
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="05cc5-103">Einführung in Klassen</span><span class="sxs-lookup"><span data-stu-id="05cc5-103">Introduction to classes</span></span>

<span data-ttu-id="05cc5-104">In dieser Lektion wird davon ausgegangen, dass Sie installiert haben [.NET Core SDK](http://dot.net/core), und einen Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="05cc5-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="05cc5-105">Wenn Sie keinen haben, versuchen Sie es [Visual Studio Code](https://code.visualstudio.com/), oder [Visual Studio](https://www.visualstudio.com/) auf Mac oder Windows.</span><span class="sxs-lookup"><span data-stu-id="05cc5-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="05cc5-106">Erstellen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="05cc5-106">Create your application</span></span>

<span data-ttu-id="05cc5-107">Verwenden ein terminal-Fenster, erstellen Sie ein Verzeichnis namens **Klassen**.</span><span class="sxs-lookup"><span data-stu-id="05cc5-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="05cc5-108">Sie müssen es die Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-108">You'll build your application there.</span></span> <span data-ttu-id="05cc5-109">Ändern Sie in diesem Verzeichnis und Dateityp `dotnet new console` im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="05cc5-110">Dieser Befehl erstellt die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="05cc5-110">This command creates your application.</span></span> <span data-ttu-id="05cc5-111">Open **"Program.cs"**.</span><span class="sxs-lookup"><span data-stu-id="05cc5-111">Open **Program.cs**.</span></span> <span data-ttu-id="05cc5-112">Es sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-112">It should look like this:</span></span>

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

<span data-ttu-id="05cc5-113">In diesem Schnellstart können Sie ihm neue Typen erstellen, die ein Bankkonto darstellen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="05cc5-114">Entwickler werden i. d. r. jede Klasse in einer anderen Text-Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="05cc5-115">Dadurch einfacher zu verwalten, wie ein Programm an Größe zunimmt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="05cc5-116">Erstellen Sie eine neue Datei mit dem Namen **BankAccount.cs** in der **Klassen** Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="05cc5-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="05cc5-117">Diese Datei enthält die Deefinition von einem ***Bankkonto***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="05cc5-118">-Objekt Oriented Programmierung organisiert Code durch Erstellen von Typen in Form von ***Klassen***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="05cc5-119">Diese Klassen enthalten den Code, der eine bestimmte Entität darstellt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="05cc5-120">Die `BankAccount` -Klasse stellt ein Bankkonto dar.</span><span class="sxs-lookup"><span data-stu-id="05cc5-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="05cc5-121">Der Code implementiert bestimmte Vorgänge über Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="05cc5-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="05cc5-122">In diesem Schnellstart unterstützt das Konto dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="05cc5-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="05cc5-123">Es wurde eine 10-stellige-Zahl, die das Konto eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="05cc5-124">Es wurde eine Zeichenfolge, die den oder die Namen der Besitzer speichert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="05cc5-125">Das Guthaben kann abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="05cc5-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="05cc5-126">Er akzeptiert einzahlungen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-126">It accepts deposits.</span></span>
1. <span data-ttu-id="05cc5-127">Er akzeptiert Rücknahmen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="05cc5-128">Der erste Saldo muss positiv sein.</span><span class="sxs-lookup"><span data-stu-id="05cc5-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="05cc5-129">Rücknahmen können nicht in einen negativen Ausgleich führen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="05cc5-130">Definieren Sie den Typ des Bankkontos</span><span class="sxs-lookup"><span data-stu-id="05cc5-130">Define the bank account type</span></span>

<span data-ttu-id="05cc5-131">Sie können zunächst erstellen die Grundlagen einer Klasse, die dieses Verhalten definiert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="05cc5-132">Es würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-132">It would look like this:</span></span>

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

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="05cc5-133">Bevor Sie fortfahren, werfen wir einen Blick auf, was Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="05cc5-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="05cc5-134">Die `namespace` Deklaration bietet eine Möglichkeit, Ihren Code logisch zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="05cc5-135">Dieser Schnellstart ist relativ klein ist, damit Sie den Code in einem einzelnen Namespace platzieren müssen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="05cc5-136">`public class BankAccount`definiert die Klasse oder ein Typ, Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="05cc5-137">Sämtliche Inhalte innerhalb der `{` und `}` , folgt die Klasse Deklaration definiert das Verhalten der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="05cc5-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="05cc5-138">Es gibt fünf ***Elemente*** von der `BankAccount` Klasse.</span><span class="sxs-lookup"><span data-stu-id="05cc5-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="05cc5-139">Die ersten drei sind ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-139">The first three are ***properties***.</span></span> <span data-ttu-id="05cc5-140">Eigenschaften können sind die Datenelemente und Code, der Überprüfung oder einer anderen Regeln erzwungen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="05cc5-141">Die letzten beiden ***Methoden***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-141">The last two are ***methods***.</span></span> <span data-ttu-id="05cc5-142">Methoden werden Codeblöcke, wie eine einzelne Funktion.</span><span class="sxs-lookup"><span data-stu-id="05cc5-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="05cc5-143">Beim Lesen der Namen der einzelnen Elemente können genug Informationen, oder ein anderer Entwickler zu verstehen, was bewirkt, dass die Klasse.</span><span class="sxs-lookup"><span data-stu-id="05cc5-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="05cc5-144">Öffnen Sie ein neues Konto</span><span class="sxs-lookup"><span data-stu-id="05cc5-144">Open a new account</span></span>

<span data-ttu-id="05cc5-145">Die erste Funktion implementieren, besteht darin, ein Bankkonto zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="05cc5-146">Wenn ein Kunde ein Konto geöffnet wird, müssen sie eine erste Saldo und die Informationen über die Besitzer oder den Besitzer dieses Kontos angeben.</span><span class="sxs-lookup"><span data-stu-id="05cc5-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="05cc5-147">Erstellen eines neuen Objekts von der `BankAccount` Typ bedeutet definieren eine ***Konstruktor*** , die diese Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="05cc5-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="05cc5-148">Ein ***Konstruktor*** ist ein Element, das den gleichen Namen wie die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="05cc5-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="05cc5-149">Es wird verwendet, um Objekte dieses Klassentyps zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="05cc5-150">Fügen Sie den folgenden Konstruktor hinzu der `BankAccount` Typ:</span><span class="sxs-lookup"><span data-stu-id="05cc5-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="05cc5-151">Konstruktoren werden aufgerufen, bei der Erstellung eines Objekts mit [ `new` ](../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="05cc5-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="05cc5-152">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` in ***"Program.cs"*** mit der folgenden Zeile (ersetzen Sie `<name>` durch den Namen Ihres):</span><span class="sxs-lookup"><span data-stu-id="05cc5-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance".);
```

<span data-ttu-id="05cc5-153">Typ `dotnet run` zu sehen, was passiert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="05cc5-154">Haben Sie bemerkt, dass die Kontonummer leer ist?</span><span class="sxs-lookup"><span data-stu-id="05cc5-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="05cc5-155">Es ist Zeit, die behoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="05cc5-155">It's time to fix that.</span></span> <span data-ttu-id="05cc5-156">Die Kontonummer sollten zugewiesen werden, wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="05cc5-157">Jedoch sollte nicht der Verantwortung des Aufrufers, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="05cc5-158">Die `BankAccount` Klassencode sollten wissen, wie neue Kontonummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="05cc5-159">Eine einfache Möglichkeit hierzu ist eine Zahl mit 10-Ziffern.</span><span class="sxs-lookup"><span data-stu-id="05cc5-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="05cc5-160">Erhöhen sie bei jeder neues Konto erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-160">Increment it when each new account is created.</span></span> <span data-ttu-id="05cc5-161">Speichern Sie schließlich Nummer des aktuellen Kontos auf, wenn ein Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="05cc5-162">Fügen Sie die folgenden Memberdeklaration zu der `BankAccount` Klasse:</span><span class="sxs-lookup"><span data-stu-id="05cc5-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="05cc5-163">Dies ist ein Datenmember.</span><span class="sxs-lookup"><span data-stu-id="05cc5-163">This is a data member.</span></span> <span data-ttu-id="05cc5-164">Es wurde `private`, dies bedeutet, dass nur über möglich, Code innerhalb der `BankAccount` Klasse.</span><span class="sxs-lookup"><span data-stu-id="05cc5-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="05cc5-165">Dies ist eine Möglichkeit, unterteilen Sie die öffentliche Aufgaben (z. B. über eine Kontonummer) über die private Implementierung (wie Kontonummern generiert werden.) Fügen Sie die folgenden zwei Zeilen, an den Konstruktor der Kontonummer zuweisen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="05cc5-166">Typ `dotnet run` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="05cc5-167">Erstellen Sie einzahlungen und Rücknahmen</span><span class="sxs-lookup"><span data-stu-id="05cc5-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="05cc5-168">Ihr Bankkonto-Klasse muss zum Akzeptieren von einzahlungen und Rücknahmen ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="05cc5-169">Wir implementieren einzahlungen und Rücknahmen durch das Erstellen einer Erfassung jeder Transaktion für das Konto ein.</span><span class="sxs-lookup"><span data-stu-id="05cc5-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="05cc5-170">Die weist einige Vorteile gegenüber der Saldo für jede Transaktion einfach aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="05cc5-171">Der Verlauf kann alle Transaktionen zu überwachen und Verwalten von täglichen Bilanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05cc5-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="05cc5-172">Durch das Berechnen des Saldo aus dem Verlauf aller Transaktionen, bei Bedarf, werden alle Fehler in einer einzigen Transaktion, die behoben wurden ordnungsgemäß in das Guthaben auf die nächste Berechnung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="05cc5-173">Zunächst erstellen einen neuen Typ aus, um eine Transaktion darzustellen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="05cc5-174">Dies ist ein einfacher Typ, der Aufgaben aufweist.</span><span class="sxs-lookup"><span data-stu-id="05cc5-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="05cc5-175">Einige Eigenschaften benötigt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-175">It needs a few properties.</span></span> <span data-ttu-id="05cc5-176">Erstellen Sie eine neue Datei mit dem Namen ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="05cc5-177">Im folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="05cc5-178">Nun fügen wir eine <xref:System.Collections.Generic.List%601> von `Transaction` -Objekte und die `BankAccount` Klasse.</span><span class="sxs-lookup"><span data-stu-id="05cc5-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="05cc5-179">Fügen Sie die folgende Deklaration hinzu:</span><span class="sxs-lookup"><span data-stu-id="05cc5-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="05cc5-180">Die <xref:System.Collections.Generic.List%601> Klasse erfordert, dass Sie einen anderen Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="05cc5-181">Fügen Sie am Anfang des Folgendes **BankAccount.cs**:</span><span class="sxs-lookup"><span data-stu-id="05cc5-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="05cc5-182">Jetzt ändern wie die `Balance` gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="05cc5-183">Sie können die Werte aller Transaktionen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="05cc5-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="05cc5-184">Ändern Sie die Deklaration von `Balance` in die `BankAccount` Klasse, um die folgenden:</span><span class="sxs-lookup"><span data-stu-id="05cc5-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="05cc5-185">Dieses Beispiel zeigt einen wichtigen Aspekt der ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="05cc5-186">Sie sind jetzt das Guthaben berechnet, wenn der Wert einer anderen Programmierer anfordert.</span><span class="sxs-lookup"><span data-stu-id="05cc5-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="05cc5-187">Die Berechnung Listet alle Transaktionen auf und gibt die Summe als dem aktuellen Saldo.</span><span class="sxs-lookup"><span data-stu-id="05cc5-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="05cc5-188">Als Nächstes implementieren die `MakeDeposit` und `MakeWithdrawal` Methoden.</span><span class="sxs-lookup"><span data-stu-id="05cc5-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="05cc5-189">Diese Methoden erzwingt die letzten beiden Regeln:, dass der erste Saldo muss positiv sein und eine Abhebung, die einen negativen Ausgleich nicht erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="05cc5-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="05cc5-190">Dies führt das Konzept der ***Ausnahmen***.</span><span class="sxs-lookup"><span data-stu-id="05cc5-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="05cc5-191">Die Standardmethode für gibt an, dass ihre Arbeit von eine Methode erfolgreich abgeschlossen werden kann, ist eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="05cc5-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="05cc5-192">Der Typ der Ausnahme und die Nachricht zugeordnet werden den Fehler beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05cc5-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="05cc5-193">Hier wird die `MakeDeposit` Methode löst eine Ausnahme aus, wenn der Anteil der Einzahlung negativ ist.</span><span class="sxs-lookup"><span data-stu-id="05cc5-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="05cc5-194">Die `MakeWithdrawal` Methode löst eine Ausnahme aus, wenn der Betrag der Abbuchung negativ ist oder wenn die Abbuchung Anwenden einer negativen Saldo ergibt:</span><span class="sxs-lookup"><span data-stu-id="05cc5-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="05cc5-195">Die [ `throw` ](../language-reference/throw.md) Anweisung **löst** eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="05cc5-195">The [`throw`](../language-reference/throw.md) statment **throws** an exception.</span></span> <span data-ttu-id="05cc5-196">Ausführung der aktuellen Methode beendet wird, und wird fortgesetzt, wenn ein entsprechender `catch` -Block gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="05cc5-197">Fügen Sie eine `catch` Block, um diesen Code etwas später zu testen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="05cc5-198">Der Konstruktor sollte eine Änderung abgerufen, sodass Fügt eine anfängliche, anstatt als das Guthaben direkt aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="05cc5-199">Da Sie bereits geschrieben haben die `MakeDeposit` -Methode, aus dem Konstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="05cc5-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="05cc5-200">Die fertige Konstruktor sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="05cc5-201"><xref:System.DateTime.Now?displayProperty=nameWithType>ist eine Eigenschaft, die das aktuelle Datum und die Uhrzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="05cc5-202">Testen Sie dies durch Hinzufügen von wenigen einzahlungen und Rücknahmen in Ihre `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="05cc5-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="05cc5-203">Anschließend testen Sie, dass Sie fehlerbedingungen abgefangen werden, indem Sie versuchen, ein Konto mit einem negativen Saldo zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="05cc5-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="05cc5-204">Verwenden Sie die [ `try` und `catch` Anweisungen](../language-reference/keywords/try-catch.md) um einen Codeblock zu markieren, die Ausnahmen auslösen kann, und um diese Fehler abzufangen, die Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="05cc5-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="05cc5-205">Das gleiche Verfahren können Sie um den Code zu testen, der für eine negative Gleichgewicht auslöst:</span><span class="sxs-lookup"><span data-stu-id="05cc5-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="05cc5-206">Speichern Sie die Datei und den Typ `dotnet run` ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="05cc5-207">Herausforderung: alle Transaktionen protokollieren</span><span class="sxs-lookup"><span data-stu-id="05cc5-207">Challenge - log all transactions</span></span>

<span data-ttu-id="05cc5-208">Um diesem Schnellstart abgeschlossen haben, können Sie schreiben die `GetAccountHistory` -Methode, erstellt eine `string` für den Transaktionsverlauf.</span><span class="sxs-lookup"><span data-stu-id="05cc5-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="05cc5-209">Fügen Sie diese Methode, um die `BankAccount` Typ:</span><span class="sxs-lookup"><span data-stu-id="05cc5-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="05cc5-210">Hierdurch wird unter Verwendung der <xref:System.Text.StringBuilder> Klasse zum Formatieren einer Zeichenfolge, die eine Zeile für jede Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="05cc5-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="05cc5-211">Die Zeichenfolge, die Formatierung von Code in diese Schnellstarts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05cc5-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="05cc5-212">Ist ein neues Zeichen `\t`.</span><span class="sxs-lookup"><span data-stu-id="05cc5-212">One new character is `\t`.</span></span> <span data-ttu-id="05cc5-213">Die Fügt einer Registerkarte, um die Ausgabe zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="05cc5-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="05cc5-214">Fügen Sie diese Zeile zum Testen in **"Program.cs"**:</span><span class="sxs-lookup"><span data-stu-id="05cc5-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="05cc5-215">Typ `dotnet run` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05cc5-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05cc5-216">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="05cc5-216">Next Steps</span></span>

<span data-ttu-id="05cc5-217">Wenn Sie hängen bleiben erhalten haben, sehen Sie die Quelle für dieses Schnellstarts [in unserer GitHub-Repository](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span><span class="sxs-lookup"><span data-stu-id="05cc5-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="05cc5-218">Herzlichen Glückwunsch, Sie haben nun alle unsere Schnellstartanleitung.</span><span class="sxs-lookup"><span data-stu-id="05cc5-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="05cc5-219">Wenn Sie weitere eager sind, versuchen Sie es unseren [Lernprogramme](../tutorials/index.md)</span><span class="sxs-lookup"><span data-stu-id="05cc5-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>