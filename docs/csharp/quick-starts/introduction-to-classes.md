---
title: "Schnellstarts – Einführung in Klassen – C#-Handbuch"
description: Erstellen Ihres ersten C#-Programms und Erforschen objektorientierter Konzepte
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: ff7cd60619f8583376442c202f27a4309790fff8
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="ed3b1-103">Einführung in Klassen</span><span class="sxs-lookup"><span data-stu-id="ed3b1-103">Introduction to classes</span></span>

<span data-ttu-id="ed3b1-104">In dieser Lektion wird vorausgesetzt, dass Sie [.NET Core SDK](http://dot.net/core) und einen Editor Ihrer Wahl installiert haben.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="ed3b1-105">Wenn Sie keinen besitzen, versuchen Sie, [Visual Studio Code](https://code.visualstudio.com/) oder [Visual Studio](https://www.visualstudio.com/) auf Mac oder Windows zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="ed3b1-106">Erstellen Ihrer Anwendung</span><span class="sxs-lookup"><span data-stu-id="ed3b1-106">Create your application</span></span>

<span data-ttu-id="ed3b1-107">Erstellen Sie in einem Terminalfenster ein Verzeichnis namens **classes**.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="ed3b1-108">Dort werden Sie Ihre Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-108">You'll build your application there.</span></span> <span data-ttu-id="ed3b1-109">Wechseln Sie in dieses Verzeichnis, und geben Sie `dotnet new console` im Konsolenfenster ein.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="ed3b1-110">Dieser Befehl erstellt die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-110">This command creates your application.</span></span> <span data-ttu-id="ed3b1-111">Öffnen Sie **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-111">Open **Program.cs**.</span></span> <span data-ttu-id="ed3b1-112">Es sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-112">It should look like this:</span></span>

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

<span data-ttu-id="ed3b1-113">In diesem Schnellstart erstellen Sie neue Typen, die ein Bankkonto darstellen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="ed3b1-114">Entwickler definieren jede Klasse in der Regel in einer anderen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="ed3b1-115">Dies erleichtert die Verwaltung bei zunehmender Programmgröße.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="ed3b1-116">Erstellen Sie eine neue Datei mit dem Namen **BankAccount.cs** im Verzeichnis **classes**.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="ed3b1-117">Diese Datei enthält die Definition eines ***Bankkontos***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="ed3b1-118">In der objektorientierten Programmierung wird der Code organisiert, indem Typen in Form von ***Klassen*** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="ed3b1-119">Diese Klassen enthalten den Code, der eine bestimmte Entität darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="ed3b1-120">Die `BankAccount`-Klasse stellt ein Bankkonto dar.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="ed3b1-121">Der Code implementiert bestimmte Vorgänge mittels Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="ed3b1-122">In diesem Schnellstart unterstützt das Bankkonto dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="ed3b1-123">Es enthält eine 10-stellige Zahl, die das Bankkonto eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="ed3b1-124">Es enthält eine Zeichenfolge, die den bzw. die Namen des Besitzers speichert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="ed3b1-125">Der Kontostand kann abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="ed3b1-126">Es akzeptiert Einzahlungen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-126">It accepts deposits.</span></span>
1. <span data-ttu-id="ed3b1-127">Es akzeptiert Abbuchungen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="ed3b1-128">Der anfängliche Kontostand muss positiv sein.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="ed3b1-129">Abbuchungen dürfen nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="ed3b1-130">Definieren des Bankkontotyps</span><span class="sxs-lookup"><span data-stu-id="ed3b1-130">Define the bank account type</span></span>

<span data-ttu-id="ed3b1-131">Sie können beginnen, indem Sie die Grundlagen einer Klasse erstellen, die dieses Verhalten definiert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="ed3b1-132">Die sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-132">It would look like this:</span></span>

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

<span data-ttu-id="ed3b1-133">Bevor wir fortfahren, lassen Sie uns anschauen, was Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="ed3b1-134">Die `namespace`-Deklaration ist eine Möglichkeit, Ihren Code logisch zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="ed3b1-135">Da dieser Schnellstart relativ klein ist, platzieren Sie den gesamten Code in einem einzelnen Namespace.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="ed3b1-136">`public class BankAccount` definiert die Klasse oder den Typ, die/den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="ed3b1-137">Sämtliche Inhalte zwischen `{` und `}`, die der Klassendeklaration folgen, definieren das Verhalten der Klasse.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="ed3b1-138">Die `BankAccount`-Klasse verfügt über fünf ***Member***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="ed3b1-139">Die ersten drei sind ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-139">The first three are ***properties***.</span></span> <span data-ttu-id="ed3b1-140">Eigenschaften sind Datenelemente und können Code aufweisen, der eine Überprüfung oder andere Regeln erzwingt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="ed3b1-141">Die letzten beiden sind ***Methoden***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-141">The last two are ***methods***.</span></span> <span data-ttu-id="ed3b1-142">Methoden sind Codeblöcke, die eine einzelne Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="ed3b1-143">Das Lesen der Namen der einzelnen Member sollte Ihnen oder anderen Entwicklern genug Informationen liefern, um zu verstehen, welche Aufgabe die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="ed3b1-144">Eröffnen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="ed3b1-144">Open a new account</span></span>

<span data-ttu-id="ed3b1-145">Die erste zu implementierende Funktion ist das Eröffnen eines Bankkontos.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="ed3b1-146">Wenn ein Kunde ein Konto eröffnet, muss er einen anfänglichen Kontostand bereitstellen und Informationen über den/die Besitzer dieses Kontos angeben.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="ed3b1-147">Das Erstellen eines neuen Objekts des `BankAccount`-Typs bedeutet Definieren eines ***Konstruktors***, der diese Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="ed3b1-148">Ein ***Konstruktor*** ist ein Member, der den gleichen Namen wie die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="ed3b1-149">Er wird verwendet, um Objekte dieses Klassentyps zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="ed3b1-150">Fügen Sie dem `BankAccount`-Typ folgenden Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="ed3b1-151">Konstruktoren werden bei der Erstellung eines Objekts mit [`new`](../language-reference/keywords/new.md) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="ed3b1-152">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` in ***program.cs*** mit der folgenden Zeile (ersetzen Sie `<name>` durch Ihren Namen):</span><span class="sxs-lookup"><span data-stu-id="ed3b1-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance".);
```

<span data-ttu-id="ed3b1-153">Geben Sie `dotnet run` ein, und beobachten Sie, was passiert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="ed3b1-154">Haben Sie bemerkt, dass die Kontonummer leer ist?</span><span class="sxs-lookup"><span data-stu-id="ed3b1-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="ed3b1-155">Es ist höchste Zeit, dies zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-155">It's time to fix that.</span></span> <span data-ttu-id="ed3b1-156">Die Kontonummer sollten zugewiesen werden, wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="ed3b1-157">Jedoch sollte nicht der Aufrufende für das Erstellen verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="ed3b1-158">Der `BankAccount`-Klassencode sollte wissen, wie neue Kontonummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="ed3b1-159">Eine einfache Möglichkeit hierzu ist, mit einer 10-stelligen Zahl zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="ed3b1-160">Lassen Sie sie bei jeder Erstellung eines neuen Kontos erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-160">Increment it when each new account is created.</span></span> <span data-ttu-id="ed3b1-161">Speichern Sie schließlich die aktuelle Kontonummer, wenn ein Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="ed3b1-162">Fügen Sie der `BankAccount`-Klasse die folgende Memberdeklaration hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="ed3b1-163">Dies ist ein Datenelement.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-163">This is a data member.</span></span> <span data-ttu-id="ed3b1-164">Es ist `private`, d.h. der Zugriff darauf ist nur über Code in der `BankAccount`-Klasse möglich.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="ed3b1-165">Dies ist eine Möglichkeit, die öffentlichen Verantwortlichkeiten (z.B. Besitz einer Kontonummer) von der privaten Implementierung (wie Kontonummern generiert werden) zu trennen. Fügen Sie dem Konstruktor die folgenden zwei Zeilen hinzu, um die Kontonummer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="ed3b1-166">Geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="ed3b1-167">Erstellen von Einzahlungen und Abbuchungen</span><span class="sxs-lookup"><span data-stu-id="ed3b1-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="ed3b1-168">Um ordnungsgemäß zu funktionieren, muss Ihre Bankkontoklasse Einzahlungen und Abbuchungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="ed3b1-169">Einzahlungen und Abbuchungen implementieren Sie, indem Sie eine Erfassung jeder Transaktion für das Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="ed3b1-170">Dies ist vorteilhafter, als den Kontostand bei jeder Transaktion einfachen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="ed3b1-171">Der Verlauf kann zum Überwachen aller Transaktionen und Verwalten täglicher Kontostände verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="ed3b1-172">Indem der Kontostand ggf. aus dem Verlauf aller Transaktionen berechnet wird, werden etwaige Korrekturen von Fehlern in einer einzelnen Transaktion bei der nächsten Berechnung im Kontostand ordnungsgemäß widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="ed3b1-173">Zunächst erstellen wir einen neuen Typ, um eine Transaktion darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="ed3b1-174">Dies ist ein einfacher Typ, der keine Verantwortlichkeiten hat.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="ed3b1-175">Er benötigt einige Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-175">It needs a few properties.</span></span> <span data-ttu-id="ed3b1-176">Erstellen Sie eine neue Datei mit dem Namen ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="ed3b1-177">Fügen Sie ihr folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="ed3b1-178">Nun fügen wir eine <xref:System.Collections.Generic.List%601> von `Transaction`-Objekten der `BankAccount`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="ed3b1-179">Fügen Sie die folgende Deklaration hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="ed3b1-180">Die <xref:System.Collections.Generic.List%601>-Klasse erfordert, dass Sie einen anderen Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="ed3b1-181">Fügen Sie am Anfang von **BankAccount.cs** Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="ed3b1-182">Jetzt ändern wir die Art, in der `Balance` gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="ed3b1-183">Er kann durch Summierung der Werte aller Transaktionen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="ed3b1-184">Ändern Sie die Deklaration von `Balance` in der `BankAccount`-Klasse folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="ed3b1-185">Dieses Beispiel zeigt einen wichtigen Aspekt der ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="ed3b1-186">Jetzt berechnen Sie den Kontostand, wenn ein anderer Programmierer den Wert anfordert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="ed3b1-187">Die Berechnung zählt alle Transaktionen auf und gibt die Summe als aktuellen Kontostand zurück.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="ed3b1-188">Implementieren Sie nun die `MakeDeposit`- und `MakeWithdrawal`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="ed3b1-189">Diese Methoden erzwingen die letzten beiden Regeln: Der anfängliche Kontostand muss positiv sein, und eine Abbuchung darf nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="ed3b1-190">Dies führt das Konzept der ***Ausnahmen*** ein.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="ed3b1-191">Standardmäßig wird eine Ausnahme ausgelöst, um anzuzeigen, dass eine Methode ihre Aufgabe nicht erfolgreich ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="ed3b1-192">Der Typ der Ausnahme und die zugeordnete Nachricht beschreiben den Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="ed3b1-193">Hier löst die `MakeDeposit`-Methode eine Ausnahme aus, wenn der Einzahlungsbetrag negativ ist.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="ed3b1-194">Die `MakeWithdrawal`-Methode löst eine Ausnahme aus, wenn der Abbuchungsbetrag negativ ist, oder wenn aus der Abbuchung ein negativer Kontostand resultiert:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="ed3b1-195">Die [`throw`](../language-reference/keywords/throw.md)-Anweisung **löst** eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-195">The [`throw`](../language-reference/keywords/throw.md) statment **throws** an exception.</span></span> <span data-ttu-id="ed3b1-196">Die Ausführung der aktuellen Methode endet und wird fortgesetzt, wenn ein entsprechender `catch`-Block gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="ed3b1-197">Sie fügen einen `catch`-Block hinzu, um diesen Code etwas später zu testen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="ed3b1-198">Der Konstruktor sollte so geändert werden, dass er eine anfängliche Transaktion hinzufügt, anstatt den Kontostand direkt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="ed3b1-199">Da Sie die `MakeDeposit`-Methode bereits geschrieben haben, rufen Sie sie aus dem Konstruktor auf.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="ed3b1-200">Der fertige Konstruktor sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="ed3b1-201"><xref:System.DateTime.Now?displayProperty=nameWithType> ist eine Eigenschaft, die das aktuelle Datum und die Uhrzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="ed3b1-202">Testen Sie dies durch Hinzufügen von ein paar Einzahlungen und Abbuchungen in Ihrer `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="ed3b1-203">Testen Sie anschließend, ob Sie Fehlerbedingungen abfangen, indem Sie versuchen, ein Konto mit einem negativen Kontostand zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

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

<span data-ttu-id="ed3b1-204">Markieren Sie mit den Anweisungen [`try` und `catch` ](../language-reference/keywords/try-catch.md) einen Codeblock, der Ausnahmen auslösen kann und die Fehler abfangen kann, die Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="ed3b1-205">Mit dem gleichen Verfahren können Sie den Code testen, der bei einem negativen Kontostand eine Ausnahme auslöst:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

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

<span data-ttu-id="ed3b1-206">Speichern Sie die Datei, und geben Sie `dotnet run` zum Testen ein.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="ed3b1-207">Herausforderung – Protokollieren aller Transaktionen</span><span class="sxs-lookup"><span data-stu-id="ed3b1-207">Challenge - log all transactions</span></span>

<span data-ttu-id="ed3b1-208">Um diesen Schnellstart abzuschließen, können Sie die `GetAccountHistory`-Methode schreiben, die einen `string` für den Transaktionsverlauf erstellt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="ed3b1-209">Fügen Sie diese Methode dem `BankAccount`-Typ hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="ed3b1-210">Hier wird die <xref:System.Text.StringBuilder>-Klasse zum Formatieren einer Zeichenfolge verwendet, die eine Zeile für jede Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="ed3b1-211">Sie haben den Zeichenfolgen-Formatierungscode bereits früher in diesen Schnellstarts gesehen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="ed3b1-212">`\t` ist ein neues Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-212">One new character is `\t`.</span></span> <span data-ttu-id="ed3b1-213">Damit wird ein Tabulator zum Formatieren der Ausgabe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="ed3b1-214">Fügen Sie diese Zeile **Program.cs** zum Testen hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed3b1-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="ed3b1-215">Geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed3b1-216">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ed3b1-216">Next Steps</span></span>

<span data-ttu-id="ed3b1-217">Wenn Sie „stecken geblieben“ sind, finden Sie die Quelle für diesen Schnellstart [in unserem GitHub-Repository](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="ed3b1-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="ed3b1-218">Herzlichen Glückwunsch, Sie haben nun alle unsere Schnellstarts absolviert.</span><span class="sxs-lookup"><span data-stu-id="ed3b1-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="ed3b1-219">Wenn Sie mehr lernen möchten, nutzen Sie unsere [Tutorials](../tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed3b1-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>