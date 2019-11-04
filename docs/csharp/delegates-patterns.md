---
title: Gängige Muster für Delegate
description: Erfahren Sie etwas über allgemeine Muster für die Verwendung von Delegaten in Ihrem Code, um starke Kopplung zwischen Komponenten zu vermeiden.
ms.date: 06/20/2016
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 174ae4129464c9d2e787048793cec764121ca4aa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454081"
---
# <a name="common-patterns-for-delegates"></a>Gängige Muster für Delegate

[Vorherige](delegates-strongly-typed.md)

Delegaten bieten einen Mechanismus, der Software-Entwürfe ermöglicht, die minimale Kopplung zwischen Komponenten umfassen.

Ein hervorragendes Beispiel für diese Art von Design ist LINQ. Das LINQ-Abfrageausdrucksmuster stützt sich auf Delegaten für alle Funktionen. Betrachten Sie folgendes einfaches Beispiel:

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

Die Sequenz von Zahlen wird auf nur die, die kleiner als der Wert 10 sind, gefiltert.
Die `Where`-Methode verwendet einen Delegaten, der bestimmt, welche Elemente einer Sequenz den Filter passieren. Wenn Sie eine LINQ-Abfrage erstellen, geben Sie die Implementierung des Delegaten für diesen bestimmten Zweck an.

Der Prototyp für die Where-Methode ist:

```csharp
public static IEnumerable<TSource> Where<TSource> (this IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

Dieses Beispiel wird mit allen Methoden wiederholt, die Teil von LINQ sind. Alle basieren auf Delegaten für den Code, der die jeweilige Abfrage verwaltet. Dieses API-Entwurfsmuster ist ein sehr leistungsfähiges Muster zum Erlernen und Verstehen.

In diesem einfachen Beispiel wird veranschaulicht, wie Delegaten nur wenig Kopplung zwischen Komponenten erfordern. Sie müssen keine Klasse erstellen, die von einer bestimmten Basisklasse abgeleitet ist. Sie müssen keine bestimmte Schnittstelle implementieren.
Die einzige Voraussetzung ist die Bereitstellung der Implementierung einer Methode, die für den jeweiligen Task unerlässlich ist.

## <a name="building-your-own-components-with-delegates"></a>Erstellen eigener Komponenten mit Delegaten

Erstellen Sie für dieses Beispiel mithilfe eines Entwurfs, das auf Delegaten basiert, eine Komponente.

Definieren wir eine Komponente, die in einem umfangreichen System für Protokollmeldungen verwendet werden kann. Bibliothekskomponenten können in vielen verschiedenen Umgebungen auf mehreren verschiedenen Plattformen verwendet werden. Es gibt zahlreiche allgemeine Funktionen in der Komponente, die die Protokolle verwalten. Es muss Meldungen von jeder Komponente im System annehmen. Diese Meldungen werden über unterschiedliche Prioritäten verfügen, die die Kernkomponente verwalten kann. Die Meldungen sollten einen Zeitstempel in ihrer endgültigen archivierten Form aufweisen. Für komplexere Szenarios können Sie Meldungen von der Quellkomponente filtern.

Es gibt ein Aspekt der Funktion, der sich häufig ändern wird: An welchem Standort Meldungen geschrieben werden. In einigen Umgebungen können sie in der Fehlerkonsole geschrieben werden. In anderen Fällen in einer Datei. Andere können beispielsweise Datenbankspeicher, Betriebssystem-Ereignisprotokolle oder andere Dokumentspeicher sein.

Es gibt auch Ausgabekombinationen, die in verschiedenen Szenarios verwendet werden könnten. Möglicherweise möchten Sie Meldungen an die Konsole und in eine Datei schreiben.

Ein Entwurf, basierend auf den Delegaten bietet ein hohes Maß an Flexibilität, und erleichtert Ihnen die Unterstützung von Speichermechanismen, die in der Zukunft möglicherweise hinzugefügt werden.

Durch dieses Design kann die primäre Protokollkomponente eine nicht virtuelle, sogar eine versiegelte Klasse sein. Sie können eine beliebige Anzahl von Delegaten angeben, um die Meldungen in unterschiedliche Speichermedien zu schreiben. Die integrierte Unterstützung für Multicastdelegaten erleichtert die Unterstützung von Szenarios, in denen Meldungen an mehreren Standorten (eine Datei und eine Konsole) geschrieben werden müssen.

## <a name="a-first-implementation"></a>Erste Implementierung

Fangen wir klein an: Die anfängliche Implementierung akzeptiert neue Meldungen, und schreibt mithilfe von angefügten Delegaten. Sie können mit einem Delegaten beginnen, der Meldungen in die Konsole schreibt.

[!code-csharp[LoggerImplementation](../../samples/csharp/delegates-and-events/Logger.cs#FirstImplementation "A first Logger implementation.")]

Die statische Klasse oben ist die einfachste Sache, die funktionieren kann. Wir müssen die einzelne Implementierung für die Methode schreiben, die Meldungen in die Konsole schreibt: 

[!code-csharp[LogToConsole](../../samples/csharp/delegates-and-events/LoggingMethods.cs#LogToConsole "A Console logger.")]

Abschließend müssen Sie den Delegaten verknüpfen, indem Sie ihn an den WriteMessage-Delegaten anfügen, der in der Protokollierung deklariert wurde:

[!code-csharp[ConnectDelegate](../../samples/csharp/delegates-and-events/Program.cs#ConnectDelegate "Connect to the delegate")]

## <a name="practices"></a>Methoden

Unser Beispiel ist bisher recht einfach, aber es veranschaulicht immer noch einige der wichtigen Richtlinien für Entwürfe, die Delegaten umfassen.

Delegattypen zu verwenden, die in der Kern-Framework definiert sind, erleichtert Benutzern die Arbeit mit den Delegaten. Sie müssen keine neue Typen definieren, und Entwickler, die die Bibliothek nutzen, müssen keine neuen, spezialisierten Delegattypen erlernen.

Die verwendeten Schnittstellen sind so minimal und so flexibel wie möglich: Um eine neue Ausgabeprotokollierung zu erstellen, müssen Sie eine Methode erstellen. Diese Methode kann eine statische Methode oder eine Instanzmethode sein. Es kann über jeden Zugriff verfügen.

## <a name="formatting-output"></a>Formatieren der Ausgabe

Lassen Sie uns die erste Version etwas stabiler machen und anschließend andere Protokollierungsmechanismen erstellen.

Als Nächstes fügen wir einige Argumente in die `LogMessage()`-Methode ein, damit Ihre Protokollklasse mehr strukturierte Meldungen erstellt:

[!code-csharp[Severity](../../samples/csharp/delegates-and-events/Logger.cs#Severity "Define severities")]
[!code-csharp[NextLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerTwo "Refine the Logger")]

Als Nächstes verwenden wir dieses `Severity`-Argument, um die Meldungen zu filtern, die in das Ausgabeprotokoll gesendet werden. 

[!code-csharp[FinalLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerFinal "Finish the Logger")]

## <a name="practices"></a>Methoden

Sie haben der Protokollierungsinfrastruktur neue Funktionen hinzugefügt. Da die Protokollierungskomponente sehr lose an Ausgabemechanismen gekoppelt ist, können diese neuen Funktionen ohne Auswirkung auf den Code, der die Protokollierungsdelegaten implementiert, hinzugefügt werden.

Solange Sie dies erstellen, sehen Sie weitere Beispiele, wie diese lose Verbindung mehr Flexibilität bei der Aktualisierung von Teilen der Site ohne Änderungen an anderen Speicherorten ermöglicht. In der Tat könnten die Klassen der Protokollierungsausgabe in einer umfangreicheren Anwendung in einer anderen Assembly sein. Sie müssen auch nicht neu erstellt werden.

## <a name="building-a-second-output-engine"></a>Erstellen einer zweiten Ausgabe-Engine

Die Protokollierungskomponente kommt gut voran. Fügen wir eine weitere Ausgabe-Engine hinzu, die Meldungen in einer Datei protokolliert. Dies wird eine etwas komplexere Ausgabe-Engine werden. Es wird eine Klasse sein, die die Dateivorgänge kapselt, und sicherstellt, dass die Datei nach jedem Schreibvorgang immer geschlossen wird. Dadurch wird sichergestellt, dass alle Daten auf den Datenträger geschrieben werden, nachdem jede Meldung generiert wurde.

Hier ist diese dateibasierte-Protokollierung:

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/FileLogger.cs#FileLogger "Log to files")]

Wenn Sie diese Klasse erstellt haben, können Sie sie instanziieren und sie fügt ihre LogMessage-Methode in die Protokollierungskomponente an:

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/Program.cs#FileLogger "Log to files")]

Diese beiden schließen einander nicht aus. Sie können beide Protokollmethoden anfügen, und Meldungen in die Konsole und eine Datei generieren:

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LoggingMethods.LogToConsole; // LoggingMethods is the static class we utilized earlier
```

Später können Sie auch in derselben Anwendung einen Delegaten ohne andere Probleme auf dem System entfernen:

```csharp
Logger.WriteMessage -= LoggingMethods.LogToConsole;
```

## <a name="practices"></a>Methoden

Sie haben nun einen zweiten Ausgabehandler für das Protokollierungs-Subsystem hinzugefügt.
Dieses Objekt benötigt ein wenig mehr Infrastruktur, um das Dateisystem ordnungsgemäß zu unterstützen. Bei dem Delegat handelt es sich um eine Instanzmethode. Es ist auch eine private Methode.
Es besteht keine Notwendigkeit für höhere Verfügbarkeit, da die Delegat-Infrastruktur die Delegaten verbinden kann.

Zweitens ermöglicht der delegatbasierte Entwurf mehrere Ausgabemethoden ohne zusätzlichen Code. Sie müssen keine zusätzliche Infrastruktur zur Unterstützung von mehreren Ausgabemethoden erstellen. Sie erhalten einfach eine andere Methode auf der Aufrufliste.

Achten Sie besonders auf den Code in der Ausgabemethode, die die Datei protokolliert. Es wird codiert, um sicherzustellen, dass keine Ausnahmen ausgelöst werden. Obwohl dies nicht immer unbedingt erforderlich ist, ist es häufig sinnvoll. Wenn eine der Delegatmethoden eine Ausnahme auslöst, werden die im Aufruf verbleibenden Delegaten nicht aufgerufen werden.

Ein letzter Hinweis: Die Dateiprotokollierung muss ihre Ressourcen durch Öffnen und Schließen der Datei in jeder Protokollmeldung verwalten. Sie können die Datei offen lassen und IDisposable implementieren, um die Datei zu schließen, wenn Sie fertig sind.
Beide Methoden haben Vor- und Nachteile. Beide erstellen etwas mehr Kopplung zwischen den Klassen.

Kein Teil des Codes in der Protokollierungsklasse müsste aktualisiert werden, um beide Szenarios zu unterstützen.

## <a name="handling-null-delegates"></a>Behandlung von NULL-Delegaten

Zum Schluss aktualisieren wir die LogMessage-Methode, damit es für jene Fälle stabil ist, wenn kein Ausgabemechanismus ausgewählt wurde. Die aktuelle Implementierung löst eine `NullReferenceException` aus, wenn der `WriteMessage`-Delegat nicht über eine angefügte Aufrufliste verfügt.
Möglicherweise bevorzugen Sie einen Entwurf, der im Hintergrund fortgesetzt wird, wenn keine Methoden angefügt wurden. Dies lässt sich mithilfe des bedingten NULL-Operators, kombiniert mit der `Delegate.Invoke()`-Methode, leicht umsetzen:

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

Der bedingte NULL-Operator (`?.`) wird verkürzt, wenn der linke Operand (`WriteMessage` in diesem Fall) NULL ist, was bedeutet, dass nicht versucht wurde, eine Meldung zu protokollieren.

Sie werden die `Invoke()`-Methode nicht in der Dokumentation für `System.Delegate` oder `System.MulticastDelegate` aufgelistet finden. Der Compiler generiert eine typsicherer `Invoke`-Methode für jeden deklarierten Delegattyp. In diesem Beispiel bedeutet das, dass `Invoke` ein einzelnes `string`-Argument nimmt und über einen void-Rückgabetyp verfügt.

## <a name="summary-of-practices"></a>Zusammenfassung der Methoden

Sie haben die Anfänge einer Protokollkomponente gesehen, die mit anderen Writern und anderen Funktionen erweitert werden konnte. Mithilfe von Delegaten im Entwurf sind diese verschiedenen Komponenten sehr lose gekoppelt. Dies bietet mehrere Vorteile. Es ist sehr einfach neue Ausgabemechanismen zu erstellen und diese an das System anzufügen. Diese Mechanismen benötigen nur eine Methode: Die Methode, die die Protokollmeldungen schreibt. Es ist ein Entwurf, der sehr stabil ist, wenn neue Funktionen hinzugefügt werden. Der für alle Writer erforderliche Vertrag dient dazu, eine Methode zu implementieren. Diese Methode kann eine statische oder Instanzmethode sein. Es kann sich um einen öffentlichen, privaten oder jeden anderen rechtlichen Zugriff handeln.

Die Protokollierungsklasse kann eine beliebige Anzahl von Verbesserungen oder Änderungen vornehmen, ohne wichtige Änderungen einzuführen. Wie jede Klasse können Sie die öffentliche API nicht ohne das Risiko von wichtigen Änderungen ändern. Aber da die Kopplung zwischen der Protokollierung und den Ausgabe-Engines nur über den Delegaten stattfindet, sind keine anderen Typen (z.B. Schnittstellen oder Basisklassen) beteiligt. Die Kopplung ist so klein wie möglich.

[Nächste](events-overview.md)
