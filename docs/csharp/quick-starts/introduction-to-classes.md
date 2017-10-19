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
# <a name="introduction-to-classes"></a>Einführung in Klassen

In dieser Lektion wird davon ausgegangen, dass Sie installiert haben [.NET Core SDK](http://dot.net/core), und einen Editor Ihrer Wahl. Wenn Sie keinen haben, versuchen Sie es [Visual Studio Code](https://code.visualstudio.com/), oder [Visual Studio](https://www.visualstudio.com/) auf Mac oder Windows.

## <a name="create-your-application"></a>Erstellen Sie die Anwendung

Verwenden ein terminal-Fenster, erstellen Sie ein Verzeichnis namens **Klassen**. Sie müssen es die Anwendung erstellen. Ändern Sie in diesem Verzeichnis und Dateityp `dotnet new console` im Konsolenfenster angezeigt. Dieser Befehl erstellt die Anwendung. Open **"Program.cs"**. Es sollte wie folgt aussehen:

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

In diesem Schnellstart können Sie ihm neue Typen erstellen, die ein Bankkonto darstellen. Entwickler werden i. d. r. jede Klasse in einer anderen Text-Datei definieren. Dadurch einfacher zu verwalten, wie ein Programm an Größe zunimmt.  Erstellen Sie eine neue Datei mit dem Namen **BankAccount.cs** in der **Klassen** Verzeichnis. 

Diese Datei enthält die Deefinition von einem ***Bankkonto***. -Objekt Oriented Programmierung organisiert Code durch Erstellen von Typen in Form von ***Klassen***. Diese Klassen enthalten den Code, der eine bestimmte Entität darstellt. Die `BankAccount` -Klasse stellt ein Bankkonto dar. Der Code implementiert bestimmte Vorgänge über Methoden und Eigenschaften. In diesem Schnellstart unterstützt das Konto dieses Verhalten:

1. Es wurde eine 10-stellige-Zahl, die das Konto eindeutig identifiziert.
1. Es wurde eine Zeichenfolge, die den oder die Namen der Besitzer speichert.
1. Das Guthaben kann abgerufen werden.
1. Er akzeptiert einzahlungen.
1. Er akzeptiert Rücknahmen.
1. Der erste Saldo muss positiv sein.
1. Rücknahmen können nicht in einen negativen Ausgleich führen.

## <a name="define-the-bank-account-type"></a>Definieren Sie den Typ des Bankkontos

Sie können zunächst erstellen die Grundlagen einer Klasse, die dieses Verhalten definiert. Es würde wie folgt aussehen:

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

Bevor Sie fortfahren, werfen wir einen Blick auf, was Sie erstellt haben.  Die `namespace` Deklaration bietet eine Möglichkeit, Ihren Code logisch zu organisieren. Dieser Schnellstart ist relativ klein ist, damit Sie den Code in einem einzelnen Namespace platzieren müssen. 

`public class BankAccount`definiert die Klasse oder ein Typ, Sie erstellen. Sämtliche Inhalte innerhalb der `{` und `}` , folgt die Klasse Deklaration definiert das Verhalten der-Klasse. Es gibt fünf ***Elemente*** von der `BankAccount` Klasse. Die ersten drei sind ***Eigenschaften***. Eigenschaften können sind die Datenelemente und Code, der Überprüfung oder einer anderen Regeln erzwungen. Die letzten beiden ***Methoden***. Methoden werden Codeblöcke, wie eine einzelne Funktion. Beim Lesen der Namen der einzelnen Elemente können genug Informationen, oder ein anderer Entwickler zu verstehen, was bewirkt, dass die Klasse.

## <a name="open-a-new-account"></a>Öffnen Sie ein neues Konto

Die erste Funktion implementieren, besteht darin, ein Bankkonto zu öffnen. Wenn ein Kunde ein Konto geöffnet wird, müssen sie eine erste Saldo und die Informationen über die Besitzer oder den Besitzer dieses Kontos angeben. 

Erstellen eines neuen Objekts von der `BankAccount` Typ bedeutet definieren eine ***Konstruktor*** , die diese Werte zuweist. Ein ***Konstruktor*** ist ein Element, das den gleichen Namen wie die Klasse hat. Es wird verwendet, um Objekte dieses Klassentyps zu initialisieren. Fügen Sie den folgenden Konstruktor hinzu der `BankAccount` Typ:

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

Konstruktoren werden aufgerufen, bei der Erstellung eines Objekts mit [ `new` ](../language-reference/keywords/new.md). Ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` in ***"Program.cs"*** mit der folgenden Zeile (ersetzen Sie `<name>` durch den Namen Ihres):

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance".);
```

Typ `dotnet run` zu sehen, was passiert.  

Haben Sie bemerkt, dass die Kontonummer leer ist? Es ist Zeit, die behoben werden kann. Die Kontonummer sollten zugewiesen werden, wenn das Objekt erstellt wird. Jedoch sollte nicht der Verantwortung des Aufrufers, ihn zu erstellen. Die `BankAccount` Klassencode sollten wissen, wie neue Kontonummern zuweisen.  Eine einfache Möglichkeit hierzu ist eine Zahl mit 10-Ziffern. Erhöhen sie bei jeder neues Konto erstellt wird. Speichern Sie schließlich Nummer des aktuellen Kontos auf, wenn ein Objekt erstellt wird.

Fügen Sie die folgenden Memberdeklaration zu der `BankAccount` Klasse:

```csharp
private static int accountNumberSeed = 1234567890;
```

Dies ist ein Datenmember. Es wurde `private`, dies bedeutet, dass nur über möglich, Code innerhalb der `BankAccount` Klasse. Dies ist eine Möglichkeit, unterteilen Sie die öffentliche Aufgaben (z. B. über eine Kontonummer) über die private Implementierung (wie Kontonummern generiert werden.) Fügen Sie die folgenden zwei Zeilen, an den Konstruktor der Kontonummer zuweisen:

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

Typ `dotnet run` um die Ergebnisse anzuzeigen.

## <a name="create-deposits-and-withdrawals"></a>Erstellen Sie einzahlungen und Rücknahmen

Ihr Bankkonto-Klasse muss zum Akzeptieren von einzahlungen und Rücknahmen ordnungsgemäß funktioniert. Wir implementieren einzahlungen und Rücknahmen durch das Erstellen einer Erfassung jeder Transaktion für das Konto ein. Die weist einige Vorteile gegenüber der Saldo für jede Transaktion einfach aktualisieren. Der Verlauf kann alle Transaktionen zu überwachen und Verwalten von täglichen Bilanzen verwendet werden. Durch das Berechnen des Saldo aus dem Verlauf aller Transaktionen, bei Bedarf, werden alle Fehler in einer einzigen Transaktion, die behoben wurden ordnungsgemäß in das Guthaben auf die nächste Berechnung berücksichtigt.

Zunächst erstellen einen neuen Typ aus, um eine Transaktion darzustellen. Dies ist ein einfacher Typ, der Aufgaben aufweist. Einige Eigenschaften benötigt. Erstellen Sie eine neue Datei mit dem Namen ***Transaction.cs***. Im folgenden Code hinzufügen:

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

Nun fügen wir eine <xref:System.Collections.Generic.List%601> von `Transaction` -Objekte und die `BankAccount` Klasse. Fügen Sie die folgende Deklaration hinzu:

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

Die <xref:System.Collections.Generic.List%601> Klasse erfordert, dass Sie einen anderen Namespace zu importieren. Fügen Sie am Anfang des Folgendes **BankAccount.cs**:

```csharp
using System.Collections.Generic;
```

Jetzt ändern wie die `Balance` gemeldet wird.  Sie können die Werte aller Transaktionen gefunden werden. Ändern Sie die Deklaration von `Balance` in die `BankAccount` Klasse, um die folgenden:

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

Dieses Beispiel zeigt einen wichtigen Aspekt der ***Eigenschaften***. Sie sind jetzt das Guthaben berechnet, wenn der Wert einer anderen Programmierer anfordert. Die Berechnung Listet alle Transaktionen auf und gibt die Summe als dem aktuellen Saldo.

Als Nächstes implementieren die `MakeDeposit` und `MakeWithdrawal` Methoden. Diese Methoden erzwingt die letzten beiden Regeln:, dass der erste Saldo muss positiv sein und eine Abhebung, die einen negativen Ausgleich nicht erstellt werden muss. 

Dies führt das Konzept der ***Ausnahmen***. Die Standardmethode für gibt an, dass ihre Arbeit von eine Methode erfolgreich abgeschlossen werden kann, ist eine Ausnahme auslöst. Der Typ der Ausnahme und die Nachricht zugeordnet werden den Fehler beschrieben. Hier wird die `MakeDeposit` Methode löst eine Ausnahme aus, wenn der Anteil der Einzahlung negativ ist. Die `MakeWithdrawal` Methode löst eine Ausnahme aus, wenn der Betrag der Abbuchung negativ ist oder wenn die Abbuchung Anwenden einer negativen Saldo ergibt:

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

Die [ `throw` ](../language-reference/throw.md) Anweisung **löst** eine Ausnahme. Ausführung der aktuellen Methode beendet wird, und wird fortgesetzt, wenn ein entsprechender `catch` -Block gefunden wird. Fügen Sie eine `catch` Block, um diesen Code etwas später zu testen.

Der Konstruktor sollte eine Änderung abgerufen, sodass Fügt eine anfängliche, anstatt als das Guthaben direkt aktualisieren. Da Sie bereits geschrieben haben die `MakeDeposit` -Methode, aus dem Konstruktor aufgerufen wird. Die fertige Konstruktor sollte wie folgt aussehen:

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<xref:System.DateTime.Now?displayProperty=nameWithType>ist eine Eigenschaft, die das aktuelle Datum und die Uhrzeit zurückgibt. Testen Sie dies durch Hinzufügen von wenigen einzahlungen und Rücknahmen in Ihre `Main` Methode:

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

Anschließend testen Sie, dass Sie fehlerbedingungen abgefangen werden, indem Sie versuchen, ein Konto mit einem negativen Saldo zu erstellen:

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

Verwenden Sie die [ `try` und `catch` Anweisungen](../language-reference/keywords/try-catch.md) um einen Codeblock zu markieren, die Ausnahmen auslösen kann, und um diese Fehler abzufangen, die Sie erwarten. Das gleiche Verfahren können Sie um den Code zu testen, der für eine negative Gleichgewicht auslöst:

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

Speichern Sie die Datei und den Typ `dotnet run` ausprobieren.

## <a name="challenge---log-all-transactions"></a>Herausforderung: alle Transaktionen protokollieren

Um diesem Schnellstart abgeschlossen haben, können Sie schreiben die `GetAccountHistory` -Methode, erstellt eine `string` für den Transaktionsverlauf. Fügen Sie diese Methode, um die `BankAccount` Typ:

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

Hierdurch wird unter Verwendung der <xref:System.Text.StringBuilder> Klasse zum Formatieren einer Zeichenfolge, die eine Zeile für jede Transaktion enthält. Die Zeichenfolge, die Formatierung von Code in diese Schnellstarts angezeigt. Ist ein neues Zeichen `\t`. Die Fügt einer Registerkarte, um die Ausgabe zu formatieren.

Fügen Sie diese Zeile zum Testen in **"Program.cs"**:

```csharp
Console.WriteLine(account.GetAccountHistory());
```

Typ `dotnet run` um die Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie hängen bleiben erhalten haben, sehen Sie die Quelle für dieses Schnellstarts [in unserer GitHub-Repository](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)

Herzlichen Glückwunsch, Sie haben nun alle unsere Schnellstartanleitung. Wenn Sie weitere eager sind, versuchen Sie es unseren [Lernprogramme](../tutorials/index.md)