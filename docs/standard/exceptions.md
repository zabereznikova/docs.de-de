---
title: "Behandeln und Auslösen von Ausnahmen in .NET"
description: Informationen zur Verwendung von Ausnahmen in .NET
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bf116df6-0042-46bf-be13-b69864816210
translationtype: Human Translation
ms.sourcegitcommit: 9584699ad7e745ae3cb059b1bb8327301c9a3286
ms.openlocfilehash: 5271b63a47aa2fcc81cd9c8b1ffd22e618829412

---

# <a name="handling-and-throwing-exceptions-in-net"></a>Behandeln und Auslösen von Ausnahmen in .NET

Anwendungen müssen in der Lage sein, Fehler zu behandeln, die während der Ausführung konsistent auftreten.  .NET bietet ein Modell, um Anwendungen auf einheitliche Weise über Fehler zu benachrichtigen: .NET-Vorgänge geben Fehler durch Auslösen von Ausnahmen an.

## <a name="exceptions"></a>Ausnahmen

Bei einer Ausnahme handelt es sich um einen Fehlerzustand oder unerwartetes Verhalten beim Ausführen eines Programms. Ausnahmen können durch Fehler in Ihrem oder in aufgerufenem Code (z.B. bei freigegebenen Bibliotheken), nicht verfügbare Betriebssystemressourcen, unerwartete, von der Runtime festgestellte Fehlerzustände (z.B. durch nicht überprüfbaren Code) und andere Ereignisse ausgelöst werden. Anwendungen können in einigen, aber nicht allen Fällen wiederhergestellt werden. Obwohl bei den meisten Anwendungsausnahmen eine Wiederherstellung möglich ist, ist dies beim Großteil der Laufzeitausnahmen nicht der Fall.

In .NET stellt eine Ausnahme ein Objekt dar, das von der [System.Exception](xref:System.Exception)-Klasse erbt. Eine Ausnahme wird in einem Codebereich ausgelöst, in dem ein Fehler aufgetreten ist. Die Ausnahme bleibt solange im Stapel, bis sie durch die Anwendung behandelt oder das Programm beendet wird.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Ausnahmen im Vergleich zu herkömmlichen Fehlerbehandlungsmethoden

Herkömmliche Modelle der Fehlerbehandlung in Sprachen beruhten bisher entweder auf eigenen sprachenabhängigen Methoden der Fehlererkennung und -behandlung oder auf dem Fehlerbehandlungsmechanismus des Betriebssystems. Die Art und Weise, in der die Ausnahmebehandlung in .NET implementiert ist, bietet folgende Vorteile:

- Das Auslösen und Behandeln von Ausnahmen funktioniert für alle .NET-Programmiersprachen gleich.

- Eine besondere Sprachsyntax ist für die Ausnahmebehandlung nicht erforderlich, trotzdem kann jede Sprache ihre eigene Syntax definieren.

- Ausnahmen können prozess- und sogar computerübergreifend ausgelöst werden.

- Einer Anwendung kann Ausnahmebehandlungscode hinzugefügt werden, um die Programmzuverlässigkeit zu erhöhen.

Ausnahmen bieten verschiedene Vorteile gegenüber anderen Methoden zur Fehlerbenachrichtigung, z.B. Rückgabecodes. Fehler bleiben nicht unerkannt, da die Runtime Ihre Anwendung beendet, wenn eine Ausnahme ausgelöst wurde und diese nicht behandelt wird. Ungültige Werte werden nicht weiter im System weitergegeben – was passieren kann, wenn im Code nicht geprüft wird, ob ein Fehlerrückgabecode vorhanden ist. 

## <a name="exception-class-and-properties"></a>Ausnahmeklasse und -eigenschaften

Die @System.Exception-Klasse ist die Basisklasse, von der Ausnahmen erben. Die Hierarchie der @System.InvalidCastException-Klasse sieht beispielsweise wie folgt aus:

```
Object
  Exception
    SystemException
       InvalidCastException
```

Die @System.Exception-Klasse verfügt über die folgenden Eigenschaften, die das Verständnis einer Ausnahme erleichtern.

| Eigenschaftenname | Beschreibung |
| ------------- | ----------- |
| @System.Exception.Data | Ein @System.Collections.IDictionary, das beliebige Daten in Schlüssel-Wert-Paaren enthält. |
| @System.Exception.HelpLink | Kann einen URL (oder URN) zu einer Hilfedatei enthalten, die ausführliche Informationen zur Ursache einer Ausnahme bereitstellt. |
| @System.Exception.InnerException | Diese Eigenschaft kann verwendet werden, um während der Ausnahmebehandlung eine Reihe von Ausnahmen zu erstellen und beizubehalten. Sie können sie verwenden, um eine neue Ausnahme zu erstellen, die zuvor bereits abgefangene Ausnahmen enthält. Die ursprüngliche Ausnahme kann durch die zweite Ausnahme in der @System.Exception.InnerException-Eigenschaft abgefangen werden. So kann der Code, der die zweite Ausnahme verarbeitet, die zusätzlichen Informationen untersuchen. Ein Beispiel: Sie verfügen über eine Methode, die ein unzureichend formatiertes Argument erhält.  Der Code versucht, das Argument zu lesen, es wird aber eine Ausnahme ausgelöst. Die Methode fängt die Ausnahme ab und löst eine @System.FormatException. aus. Um die Fähigkeit des Aufrufers zu erhöhen, den Grund für eine Ausnahme zu ermitteln, ist es manchmal wünschenswert, dass eine Methode eine von einer Hilfsroutine ausgelöste Ausnahme abfängt und dann eine Ausnahme auslöst, die bessere Hinweise auf den aufgetretenen Fehler bietet. Es kann eine neue, aussagekräftigere Ausnahme erstellt werden, in der der Verweis auf die innere Ausnahme auf die ursprüngliche Ausnahme festgelegt werden kann. Diese aussagekräftigere Ausnahme kann für den Aufrufer ausgelöst werden. Beachten Sie, dass Sie mit dieser Funktionalität eine Reihe von verknüpften Ausnahmen erstellen können, die mit der Ausnahme endet, die zuerst ausgelöst wurde. |
| @System.Exception.Message | Bietet Informationen zur Ursache einer Ausnahme.
| @System.Exception.Source | Gibt den Namen der Anwendung oder des Objekts zurück, die bzw. das den Fehler verursacht hat, oder legt diesen fest. |
| @System.Exception.StackTrace | Enthält eine Stapelüberwachung, die verwendet kann, um zu ermitteln, wo ein Fehler aufgetreten ist. Die Stapelüberwachung beinhaltet den Quelldateinamen und die Programmzeilennummer, falls Debuginformationen verfügbar sind. |

Die meisten Klassen, die von @System.Exception erben, implementieren keine zusätzlichen Member oder zusätzlichen Funktionen. Sie erben lediglich von @System.Exception. Daher finden sich die wichtigsten Informationen für eine Ausnahme in der Hierarchie der Ausnahmeklassen, dem Namen der Ausnahme und den in der Ausnahme enthaltenen Details.

Es wird empfohlen, nur Objekte auszulösen und abzufangen, die von @System.Exception, abgeleitet sind. Sie können jedoch jedes beliebige, von der @System.Object-Klasse abgeleitete Objekt als Ausnahme auslösen. Beachten Sie, dass einige Sprachen nur das Auslösen und Abfangen von Objekten unterstützen, die von @System.Exception. abgeleitet sind.

## <a name="common-exceptions"></a>Allgemeine Ausnahmen

In der folgenden Tabelle sind einige allgemeine Ausnahmen sowie Beispiele aufgeführt, die die Ausnahmen verursachen können.

| Ausnahmetyp | Basistyp | Beschreibung | Beispiel |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | Die Basisklasse für alle Ausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| @System.IndexOutOfRangeException | @System.Exception | Wird von der Runtime nur dann ausgelöst, wenn ein Array falsch indiziert ist. | Indizieren eines Arrays außerhalb seines gültigen Bereichs: `arr[arr.Length+1]` |
| @System.NullReferenceException | @System.Exception | Wird von der Runtime nur dann ausgelöst, wenn auf ein NULL-Objekt verwiesen wird. | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | Wird von Methoden ausgelöst, wenn ein ungültiger Status vorliegt. | Aufrufen von `Enumerator.GetNext()` nach Entfernen eines Elements aus der zugrunde liegenden Auflistung. |
| @System.ArgumentException | @System.Exception | Die Basisklasse für alle Argumentausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| @System.ArgumentNullException | @System.Exception | Wird von Methoden ausgelöst, bei denen ein Argument nicht gleich NULL sein darf. | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | Wird von Methoden ausgelöst, die überprüfen, ob Argumente in einem angegebenen Bereich liegen. | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Verwenden des try/catch-Blocks zum Abfangen von Ausnahmen

Platzieren Sie die Codeabschnitte, die möglicherweise Ausnahmen auslösen, in einem `try`-Block, und platzieren Sie den Code, der die Ausnahmen behandelt, in einem `catch`-Block. Der `catch`-Block ist eine Reihe von Anweisungen, der mit dem Schlüsselwort `catch` beginnt, gefolgt von einem Ausnahmetyp und einer auszuführenden Aktion.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine mögliche Ausnahme abzufangen. Die `Main`-Methode enthält einen `try`-Block mit einer @System.IO.StreamReader-Anweisung, die eine Datei namens `data.txt` öffnet und eine Zeichenfolge aus der Datei schreibt. Dem `try`-Block folgt ein `catch`-Block, der alle Ausnahmen abfängt, die aus dem `try`-Block resultieren.

A#
```
using System;
using System.IO;

public class ProcessFile
{
    public static void Main()
    {
        try
        {
            StreamReader sr = File.OpenText("data.txt");
            Console.WriteLine("The first line of this file is {0}", sr.ReadLine());
            sr.Dispose();
        }
        catch (Exception e)
        {
            Console.WriteLine("An error occurred: '{0}'", e);
        }
    }
}
```

Die Common Language Runtime fängt Ausnahmen ab, die nicht von einem catch-Block abgefangen werden. Je nach Konfiguration der Runtime wird ein Dialogfeld zum Debuggen angezeigt, oder das Programm beendet die Ausführung und zeigt ein Dialogfeld mit Informationen zur Ausnahme an, oder es wird ein Fehler an STDERR ausgegeben.

> [!NOTE] 
> Nahezu jede Codezeile kann eine Ausnahme verursachen, insbesondere Ausnahmen, die von der Common Language Runtime selbst ausgelöst werden, z.B. eine @System.OutOfMemoryException. Die meisten Anwendungen müssen diese Ausnahmen nicht behandeln, beim Schreiben von Bibliotheken, die von anderen Anwendungen verwendet werden sollen, sollte diese Möglichkeit allerdings berücksichtigt werden. Vorschläge dazu, wann Sie Code in einen try-Block platzieren sollten, finden Sie unter [Bewährte Methoden für Ausnahmen](#best-practices-for-exceptions).
 
## <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Verwenden spezifischer Ausnahmen in einem catch-Block

Das vorherige Codebeispiel veranschaulicht eine grundlegende `catch`-Anweisung, die alle Ausnahmen abfängt. Im Allgemeinen empfiehlt es sich beim Programmieren jedoch, einen bestimmten Ausnahmetyp abzufangen, anstatt eine grundlegende `catch`-Anweisung zu verwenden.

Wenn eine Ausnahme auftritt, wird sie von unten nach oben durch den Stapel übergeben, und jeder Block erhält die Möglichkeit, sie zu behandeln. Die Reihenfolge der catch-Anweisungen ist wichtig. Platzieren Sie catch-Blöcke für bestimmte Ausnahmen vor einen allgemeinen Block zum Abfangen von Ausnahmen. Andernfalls gibt der Compiler möglicherweise einen Fehler aus. Der richtige catch-Block wird ermitteln, indem der Typ der Ausnahme mit dem Namen der im catch-Block angegebenen Ausnahme abgeglichen wird. Wenn kein bestimmter catch-Block vorhanden ist, wird die Ausnahme durch einen allgemeinen catch-Block abgefangen, sofern vorhanden.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block zum Abfangen einer @System.InvalidCastException. Das Beispiel erstellt eine Klasse namens `Employee` mit einer einzigen Eigenschaft für die Mitarbeiterstufe (`Emlevel`). Eine Methode, `PromoteEmployee`, übernimmt ein Objekt und erhöht die Mitarbeiterstufe. Eine @System.InvalidCastException tritt auf, wenn eine @System.DateTime-Instanz an die `PromoteEmployee`-Methode übergeben wird.

A#
```
using System;

public class Employee
{
    //Create employee level property.
    public int Emlevel
    {
        get
        {
            return(emlevel);
        }
        set
        {
            emlevel = value;
        }
    }

    private int emlevel = 0;
}

public class Ex13
{
    public static void PromoteEmployee(Object emp)
    {
        //Cast object to Employee.
        Employee e = (Employee) emp;
        // Increment employee level.
        e.Emlevel = e.Emlevel + 1;
    }

    public static void Main()
    {
        try
        {
            Object o = new Employee();
            DateTime newyears = new DateTime(2001, 1, 1);
            //Promote the new employee.
            PromoteEmployee(o);
            //Promote DateTime; results in InvalidCastException as newyears is not an employee instance.
            PromoteEmployee(newyears);
        }
        catch (InvalidCastException e)
        {
            Console.WriteLine("Error passing data to PromoteEmployee method. " + e.Message);
        }
    }
}
```

## <a name="how-to-use-finally-blocks"></a>Verwenden von finally-Blöcken

Wenn eine Ausnahme auftritt, wird die Ausführung beendet und die Steuerung an den entsprechenden Ausnahmehandler übergeben. Dies bedeutet häufig, dass Codezeilen umgangen werden, die eigentlich ausgeführt werden sollten. Daher muss auch nach Auslösen einer Ausnahme eine Ressourcenbereinigung durchgeführt werden, z.B. das Schließen einer Datei. Zu diesem Zweck können Sie einen `finally`-Block verwenden. Ein `finally`-Block wird immer ausgeführt, unabhängig davon, ob eine Ausnahme ausgelöst wird.

Im folgenden Codebeispiel wird mit ein `try`/`catch`-Block zum Abfangen einer @System.ArgumentOutOfRangeException. verwendet. Die `Main`-Methode erstellt zwei Arrays und versucht, das eine Array in das andere zu kopieren. Die Aktion generiert eine @System.ArgumentOutOfRangeException, und der Fehler wird an die Konsole geschrieben. Der `finally`-Block wird unabhängig vom Ergebnis des Kopiervorgangs ausgeführt.

A#
```
using System;

class ArgumentOutOfRangeExample
{
    public static void Main()
    {
        int[] array1 = {0, 0};
        int[] array2 = {0, 0};

        try
        {
            Array.Copy(array1, array2, -1);
        }
        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("Error: {0}", e);
        }
        finally
        {
            Console.WriteLine("This statement is always executed.");
        }
    }
}
```

## <a name="how-to-explicitly-throw-exceptions"></a>Explizites Auslösen von Ausnahmen

Sie können mithilfe der `throw`-Anweisung eine Ausnahme explizit auslösen. Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen. Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.

Im folgenden Codebeispiel wird ein `try`/`catch`-Block verwendet, um eine mögliche @System.IO.FileNotFoundException. abzufangen. Auf den `try`-Block folgt ein `catch`-Block, der die @System.IO.FileNotFoundException abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird. Die nächste Anweisung ist die `throw`-Anweisung, die eine neue @System.IO.FileNotFoundException auslöst und der Ausnahme Textinformationen hinzufügt.

A#
```
using System;
using System.IO;

public class ProcessFile
{
   public static void Main()
      {
      FileStream fs = null;
      try   
      {
         //Opens a text tile.
         fs = new FileStream(@"C:\temp\data.txt", FileMode.Open);
         StreamReader sr = new StreamReader(fs);
         string line;

         //A value is read from the file and output to the console.
         line = sr.ReadLine();
         Console.WriteLine(line);
      }
      catch(FileNotFoundException e)
      {
         Console.WriteLine("[Data File Missing] {0}", e);
         throw new FileNotFoundException(@"[data.txt not in c:\temp directory]",e);
      }
      finally
      {
         if (fs != null)
            fs.Dispose();
      }
   }
}
```

## <a name="how-to-create-user-defined-exceptions"></a>Erstellen benutzerdefinierter Ausnahmen

.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der @System.Exception.-Basisklasse abgeleitet werden. Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der @System.Exception-Klasse eigene Ausnahmeklassen erstellen.

Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt. Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`. Die Klasse wird von @System.Exception abgeleitet und enthält drei Konstruktoren.

A#
```
using System;

public class EmployeeListNotFoundException: Exception
{
    public EmployeeListNotFoundException()
    {
    }

    public EmployeeListNotFoundException(string message)
        : base(message)
    {
    }

    public EmployeeListNotFoundException(string message, Exception inner)
        : base(message, inner)
    {
    }
}
```

> [!NOTE]
> In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind. Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](#best-practices-for-exceptions).

## <a name="best-practices-for-exceptions"></a>Bewährte Methoden für Ausnahmen

Eine ausgereifte App behandelt Ausnahmen und Fehler, um App-Abstürze zu verhindern. In diesem Abschnitt werden bewährte Methoden für die Behandlung und Erstellung von Ausnahmen beschrieben.

### <a name="use-trycatchfinally-blocks"></a>Verwenden von try/catch/finally-Blöcken

Verwenden Sie `try`/`catch`/`finally`-Blöcke bei Code, der möglicherweise eine Ausnahme generieren kann. 

Ordnen Sie Ausnahmen in `catch`-Blöcken immer von der spezifischsten bis zur allgemeinsten an.

Verwenden Sie einen `finally`-Block, um Ressourcen zu bereinigen, unabhängig davon, ob eine Wiederherstellung möglich ist oder nicht.

### <a name="handle-common-conditions-without-throwing-exceptions"></a>Behandeln von allgemeinen Bedingungen ohne Auslösen von Ausnahmen

Bedingungen, deren Auftreten wahrscheinlich ist, die aber eine Ausnahme auslösen, sollten Sie so behandeln, dass die Ausnahme vermieden wird. Wenn Sie z.B. versuchen, eine bereits geschlossene Verbindung zu schließen, erhalten Sie eine `InvalidOperationException`. Dies können Sie verhindern, indem Sie eine `if`-Anweisung verwenden, um den Verbindungsstatus zu überprüfen, bevor Sie versuchen, die Verbindung zu schließen.

A#
```
if (conn.State != ConnectionState.Closed)
{
    conn.Close();
}
```

Wenn Sie den Verbindungsstatus vor dem Schließen der Verbindung nicht überprüfen, können Sie eine `InvalidOperationException`-Ausnahme abfangen.

A#
```
try
{
    conn.Close();
}
catch (InvalidOperationException ex)
{
    Console.WriteLine(ex.GetType().FullName);
    Console.WriteLine(ex.Message);
}
```

Die Wahl der Methode hängt von der erwarteten Häufigkeit des Ereignisses ab.

- Verwenden Sie die Ausnahmebehandlung, wenn das Ereignis nicht sehr häufig auftritt, d. h. wenn das Ereignis wirklich außergewöhnlich ist und auf einen Fehler hinweist (z. B. ein unerwartetes Dateiende). Wenn Sie die Ausnahmebehandlung verwenden, wird weniger Code in normalen Bedingungen ausgeführt.

- Wenn das Ereignis regelmäßig auftritt und als Teil der normalen Programmausführung betrachtet werden kann, suchen Sie nach Fehlerbedingungen im Code. Durch Suchen und Beheben allgemeiner Fehlerbedingungen wird weniger Code ausgeführt, da Ausnahmen vermieden werden.

### <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Entwerfen von Klassen mit dem Ziel, Ausnahmen zu vermeiden

Eine Klasse kann Methoden oder Eigenschaften bereitstellen, mit deren Hilfe ein Aufruf vermieden werden kann, der eine Ausnahme auslösen würde. Beispielsweise stellt eine @System.IO.FileStream-Klasse Methoden bereit, mithilfe derer bestimmt werden kann, ob das Ende der Datei erreicht wurde. Dadurch kann die Ausnahme vermieden werden, die durch den Versuch ausgelöst wird, nach Erreichen des Dateiendes weiterzulesen. Das folgende Beispiel zeigt, wie eine Datei bis zum Ende gelesen werden kann, ohne dass eine Ausnahme ausgelöst wird.

A#
```
class FileRead
{
    public void ReadAll(FileStream fileToRead)
    {
        // This if statement is optional
        // as it is very unlikely that
        // the stream would ever be null.
        if (fileToRead == null)
        {
            throw new System.ArgumentNullException();
        }

        int b;

        // Set the stream position to the beginning of the file.
        fileToRead.Seek(0, SeekOrigin.Begin);

        // Read each byte to the end of the file.
        for (int i = 0; i < fileToRead.Length; i++)
        {
            b = fileToRead.ReadByte();
            Console.Write(b.ToString());
            // Or do something else with the byte.
        }
    }
}
```

Eine andere Möglichkeit zum Vermeiden von Ausnahmen ist es, bei sehr häufig auftretenden Fehlern „null“ zurückzugeben, anstatt eine Ausnahme auszulösen. Ein sehr häufig auftretender Fehler kann als normale Ablaufsteuerung betrachtet werden. Indem Sie in diesen Fällen NULL zurückgeben, minimieren Sie die Auswirkungen auf die Leistung einer App.

### <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Auslösen von Ausnahmen statt Zurückgeben eines Fehlercodes

Ausnahmen stellen sicher, dass Fehler nicht unbemerkt bleiben, weil der aufrufende Code einen Rückgabecode nicht überprüft hat. 

### <a name="use-the-predefined-net-exception-types"></a>Verwenden der vordefinierten .NET-Ausnahmetypen

Führen Sie eine neue Ausnahmenklasse nur ein, wenn keine vordefinierte zutrifft. Beispiel:

- Lösen Sie eine @System.InvalidOperationException-Ausnahme aus, wenn eine festgelegte Eigenschaft oder ein Methodenaufruf aufgrund des aktuellen Status des Objekts nicht geeignet ist.

- Lösen Sie eine @System.ArgumentException oder eine der vordefinierten Klassen aus, die von @System.ArgumentException abgeleitet werden, wenn ungültige Parameter übergeben werden.

### <a name="end-exception-class-names-with-the-word-exception"></a>Enden von Ausnahmeklassen auf das Wort `Exception`

Wenn eine benutzerdefinierte Ausnahme erforderlich ist, benennen Sie diese entsprechend, und leiten Sie sie von der @System.Exception-Klasse ab. Beispiel:

A#
```
public class MyFileNotFoundException : Exception
{
}
```

### <a name="include-three-constructors-in-custom-exception-classes"></a>Einschließen von drei Konstruktoren in benutzerdefinierte Ausnahmeklassen

Verwenden Sie beim Erstellen eigener Ausnahmeklassen mindestens die drei allgemeinen Konstruktoren: den Standardkonstruktor, einen Konstruktor, der eine Zeichenfolgenmeldung akzeptiert, und einen Konstruktor, der eine Zeichenfolgenmeldung und eine innere Ausnahme akzeptiert.

- @System.Exception.%23ctor,, der Standardwerte verwendet.

- @System.Exception.%23ctor(System.String),, der eine Zeichenfolgenmeldung akzeptiert.

- @System.Exception.%23ctor(System.String,System.Exception),, der eine Zeichenfolgenmeldung und eine interne Ausnahme akzeptiert.

Ein Beispiel finden Sie unter [Erstellen benutzerdefinierter Ausnahmen](#how-to-create-user-defined-exceptions).

### <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Sicherstellen, dass Ausnahmedaten bei Remoteausführung von Code verfügbar sind

Stellen Sie beim Erstellen von benutzerdefinierten Ausnahmen sicher, dass die Metadaten für die Ausnahmen für remote ausgeführten Code verfügbar sind. 

In .NET-Runtimes, die App-Domänen implementieren, können Ausnahmen z.B. über die App-Domänen hinweg auftreten. Ein Beispiel: App-Domäne A erstellt App-Domäne B, die wiederum Code ausführt, der eine Ausnahme auslöst. Damit die App-Domäne A die Ausnahme ordnungsgemäß erfasst und behandelt, muss die Assembly gefunden werden, in der die durch die App-Domäne B ausgelöste Ausnahme enthalten ist. Wenn die App-Domäne B eine Ausnahme auslöst, die in einer Assembly in ihrer Anwendungsbasis enthalten ist, aber nicht in der Anwendungsbasis von App-Domäne A, kann die App-Domäne A die Ausnahme nicht finden. Daraufhin löst die Common Language Runtime eine @System.IO.FileNotFoundException aus. Um diese Situation zu vermeiden, haben Sie zwei Möglichkeiten, die Assembly mit den Ausnahmeinformationen bereitzustellen:

- Legen Sie die Assembly in einer gemeinsamen Anwendungsbasis ab, die sich beide App-Domänen teilen.

    \- oder –

- Wenn die Domänen keine gemeinsame Anwendungsbasis verwenden, signieren Sie die Assembly, in der die Ausnahmeinformationen enthalten sind, mit einem starken Namen und legen sie in einem globalen Assemblycache ab.

### <a name="include-a-localized-description-string-in-every-exception"></a>Einschließen einer lokalisierten Beschreibungszeichenfolge in jeder Ausnahme

Die für Benutzer sichtbare Fehlermeldung wird von der Beschreibungszeichenfolge der ausgelösten Ausnahme abgeleitet, nicht vom Namen der Ausnahmeklasse.

### <a name="use-grammatically-correct-error-messages"></a>Verwenden von grammatisch korrekten Fehlermeldungen

Verfassen Sie klar verständliche Meldungen, und setzen Sie Satzendpunkte. Jeder Satz in einer Beschreibungszeichenfolge sollte mit einem Punkt beendet werden. „In der Protokolltabelle ist ein Überlauf aufgetreten.“ Dies ist ein Beispiel für eine angemessene Beschreibungszeichenfolge.

### <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Bereitstellen zusätzlicher Eigenschaften in benutzerdefinierten Ausnahmen, sofern erforderlich

Geben Sie zusätzliche Eigenschaften für eine Ausnahme nur dann zusätzlich zur Beschreibungszeichenfolge an, wenn es ein programmgesteuertes Szenario gibt, in dem dieser Zusatz sinnvoll ist. Beispielsweise gibt die @System.IO.FileNotFoundException die @System.IO.FileNotFoundException.FileName-Eigenschaft an.

### <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Platzieren von throw-Anweisungen so, dass die Stapelüberwachung nützlich ist

Die Stapelüberwachung beginnt mit der Anweisung, bei der die Ausnahme ausgelöst wurde, und endet mit der `catch`-Anweisung, mit der die Ausnahme abgefangen wird.

### <a name="use-exception-builder-methods"></a>Verwenden von Methoden zum Generieren von Ausnahmen

Es ist üblich, dass eine Klasse von unterschiedlichen Punkten in der Implementierung aus die gleiche Ausnahme auslöst. Verwenden Sie Hilfsmethoden, die eine Ausnahme erstellen und zurückgeben, um ausufernden Code zu vermeiden. Zum Beispiel:

A#
```
class FileReader
{
    private string fileName;

    public FileReader(string path)
    {
        fileName = path;
    }

    public byte[] Read(int bytes)
    {
        byte[] results = FileUtils.ReadFromFile(fileName, bytes);
        if (results == null)
        {
            throw NewFileIOException();
        }
        return results;
    }

    FileReaderException NewFileIOException()
    {
        string description = "My NewFileIOException Description";

        return new FileReaderException(description);
    }
}

```

In einigen Fällen ist es besser, den Konstruktor einer Ausnahme zu verwenden, um die Ausnahme zu generieren. Ein Beispiel hierfür ist eine globale Ausnahmeklasse wie etwa @System.ArgumentException,. 

### <a name="clean-up-intermediate-results-when-throwing-an-exception"></a>Löschen von Zwischenergebnissen beim Auslösen von Ausnahmen

Aufrufer sollten davon ausgehen können, dass keine Nebeneffekte auftreten, wenn eine Ausnahme von einer Methode ausgelöst wird. Ein Beispiel: Sie haben Code für Geldüberweisungen geschrieben. Ihr Code bucht Geld von einem Konto ab und zahlt es auf ein anderes Konto ein. Wenn nun beim Ausführen der Einzahlung eine Ausnahme ausgelöst wird, sollte die Abbuchung natürlich nicht in Kraft bleiben.

A#
```
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

In dieser Situation besteht eine Möglichkeit darin, alle Ausnahmen abzufangen, die von der Einzahlungstransaktion ausgelöst wurden, und für die Abbuchung ein Rollback auszuführen.

A#
```
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
        throw
    }
}
```

Dieses Beispiel veranschaulicht die Verwendung von `throw`, um die ursprüngliche Ausnahme erneut auszulösen, damit Aufrufer die tatsächliche Ursache des Problems erkennen können, ohne die @System.Exception.InnerException-Eigenschaft untersuchen zu müssen. Eine Alternative ist es, eine neue Ausnahme auszulösen und die ursprüngliche Ausnahme als innere Ausnahme einzuschließen:

A#
```
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a>Siehe auch

Weitere Informationen zur Funktionsweise von Ausnahmen in .NET finden Sie in [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Was jeder Entwickler über Ausnahmen in der Runtime wissen muss).



<!--HONumber=Nov16_HO3-->


