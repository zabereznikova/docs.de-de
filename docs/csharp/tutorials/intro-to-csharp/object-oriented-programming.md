---
title: Objektorientiertes Programmieren (C#)
description: C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Abstraktion, Kapselung, Vererbung und Polymorphie.
ms.date: 09/30/2020
ms.openlocfilehash: 4ae31e18fcd88870f511e77bb0c555f35394fd1b
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687993"
---
# <a name="object-oriented-programming-c"></a>Objektorientiertes Programmieren (C#)

C# ist eine objektorientierte Programmiersprache. Die folgenden vier bei der objektorientierten Programmierung eingesetzten Verfahren sind besonders wichtig:

- *Abstraktion* bedeutet, dass die unnötigen Details von Typconsumern ausgeblendet werden.
- *Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.
- *Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.
- *Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.

Im vorherigen Tutorial [Einführung in Klassen](introduction-to-classes.md) wurden sowohl *Abstraktion* als auch *Kapselung* vorgestellt. Die `BankAccount`-Klasse hat eine Abstraktion für das Konzept eines Bankkontos bereitgestellt. Sie können ihre Implementierung ändern, ohne den Code zu beeinflussen, in dem die `BankAccount`-Klasse verwendet wurde. Sowohl die `BankAccount`- als auch die `Transaction`-Klasse bieten eine Kapselung der Komponenten, die zum Beschreiben dieser Konzepte im Code erforderlich sind.

In diesem Tutorial wird die Anwendung so erweitert, dass *Vererbung* und *Polymorphie* zum Hinzufügen neuer Features verwendet werden. Außerdem werden Sie der `BankAccount`-Klasse Features hinzufügen und dabei die Verfahren *Abstraktion* und *Kapselung* einsetzen, die Sie im vorherigen Tutorial kennengelernt haben.

## <a name="create-different-types-of-accounts"></a>Erstellen unterschiedlicher Kontotypen

Nach der Erstellung dieses Programms erhalten Sie Anforderungen zum Hinzufügen von Features. Dies funktioniert hervorragend, solange nur ein Bankkontotyp vorhanden ist. Im Laufe der Zeit ändern sich die Anforderungen, und entsprechende Kontotypen werden erforderlich:

- Ein zinsbringendes Konto, auf dem sich am Ende jedes Monats Zinsen ansammeln.
- Eine Kreditlinie, die einen negativen Saldo aufweisen kann, für die aber ggf. monatliche Zinskosten anfallen.
- Ein Prepaid-Geschenkkartenkonto, in das einmal eingezahlt wird und von dem nur ausgezahlt werden kann. Dies kann zu Beginn jedes Monats einmal aufgefüllt werden.

All diese unterschiedlichen Konten ähneln der `BankAccount`-Klasse, die im vorherigen Tutorial definiert wurde. Sie können den betreffenden Code kopieren, die Klassen umbenennen und Änderungen vornehmen. Dieses Verfahren würde kurzfristig funktionieren, aber im Laufe der Zeit mehr Arbeit verursachen. Änderungen müssten über alle betroffenen Klassen kopiert werden.

Stattdessen können Sie neue Bankkontotypen erstellen, die Methoden und Daten von der `BankAccount`-Klasse erben, die im vorherigen Tutorial erstellt wurde. Diese neuen Klassen können die `BankAccount`-Klasse durch das spezifische Verhalten erweitern, das für den jeweiligen Typ erforderlich ist:

```csharp
public class InterestEarningAccount : BankAccount
{
}

public class LineOfCreditAccount : BankAccount
{
}

public class GiftCardAccount : BankAccount
{
}
```

Jede dieser Klassen *erbt* das gemeinsame Verhalten von der gemeinsamen *Basisklasse*, der `BankAccount`-Klasse. Schreiben Sie die Implementierungen für neue und andere Funktionen in jede der *abgeleiteten Klassen*.  Diese abgeleiteten Klassen verfügen bereits über das gesamte Verhalten, das in der `BankAccount`-Klasse definiert ist.

Es empfiehlt sich, jede neue Klasse in einer anderen Quelldatei zu erstellen. In [Visual Studio](https://visualstudio.com) können Sie mit der rechten Maustaste auf das Projekt klicken und *Klasse hinzufügen* auswählen, um eine neue Klasse in einer neuen Datei hinzuzufügen. Wählen Sie in [Visual Studio Code](https://code.visualstudio.com) die Option *Datei* und dann *Neu* aus, um eine neue Quelldatei zu erstellen. Benennen Sie in beiden Tools die Datei entsprechend dem Klassennamen um: *InterestEarningAccount.cs*, *LineOfCreditAccount.cs* und *GiftCardAccount.cs*.

Wenn Sie die Klassen wie im obigen Beispiel gezeigt erstellen, werden Sie feststellen, dass keine der abgeleiteten Klassen kompiliert wird. Ein Konstruktor ist für die Initialisierung eines Objekts verantwortlich. Der Konstruktor einer abgeleiteten Klasse muss die abgeleitete Klasse initialisieren und Anweisungen dazu bereitstellen, wie das in der abgeleiteten Klasse enthaltene Basisklassenobjekt zu initialisieren ist. Die ordnungsgemäße Initialisierung erfolgt normalerweise ohne zusätzlichen Code. Die `BankAccount`-Klasse deklariert einen öffentlichen Konstruktor mit der folgenden Signatur:

```csharp
public BankAccount(string name, decimal initialBalance)
```

Der Compiler generiert keinen Standardkonstruktor, wenn Sie selbst einen Konstruktor definieren. Dies bedeutet, dass jede abgeleitete Klasse diesen Konstruktor explizit aufrufen muss. Sie deklarieren einen Konstruktor, der Argumente an den Basisklassenkonstruktor übergeben kann.  Der folgende Code zeigt den Konstruktor für `InterestEarningAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="DerivedConstructor":::

Die Parameter für diesen neuen Konstruktor entsprechen dem Parametertyp und den Namen des Basisklassenkonstruktors. Verwenden Sie die `: base()`-Syntax, um einen Aufruf an einen Basisklassenkonstruktor anzugeben. Einige Klassen definieren mehrere Konstruktoren, und mit dieser Syntax können Sie den aufzurufenden Basisklassenkonstruktor auswählen. Nachdem Sie die Konstruktoren aktualisiert haben, können Sie den Code für die einzelnen abgeleiteten Klassen entwickeln. Die Anforderungen für die neuen Klassen können wie folgt angegeben werden:

- Ein zinsbringendes Konto:
  - Erhält eine Gutschrift von 2 % des Saldos am Monatsende.
- Eine Kreditlinie:
  - Kann einen negativen Saldo aufweisen, aber als absoluter Wert die Kreditlinie nicht überschreiten.
  - Es fallen monatlich Zinsgebühren an, wenn der Saldo am Monatsende nicht 0 ist.
  - Für jede Abbuchung, die die Kreditlinie überschreitet, wird eine Gebühr erhoben.
- Ein Geschenkkartenkonto:
  - Kann einmal monatlich am letzten Tag des Monats mit einem angegebenen Betrag aufgefüllt werden.

Sie sehen, dass alle drei Kontotypen über eine Aktion verfügen, die am Ende jedes Monats stattfindet. Jeder Kontotyp führt jedoch unterschiedliche Aufgaben aus. Sie verwenden *Polymorphie*, um diesen Code zu implementieren. Erstellen Sie eine einzelne `virtual`-Methode in der `BankAccount`-Klasse:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="DeclareMonthEndTransactions":::

Der obige Code zeigt, wie Sie mit dem `virtual`-Schlüsselwort eine Methode in der Basisklasse deklarieren, für die eine abgeleitete Klasse eine andere Implementierung bereitstellen kann. Bei einer `virtual`-Methode handelt es sich um eine Methode, bei der jede abgeleitete Klasse eine Neuimplementierung auswählen kann. Die abgeleiteten Klassen verwenden das `override`-Schlüsselwort, um die neue Implementierung zu definieren. Dieser Vorgang wird normalerweise als „Überschreiben der Basisklassenimplementierung“ bezeichnet. Das `virtual`-Schlüsselwort gibt an, dass abgeleitete Klassen das Verhalten außer Kraft setzen können. Sie können auch `abstract`-Methoden deklarieren, bei denen abgeleitete Klassen das Verhalten außer Kraft setzen müssen. Die Basisklasse stellt keine Implementierung für eine `abstract`-Methode bereit. Als nächstes müssen Sie die Implementierung für zwei der neu erstellten Klassen definieren. Beginnen Sie mit dem `InterestEarningAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="ApplyMonthendInterest":::

Fügen Sie dem `LineOfCreditAccount` folgenden Code hinzu. Der Code negiert den Saldo, um eine positive Zinsgebühr zu berechnen, die vom Konto abgebucht wird:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ApplyMonthendInterest":::

Für die `GiftCardAccount`-Klasse sind zwei Änderungen erforderlich, um die Funktion am Monatsende zu implementieren. Ändern Sie zunächst den Konstruktor so, dass er einen optionalen Betrag enthält, der monatlich hinzugefügt werden soll:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="GiftCardAccountConstruction":::

Der Konstruktor stellt einen Standardwert für den `monthlyDeposit`-Wert bereit, sodass Aufrufer keine `0` eingeben müssen, wenn keine monatliche Einzahlung erfolgt. Überschreiben Sie als nächstes die `PerformMonthEndTransactions`-Methode, um die monatliche Einzahlung hinzuzufügen, falls sie im Konstruktor auf einen Wert ungleich 0 festgelegt wurde:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="AddMonthlyDeposit":::

Durch die Überschreibung wird die im Konstruktor festgelegte monatliche Einzahlung angewendet. Fügen Sie der `Main`-Methode den folgenden Code hinzu, um diese Änderungen für das `GiftCardAccount` und das `InterestEarningAccount` zu testen:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="FirstTests":::

Überprüfen Sie die Ergebnisse. Fügen Sie jetzt einen ähnlichen Testcode für das `LineOfCreditAccount` hinzu:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Wenn Sie den vorangehenden Code hinzufügen und das Programm ausführen, wird in etwa folgender Fehler angezeigt:

```console
Unhandled exception. System.ArgumentOutOfRangeException: Amount of deposit must be positive (Parameter 'amount')
   at OOProgramming.BankAccount.MakeDeposit(Decimal amount, DateTime date, String note) in BankAccount.cs:line 42
   at OOProgramming.BankAccount..ctor(String name, Decimal initialBalance) in BankAccount.cs:line 31
   at OOProgramming.LineOfCreditAccount..ctor(String name, Decimal initialBalance) in LineOfCreditAccount.cs:line 9
   at OOProgramming.Program.Main(String[] args) in Program.cs:line 29
```

> [!NOTE]
> Die tatsächliche Ausgabe enthält den vollständigen Pfad zum Ordner mit dem Projekt. Die Ordnernamen wurden zur Kürzung ausgelassen. Abhängig von Ihrem Codeformat können auch die Zeilennummern leicht abweichen.

Dieser Code verursacht einen Fehler, weil `BankAccount` von einem Anfangssaldo größer als 0 ausgeht. Eine weitere Annahme in der `BankAccount`-Klasse besteht darin, dass der Saldo nicht negativ sein kann. Stattdessen wird jede Abbuchung, die das Konto überzieht, abgelehnt. Beide Annahmen müssen geändert werden. Das Kreditlinienkonto beginnt bei 0 und weist im Allgemeinen einen negativen Saldo auf. Wenn ein Kunde zu viel Geld aufnimmt, fällt zudem eine Gebühr an. Die Transaktion wird akzeptiert, sie kostet lediglich mehr. Die erste Regel kann implementiert werden, indem Sie dem `BankAccount`-Konstruktor, der den Mindestsaldo angibt, ein optionales Argument hinzufügen. Der Standardwert ist `0`. Die zweite Regel erfordert einen Mechanismus, der es abgeleiteten Klassen ermöglicht, den Standardalgorithmus zu ändern. In gewisser Hinsicht fragt die Basisklasse beim abgeleiteten Typ ab, was bei einer Überziehung geschehen soll. Das Standardverhalten besteht darin, die Transaktion durch Auslösen einer Ausnahme abzulehnen.

Fügen wir zuerst einen zweiten Konstruktor hinzu, der einen optionalen `minimumBalance`-Parameter enthält. Dieser neue Konstruktor führt alle Aktionen aus, die vom vorhandenen Konstruktor durchgeführt werden. Außerdem legt er die Eigenschaft des Mindestsaldos fest. Sie könnten den Text des vorhandenen Konstruktors kopieren. Dies bedeutet jedoch, dass in Zukunft zwei Stellen geändert werden müssen. Stattdessen können Sie die *Konstruktorverkettung* verwenden, sodass ein Konstruktor einen anderen aufruft. Der folgende Code zeigt die beiden Konstruktoren und das neue zusätzliche Feld:

 :::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="ConstructorModifications":::

Der obige Code zeigt zwei neue Verfahren. Erstens ist das Feld `minimumBalance` als `readonly` markiert. Somit kann der Wert nach Erstellen des Objekts nicht mehr geändert werden. Nach dem Erstellen von `BankAccount` kann `minimumBalance` nicht mehr geändert werden. Zweitens verwendet der Konstruktor, der zwei Parameter akzeptiert, `: this(name, initialBalance, 0) { }` als Implementierung. Der `: this()`-Ausdruck ruft den anderen Konstruktor auf – den Konstruktor mit drei Parametern. Durch dieses Verfahren können Sie auch dann eine einzige Implementierung für die Initialisierung eines Objekts verwenden, wenn im Clientcode einer von vielen Konstruktoren ausgewählt werden kann.

Diese Implementierung ruft `MakeDeposit` nur dann auf, wenn der anfängliche Saldo größer als `0`ist. Dadurch wird die Regel beibehalten, dass Einzahlungen positiv sein müssen, und dennoch ermöglicht, dass das Kreditkonto bei einem Saldo von `0` geöffnet bleibt.

Da die `BankAccount`-Klasse jetzt ein schreibgeschütztes Feld für den Mindestsaldo aufweist, besteht die letzte Änderung darin, den festen Code `0` in der `MakeWithdrawal`-Methode in `minimumBalance` zu ändern:

```csharp
if (Balance - amount < minimumBalance)
```

Nach Erweiterung der `BankAccount`-Klasse können Sie den `LineOfCreditAccount`-Konstruktor so ändern, dass er den neuen Basiskonstruktor aufruft, wie im folgenden Code gezeigt:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ConstructLineOfCredit":::

Beachten Sie, dass der `LineOfCreditAccount`-Konstruktor das Vorzeichen des Parameters `creditLimit` ändert, sodass er der Bedeutung des Parameters `minimumBalance` entspricht.

## <a name="different-overdraft-rules"></a>Verschiedene Regeln für Überziehung

Das letzte hinzuzufügende Feature ermöglicht es dem `LineOfCreditAccount`, für das Überziehen des Kreditlimits eine Gebühr zu erheben, statt die Transaktion abzulehnen.

Ein Verfahren besteht darin, eine virtuelle Funktion zu definieren, in der das erforderliche Verhalten implementiert wird. Die `BankAccount`-Klasse gestaltet die `MakeWithdrawal`-Methode in zwei Methoden um. Die neue Methode führt die angegebene Aktion aus, wenn der Saldo durch die Abbuchung unter den Mindestbetrag fällt. Die vorhandene `MakeWithdrawal`-Methode enthält den folgenden Code:

```csharp
public void MakeWithdrawal(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of withdrawal must be positive");
    }
    if (Balance - amount < minimumBalance)
    {
        throw new InvalidOperationException("Not sufficient funds for this withdrawal");
    }
    var withdrawal = new Transaction(-amount, date, note);
    allTransactions.Add(withdrawal);
}
```

Ersetzen Sie den Code durch folgenden Code:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="RefactoredMakeWithdrawal":::

Die hinzugefügte Methode ist `protected`, was bedeutet, dass sie nur von abgeleiteten Klassen aufgerufen werden kann. Diese Deklaration verhindert, dass die Methode von anderen Clients aufgerufen wird. Zudem ist sie `virtual`, damit abgeleitete Klassen das Verhalten ändern können. Der Rückgabetyp ist eine `Transaction?`. Die `?`-Anmerkung gibt an, dass die Methode `null` zurückgeben darf. Fügen Sie im `LineOfCreditAccount` die folgende Implementierung hinzu, damit bei Überschreiten des Abbuchungslimits eine Gebühr erhoben wird:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="AddOverdraftFee":::

Die Außerkraftsetzung gibt bei Überziehen des Kontos eine Gebührentransaktion zurück. Wenn die Abbuchung den Grenzwert nicht überschreitet, gibt die Methode eine `null`-Transaktion zurück. Dies bedeutet, dass keine Gebühren erhoben werden. Testen Sie diese Änderungen, indem Sie der `Main`-Methode in der `Program`-Klasse den folgenden Code hinzufügen:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Führen Sie das Programm aus, und überprüfen Sie die Ergebnisse.

## <a name="summary"></a>Zusammenfassung

Wenn Sie nicht weiterkommen, sehen Sie sich die Quelle für dieses Tutorial [in unserem GitHub-Repository](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/object-oriented-programming) an.

In diesem Tutorial wurden viele Verfahren vorgestellt, die bei der objektorientierten Programmierung verwendet werden:

- Sie haben *Abstraktion* eingesetzt, als Sie in jeder Klasse viele Details als `private` festgelegt haben.
- Sie haben *Kapselung* verwendet, als Sie Klassen für jeden der verschiedenen Kontotypen definiert haben. Diese Klassen beschreiben das Verhalten für den jeweiligen Kontotyp.
- Sie haben *Vererbung* verwendet, als Sie die bereits in der `BankAccount`-Klasse erstellte Implementierung genutzt haben, um Code zu sparen.
- Sie haben *Polymorphie* eingesetzt, indem Sie `virtual`-Methoden erstellt haben, die von abgeleiteten Klassen überschrieben werden können, um ein bestimmtes Verhalten für den jeweiligen Kontotyp zu erzielen.

Herzlichen Glückwunsch! Sie haben unsere Tutorials zur Einführung in C# vollständig abgeschlossen. Wenn Sie mehr erfahren möchten, sehen Sie sich weitere [Tutorials](../index.md) an.
