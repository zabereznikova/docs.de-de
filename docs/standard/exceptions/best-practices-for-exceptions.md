---
title: Best Practices für Ausnahmen – .NET
description: Erfahren Sie über bewährte Methoden für Ausnahmen, z. B. die Verwendung von „try/catch/finally“, den Umgang mit gängigen Zuständen ohne Ausnahmen und die Verwendung von vordefinierter .NET-Ausnahmetypen.
ms.date: 12/05/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 815dcc81cf41465bffd1515d366a66ff558304fa
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828230"
---
# <a name="best-practices-for-exceptions"></a>Best Practices für Ausnahmen

Eine ausgereifte App behandelt Ausnahmen und Fehler, um App-Abstürze zu verhindern. In diesem Abschnitt werden Best Practices für die Behandlung und Erstellung von Ausnahmen beschrieben.

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a>Verwenden Sie Try/Catch/Finally-Blöcke zum Beheben von Fehlern oder zum Freigeben von Ressourcen.

Betten Sie Code, der Ausnahmen erzeugen kann, in `try`/`catch`-Blöcke ein, ***damit*** ihr Code nach diesen Ausnahmen wiederhergestellt werden kann. Ordnen Sie Ausnahmen in `catch`-Blöcken immer von der am stärksten abgeleiteten zur am wenigsten abgeleiteten. Alle Ausnahmen sind von <xref:System.Exception> abgeleitet. Stärker abgeleitete Ausnahmen werden nicht durch eine catch-Klausel verarbeitet, der eine catch-Klausel für eine Ausnahmebasisklasse vorangestellt ist. Wenn Ihr Code aus einer Ausnahme nicht wiederhergestellt werden kann, fangen Sie diese Ausnahme nicht ab. Aktivieren Sie Methoden weiter oben in der Aufrufliste, um nach Möglichkeit eine Wiederherstellung auszuführen.

Bereinigen Sie die Ressourcen, die mit `using`-Anweisungen oder `finally`-Blöcken zugeordnet wurden. Bevorzugen Sie `using`-Anweisungen, um Ressourcen automatisch zu bereinigen, wenn Ausnahmen ausgelöst werden. Verwenden Sie `finally`-Blöcke, um Ressourcen zu bereinigen, die <xref:System.IDisposable> nicht implementieren. Code in einer `finally`-Klausel wird fast immer – d. h. auch bei Auslösen einer Ausnahme – ausgeführt.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Behandeln häufig auftretender Bedingungen ohne Auslösen von Ausnahmen

Bedingungen, deren Auftreten wahrscheinlich ist, die aber möglicherweise eine Ausnahme auslösen, sollten Sie so behandeln, dass die Ausnahme vermieden wird. Wenn Sie z. B. versuchen, eine bereits geschlossene Verbindung erneut zu schließen, erhalten Sie eine `InvalidOperationException`. Dies können Sie verhindern, indem Sie eine `if`-Anweisung verwenden, um den Verbindungsstatus zu überprüfen, bevor Sie versuchen, die Verbindung zu schließen.

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

Wenn Sie den Verbindungsstatus vor dem Schließen der Verbindung nicht überprüfen, können Sie die `InvalidOperationException` abfangen.

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

Die Wahl der Methode hängt von der erwarteten Häufigkeit des Ereignisses ab.

- Verwenden Sie die Ausnahmebehandlung, wenn das Ereignis nicht sehr häufig auftritt, d.  h. wenn es wirklich ungewöhnlich ist und auf einen Fehler hinweist (z. B. ein unerwartetes Dateiende). Wenn Sie die Ausnahmebehandlung verwenden, wird weniger Code in normalen Bedingungen ausgeführt.

- Wenn das Ereignis regelmäßig auftritt und als Teil der normalen Programmausführung betrachtet werden kann, suchen Sie im Code nach Fehlerbedingungen. Wenn Sie auf gängige Fehlerbedingungen prüfen, wird weniger Code ausgeführt, da Ausnahmen vermieden werden.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Entwerfen von Klassen mit dem Ziel, Ausnahmen zu vermeiden

Eine Klasse kann Methoden oder Eigenschaften bereitstellen, mit deren Hilfe ein Aufruf vermieden werden kann, der andernfalls eine Ausnahme auslösen würde. Beispielsweise stellt eine <xref:System.IO.FileStream>-Klasse Methoden bereit, mithilfe derer bestimmt werden kann, ob das Ende der Datei erreicht wurde. Dadurch kann die Ausnahme vermieden werden, die andernfalls durch den Versuch ausgelöst würde, nach Erreichen des Dateiendes weiterzulesen. Das folgende Beispiel zeigt, wie eine Datei bis zum Ende gelesen werden kann, ohne dass eine Ausnahme ausgelöst wird.

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

Eine andere Möglichkeit zum Vermeiden von Ausnahmen besteht darin, bei sehr häufig auftretenden Fehlern NULL (oder einen Standardwert) zurückzugeben, statt eine Ausnahme auszulösen. Ein sehr häufig auftretender Fehler kann durchaus als normale Ablaufsteuerung betrachtet werden. Indem Sie in diesen Fällen NULL (oder einen Standardwert) zurückgeben, minimieren Sie die Auswirkungen auf die Leistung einer App.

Ob Sie bei Werttypen `Nullable<T>` oder einen Standardwert als Fehlerindikator verwenden, richtet sich nach Ihrer speziellen App. Durch Verwendung von `Nullable<Guid>` wird `default` zu `null` statt zu `Guid.Empty`. Manchmal wird durch Hinzufügen von `Nullable<T>` klarer, ob ein Wert vorhanden oder nicht vorhanden ist. Andererseits kann das Hinzufügen von `Nullable<T>` dazu führen, dass zusätzliche Fälle geprüft werden müssen, die eigentlich nicht notwendig sind und nur zu potenzielle Fehlerquellen führen.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Auslösen von Ausnahmen statt Zurückgeben eines Fehlercodes

Ausnahmen sorgen dafür, dass Fehler nicht unbemerkt bleiben, nur weil der aufrufende Code einen Rückgabecode nicht überprüft hat.

## <a name="use-the-predefined-net-exception-types"></a>Verwenden der vordefinierten .NET-Ausnahmetypen

Verwenden Sie eine neue Ausnahmeklasse nur dann, wenn sich keine vordefinierte Klasse anbietet. Zum Beispiel:

- Lösen Sie eine <xref:System.InvalidOperationException> immer dann aus, wenn aufgrund des aktuellen Status des Objekts weder ein Eigenschaftensatz noch ein Methodenaufruf geeignet sind.

- Lösen Sie eine <xref:System.ArgumentException> oder eine der von <xref:System.ArgumentException> abgeleiteten vordefinierten Klassen in dem Fall aus, dass ungültige Parameter übergeben werden.

## <a name="end-exception-class-names-with-the-word-exception"></a>Verwenden des Worts `Exception` am Ende von Ausnahmeklassennamen

Wenn eine benutzerdefinierte Ausnahme erforderlich ist, benennen Sie diese entsprechend, und leiten Sie sie von der <xref:System.Exception>-Klasse ab. Beispiel:

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a>Einschließen von drei Konstruktoren in benutzerdefinierte Ausnahmeklassen

Verwenden Sie beim Erstellen eigener Ausnahmeklassen mindestens die drei gängigen Konstruktoren: den parameterlosen Konstruktor, einen Konstruktor, der eine Zeichenfolgenmeldung entgegennimmt, und einen Konstruktor, der eine Zeichenfolgenmeldung und eine innere Ausnahme entgegennimmt.

- <xref:System.Exception.%23ctor>, der Standardwerte verwendet.

- <xref:System.Exception.%23ctor%28System.String%29>, der eine Zeichenfolgenmeldung entgegennimmt.

- <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, der eine Zeichenfolgenmeldung und eine interne Ausnahme entgegennimmt.

Ein Beispiel finden Sie unter [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Sicherstellen, dass Ausnahmedaten bei der Remoteausführung von Code verfügbar sind

Stellen Sie beim Erstellen benutzerdefinierter Ausnahmen sicher, dass die Metadaten für die Ausnahmen für remote ausgeführten Code verfügbar sind.

In .NET-Implementierungen, die App-Domänen unterstützen, können Ausnahmen beispielsweise über mehrere App-Domänen hinweg auftreten. Nehmen wir an, App-Domäne A erstellt App-Domäne B, und in App-Domäne B wird Code ausgeführt, der eine Ausnahme auslöst. Damit App-Domäne A die Ausnahme ordnungsgemäß abfängt und behandelt, muss sie die Assembly finden, in der die durch App-Domäne B ausgelöste Ausnahme enthalten ist. Wenn App-Domäne B eine Ausnahme auslöst, die in einer Assembly in ihrer Anwendungsbasis, nicht aber in der Anwendungsbasis von App-Domäne A enthalten ist, kann App-Domäne A die Ausnahme nicht finden. Daraufhin löst die Common Language Runtime eine <xref:System.IO.FileNotFoundException> aus. Um diese Situation zu vermeiden, haben Sie zwei Möglichkeiten, die Assembly mit den Ausnahmeinformationen bereitzustellen:

- Sie legen die Assembly in einer gemeinsamen Anwendungsbasis ab, die von beiden App-Domänen verwendet wird.

    \- oder -

- Sofern die Domänen keine gemeinsame Anwendungsbasis verwenden, signieren Sie die Assembly, in der die Ausnahmeinformationen enthalten sind, mit einem starken Namen und legen sie in einem globalen Assemblycache ab.

## <a name="use-grammatically-correct-error-messages"></a>Verwenden grammatisch korrekter Fehlermeldungen

Verfassen Sie klar verständliche Meldungen und achten Sie vor allem am Ende eines Satzes auf korrekte Satzzeichen. Jeder Satz in der Zeichenfolge, der der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft zugeordnet ist, muss mit einem Punkt enden. So ist der Satz „In der Protokolltabelle ist ein Überlauf aufgetreten.“ ein Beispiel für eine angemessene Meldungszeichenfolge.

## <a name="include-a-localized-string-message-in-every-exception"></a>Einschließen einer lokalisierten Meldungszeichenfolge in jede Ausnahme

Die dem Benutzer angezeigte Fehlermeldung wird von der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft der ausgelösten Ausnahme abgeleitet, nicht vom Namen der Ausnahmeklasse. In der Regel können Sie der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft einen Wert zuweisen, indem Sie die Meldungszeichenfolge an das `message`-Argument eines [Ausnahmekonstruktors](xref:System.Exception.%23ctor%2A) übergeben.

Sie sollten für lokalisierte Anwendungen eine lokalisierte Meldungszeichenfolge für jede Ausnahme angeben, die Ihre Anwendung ausgeben könnte. Verwenden Sie Ressourcendateien, um lokalisierte Fehlermeldungen zur Verfügung zu stellen. Weitere Informationen zum Lokalisieren von Anwendungen und zum Abrufen lokalisierter Zeichenfolgen finden Sie in den folgenden Artikeln:

- [Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen](how-to-create-localized-exception-messages.md)
- [Ressourcen in Desktop-Apps](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Bereitstellen zusätzlicher Eigenschaften in benutzerdefinierten Ausnahmen, sofern erforderlich

Geben Sie zusätzliche Eigenschaften für eine Ausnahme nur dann neben der benutzerdefinierten Meldungszeichenfolge an, wenn es ein programmgesteuertes Szenario gibt, in dem ein solcher Zusatz sinnvoll ist. Beispielsweise gibt die <xref:System.IO.FileNotFoundException> die <xref:System.IO.FileNotFoundException.FileName>-Eigenschaft an.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Platzieren von throw-Anweisungen in einer Weise, dass die Stapelüberwachung nützlich ist

Die Stapelüberwachung beginnt bei der Anweisung, bei der die Ausnahme ausgelöst wurde, und endet mit der `catch`-Anweisung, mit der die Ausnahme abgefangen wird.

## <a name="use-exception-builder-methods"></a>Verwenden von Methoden zum Generieren von Ausnahmen

Häufig löst eine Klasse die jeweils gleiche Ausnahme an unterschiedlichen Stellen in der Implementierung aus. Verwenden Sie Hilfsmethoden, die eine Ausnahme erstellen und zurückgeben, um ausufernden Code zu vermeiden. Zum Beispiel:

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

In einigen Fällen ist es besser, eine Ausnahme mithilfe des zugehörigen Konstruktors zu erstellen. Ein Beispiel hierfür ist eine globale Ausnahmeklasse wie etwa <xref:System.ArgumentException>.

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a>Wiederherstellen des Status, wenn Methoden aufgrund von Ausnahmen nicht abgeschlossen werden

Aufrufende Funktionen sollten erwarten können, dass beim Auslösen einer Ausnahme durch eine Methode keine Nebeneffekte auftreten. Angenommen, Sie haben Code für Geldüberweisungen geschrieben. Ihr Code bucht einen Betrag von einem Konto ab und schreibt ihn einem anderen Konto gut. Wenn nun beim Ausführen der Gutschrift eine Ausnahme ausgelöst wird, darf die Abbuchung natürlich nicht bestehen bleiben.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

Die obige Methode löst Ausnahmen nicht direkt aus, sondern muss defensiv geschrieben werden, damit, wenn die Gutschrift fehlschlägt, die Abbuchung rückgängig gemacht wird.

In dieser Situation besteht eine Möglichkeit darin, alle Ausnahmen abzufangen, die von der Gutschrifttransaktion ausgelöst wurden, und für die Abbuchung einen Rollback auszuführen.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

Dieses Beispiel veranschaulicht die Verwendung von `throw`, um die ursprüngliche Ausnahme erneut auszulösen, damit aufrufende Funktionen die tatsächliche Ursache des Problems erkennen können, ohne die <xref:System.Exception.InnerException>-Eigenschaft untersuchen zu müssen. Eine Alternative besteht darin, eine neue Ausnahme auszulösen und die ursprüngliche Ausnahme als innere Ausnahme einzuschließen:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
