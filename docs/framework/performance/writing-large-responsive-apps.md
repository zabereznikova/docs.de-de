---
title: Schreiben großer, reaktionsfähiger .NET Framework-Apps
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 57f65feff5260cb83df5354f5d7ee1bad0babb3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180580"
---
# <a name="writing-large-responsive-net-framework-apps"></a>Schreiben großer, reaktionsfähiger .NET Framework-Apps

In diesem Artikel werden Tipps zum Verbessern der Leistung von großen .NET Framework-Apps oder Apps bereitgestellt, die großen Datenmengen wie Dateien oder Datenbanken verarbeiten. Die Tipps stammen aus dem Umschreiben der C#- und Visual Basic-Compiler in verwalteten Code, und dieser Artikel enthält mehrere reale Beispiele aus dem C#-Compiler.
  
.NET Framework ist sehr produktiv für das Erstellen von Apps. Leistungsstarke und sichere Sprachen und eine umfassende Sammlung von Bibliotheken sorgen für eine sehr erfolgreiche Erstellung von Apps. Aber mit großer Produktivität geht auch Verantwortung einher. Sie sollten die gesamte Leistung von .NET Framework nutzen, aber darauf vorbereitet sein, die Leistung Ihres Codes bei Bedarf abzustimmen.
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a>Warum die neue Compilerleistung für Ihre App angewendet werden kann  
 Das .NET Compiler Platform-Team („Roslyn“) hat die C#- und Visual Basic-Compiler in verwalteten Code umgeschrieben, um neue APIs für das Modellieren und Analysieren von Code, das Erstellen von Tools und das Unterstützen einer wesentlich umfassenderen codeabhängigen Erfahrung in Visual Studio bereitzustellen. Das Umschreiben der Compiler und das Erstellen von Visual Studio-Erfahrungen in den neuen Compilern hat nützliche Leistungseinblicke ergeben, die für jede große .NET Framework-App oder jede App anwendbar sind, die viele Daten verarbeitet. Sie müssen sich nicht mit Compilern auskennen, um die Einblicke und Beispiele aus dem C#-Compiler nutzen zu können.
  
 Visual Studio verwendet die Compiler-APIs, um all die IntelliSense-Funktionen zu erstellen, die bei Benutzern beliebt sind, zum Beispiel die farbliche Kennzeichnung von Bezeichnern und Schlüsselwörtern, Syntaxvervollständigungslisten, Wellenlinien für Fehler, Parametertipps, Codeprobleme und Codeaktionen. Visual Studio stellt diese Hilfe bereit, während Entwickler ihren Code eingeben und ändern, und Visual Studio muss reaktionsfähig bleiben, während der Compiler den von Entwicklern bearbeiteten Code kontinuierlich modelliert.
  
 Wenn Ihre Endbenutzer mit der App interagieren, erwarten sie, dass die App reaktionsfähig ist. Eingaben oder Befehlsverarbeitung sollten nie blockiert sein. Die Hilfe sollte schnell angezeigt oder geschlossen werden, wenn der Benutzer die Eingabe fortsetzt. Ihre App sollte vermeiden, den UI-Thread mit langen Berechnungen zu blockieren, die Ihre App langsam machen.
  
 Weitere Informationen zu Roslyn-Compilern finden Sie im [.NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).
  
## <a name="just-the-facts"></a>Reine Tatsachen  
 Berücksichtigen Sie die folgenden Tatsachen, wenn Sie die Leistung optimieren und reaktionsfähige .NET Framework-Apps erstellen.
  
### <a name="fact-1-dont-prematurely-optimize"></a>Tatsache 1: Vermeiden Sie eine vorzeitige Optimierung.  
 Das Schreiben von Code, der komplexer als notwendig ist, zieht Kosten für Wartung, Debugging und Verfeinerung nach sich. Erfahrene Programmierer verstehen intuitiv, wie sie Codierungsprobleme lösen und einen effizienteren Code schreiben. Dennoch optimieren Sie ihren Code manchmal vorzeitig. Sie verwenden beispielsweise eine Hashtabelle, wenn ein einfaches Array ausreichen würde, oder sie verwenden ein kompliziertes Zwischenspeichern, das möglicherweise Speicherverluste verursacht statt einfach Werte neu zu berechnen. Selbst wenn Sie ein erfahrener Programmierer sind, sollten Sie Ihren Code auf Leistung testen und analysieren, wenn Sie Probleme finden.
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a>Tatsache 2: Wenn Sie nicht messen, raten Sie.  
 Profile und Messungen lügen nicht. Profile zeigen Ihnen, ob die CPU vollständig geladen ist oder Sie von Datenträger-E/A blockiert werden. Profile teilen Ihnen mit, welche Art und wie viel Speicher Sie zuweisen und ob Ihre CPU viel Zeit in der [Garbage Collection](../../standard/garbage-collection/index.md) (GC) verbringt.
  
 Sie sollten Leistungsziele für wichtige Kundenerfahrungen oder -szenarien in Ihrer App festlegen und Tests schreiben, um die Leistung zu messen. Untersuchen Sie fehlschlagende Tests, indem Sie die wissenschaftliche Methode anwenden: Verwenden Sie Profile, um Ihnen die Richtung zu weisen, stellen Sie Hypothesen auf, worin das Problem bestehen könnte, und testen Sie Ihre Hypothese mit einem Experiment oder einer Codeänderung. Richten Sie Baselineleistungsmessungen über die Zeit mit regelmäßigen Tests ein, damit Sie Änderungen isolieren können, die Leistungsregressionen verursachen. Wenn Sie die Leistungsarbeit auf eine rigorose Weise angehen, verschwenden Sie keine Zeit mit Codeaktualisierungen, die Sie nicht benötigen.
  
### <a name="fact-3-good-tools-make-all-the-difference"></a>Tatsache 3: Gute Tools machen einen großen Unterschied.  
 Mit guten Tools können Sie schnell einen Drilldown in die größten Leistungsprobleme (CPU, Speicher oder Datenträger) ausführen und den Code finden, der diese Engpässe verursacht. Microsoft liefert eine Vielzahl von Leistungstools wie [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) und [PerfView](https://www.microsoft.com/download/details.aspx?id=28567)aus.
  
 PerfView ist ein kostenloses und erstaunlich leistungsstarkes Tool, mit dem Sie sich auf tiefliegende Probleme wie Datenträger-E/A, GC-Ereignisse und Arbeitsspeicher konzentrieren können. Sie erfassen leistungsrelevante Ereignisse der [Ereignisablaufverfolgung für Windows](../wcf/samples/etw-tracing.md) (Event Tracing for Windows, ETW) und zeigen auf einfache Weise Informationen pro App, pro Prozess, pro Stapel und pro Thread an. PerfView zeigt Ihnen, wie viel und welche Art von Speicher Ihre App zuweist und welche Funktionen oder Aufrufstapel zu welchem Anteil der Speicherbelegungen beitragen. Einzelheiten finden Sie in den umfassenden Hilfethemen, Demos und Videos, die mit dem Tool ausgeliefert werden (zum Beispiel die [PerfView-Tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) auf Channel 9).
  
### <a name="fact-4-its-all-about-allocations"></a>Tatsache 4: Es dreht sich alles um Zuordnungen.  
 Möglicherweise denken Sie, dass es beim Erstellen einer reaktionsfähigen .NET Framework-App vor allem um Algorithmen wie die Verwendung von QuickSort anstelle von BubbleSort geht, aber das ist nicht der Fall. Der größte Faktor bei der Erstellung einer reaktionsfähigen App ist die Speicherbelegung, insbesondere wenn Ihre App sehr groß ist oder große Datenmengen verarbeitet.
  
 Nahezu die gesamte Arbeit beim Erstellen reaktionsfähiger IDE-Erfahrungen mit den neuen Compiler-APIs beinhaltete das Vermeiden von Speicherbelegungen und das Verwalten von Zwischenspeicherstrategien. PerfView-Ablaufverfolgungen zeigen, dass die Leistung der neuen C#- und Visual Basic-Compiler selten CPU-gebunden ist. Die Compiler können E/A-gebunden sein, wenn Sie Hundertausende oder Millionen von Codezielen oder Metadaten lesen oder generierten Code ausgeben. Die UI-Threadverzögerungen erfolgen nahezu alle wegen der Garbage Collection. Die .NET Framework GC ist weitgehend für Leistung optimiert und führt einen großen Teil ihrer Arbeit parallel zur Ausführung von App-Code durch. Dennoch kann eine einzige Speicherbelegung eine teure [gen2](../../standard/garbage-collection/fundamentals.md)-Collection auslösen, die alle Threads anhält.
  
## <a name="common-allocations-and-examples"></a>Typische Speicherbelegungen und Beispiele  
 Die Beispielausdrücke in diesem Abschnitt haben verborgene Speicherbelegungen, die klein erscheinen. Aber wenn eine große App die Ausdrücke oft genug ausführt, können Sie Speicherbelegungen mit Hunderten von Megabyte oder sogar Gigabyte verursachen. Beispielsweise wurden bei einminütigen Tests, in denen eine Eingabe des Entwicklers im Editor simuliert wurden, mehrere Gigabyte Speicher belegt und dazu geführt, dass sich das Leistungsteam auf Eingabeszenarien konzentrierte.
  
### <a name="boxing"></a>Boxing  
 [Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) findet statt, wenn Werttypen, die normalerweise im Stapel oder in Datenstrukturen vorkommen, in ein Objekt eingeschlossen werden. Das heißt, Sie ordnen ein Objekt zu, das die Daten hält, und geben dann einen Zeiger zum Objekt zurück. .NET Framework führt das Boxing von Werten manchmal aufgrund der Signatur einer Methode oder des Typs eines Speicherstandorts durch. Das Einschließen eines Werttyps in ein Objekt führt zu einer Speicherbelegung. Viele Boxingvorgänge können zu Speicherbelegungen mit mehrere Megabyte oder Gigabyte für Ihre App beitragen, was bedeutet, dass Ihre App mehr GCs verursacht. .NET Framework und die Sprachcompiler vermeiden das Boxing, wenn möglich, aber manchmal kommt es dazu, wenn Sie es am wenigsten erwarten.
  
 Um Boxing in PerfView zu sehen, öffnen Sie eine Ablaufverfolgung, und sehen Sie sich GC-Heapbelegungsstapel unter dem Prozessnamen Ihrer App an (denken Sie daran, dass PerfView Berichte zu allen Prozessen erstellt). Wenn Sie Typen wie <xref:System.Int32?displayProperty=nameWithType> und <xref:System.Char?displayProperty=nameWithType> unter Belegungen sehen, wird ein Boxing von Werttypen durchgeführt. Wenn Sie einen dieser Typen auswählen, werden die Stapel und Funktionen angezeigt, in denen sie verschachtelt sind.
  
 **Beispiel 1: Zeichenfolgenmethoden und Werttypargumente**  
  
 In diesem Beispielcode wird ein potenziell unnötiges und übermäßiges Boxing dargestellt:  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 Dieser Code stellt Protokollierungsfunktionen bereit, was bedeutet, dass eine App die `Log`-Funktion häufig, möglicherweise mehrere Millionen mal aufruft. Das Problem ist, dass der Aufruf an `string.Format` in die <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>-Überladung aufgelöst wird.
  
 Für diese Überladung muss .NET die `int`-Werte in Objekten verschachteln, um sie an diesen Methodenaufruf zu übergeben. Eine Teilkorrektur besteht darin, `id.ToString()` und `size.ToString()` aufzurufen und alle Zeichenfolgen (die Objekte sind) an den `string.Format`-Aufruf zu übergeben. Das Aufrufen von `ToString()` ordnet eine Zeichenfolge zu, aber diese Zuordnung findet in `string.Format` sowieso statt.
  
 Sie können überlegen, dass dieser grundlegende Aufruf an `string.Format` nur eine Zeichenfolgenverkettung ist, deshalb können Sie stattdessen den folgenden Code schreiben:  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 Diese Codezeile führt jedoch eine Boxingbelegung ein, da sie zu <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29> kompiliert wird. .NET Framework muss das Zeichenliteral verschachteln, um `Concat` aufzurufen.  
  
 **Korrektur für Beispiel 1**  
  
 Die vollständige Korrektur ist einfach. Ersetzen Sie einfach das Zeichenliteral mit einem Zeichenfolgenliteral, das kein Boxing hervorruft, da Zeichenfolgen bereits Objekte sind:  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 **Beispiel 2: Enum-Boxing**  
  
 Dieses Beispiel war aufgrund der häufigen Verwendung von Enumerationstypen, insbesondere bei Wörterbuchsuchvorgängen, für eine enorme Menge an Belegung in den neuen C#- und Visual Basic-Compilern verantwortlich.
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 Das Problem ist sehr subtil. PerfView würde dies als <xref:System.Enum.GetHashCode>-Boxing melden, weil die Methode die zugrunde liegende Darstellung des Enumerationstyps aus Implementierungsgründen verschachtelt. Wenn Sie in PerfView genau hinsehen, sehen Sie möglicherweise zwei Boxingzuordnungen für jeden Aufruf an <xref:System.Enum.GetHashCode>. Der Compiler fügt eine ein, .NET Framework die andere.
  
 **Korrektur für Beispiel 2**  
  
 Sie können beide Zuordnungen leicht vermeiden, indem Sie eine Umwandlung zur zugrunde liegenden Darstellung vornehmen, bevor Sie <xref:System.Enum.GetHashCode> aufrufen:  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 Eine andere übliche Quelle für das Boxing bei Enumerationstypen ist die <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>-Methode. Das an <xref:System.Enum.HasFlag%28System.Enum%29> übergebene Argument muss geschachtelt werden. In den meisten Fällen ist es einfacher und zuordnungsfrei, Aufrufe an <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> durch einen bitweisen Test zu ersetzen.
  
 Behalten Sie die erste Leistungstatsache im Hinterkopf (keine vorzeitige Optimierung), und fangen Sie nicht an, Ihren gesamten Code auf diese Weise umzuschreiben. Ihnen sollten diese Boxingkosten bewusst sein, aber Sie sollten Ihren Code nur ändern, nachdem Sie ein Profil für Ihre App erstellt und die Hotspots gefunden haben.
  
### <a name="strings"></a>Zeichenfolgen  
 Zeichenfolgenmanipulationen zählen zu den größten Verursachern von Zuordnungen und zeigen sich in PerfView oft in den ersten fünf Zuordnungen. Programme verwenden Zeichenfolgen für die Serialisierung, JSON und REST-APIs. Sie können Zeichenfolgen als programmgesteuerte Konstanten für die Interoperation mit Systemen verwenden, wenn Sie keine Enumerationstypen benutzen können. Wenn Ihre Profilerstellung zeigt, dass sich Zeichenfolgen stark auf die Leistungs auswirken, suchen Sie nach Aufrufen an <xref:System.String>-Methoden wie <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A> und so weiter. Die Verwendung von <xref:System.Text.StringBuilder> zum Vermeiden der Kosten der Erstellung einer Zeichenfolge aus vielen Teilen hilft, aber selbst das Zuordnen des <xref:System.Text.StringBuilder>-Objekts kann zu einem Engpass werden, den Sie verwalten müssen.
  
 **Beispiel 3: Zeichenfolgenvorgänge**  
  
 Der C#-Compiler hatte den folgenden Code, der den Text eines formatierten XML-Dokumentationskommentars schreibt:  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 Sie können sehen, dass dieser Code eine Menge Zeichenfolgenmanipulation durchführt. Der Code verwendet Bibliotheksmethoden, um Zeilen in separate Zeichenfolgen zu trennen, Leerzeichen zu entfernen, zu überprüfen, ob das Argument `text` ein XML-Dokumentationskommentar ist, und untergeordnete Zeichenfolgen zu extrahieren.
  
 In der erste Zeile in `WriteFormattedDocComment` ordnet der Aufruf `text.Split` bei jedem Aufruf ein neues Array mit drei Elementen als Argument zu. Der Compiler muss Code ausgeben, um dieses Array jedes Mal zuzuordnen. Der Grund hierfür ist, dass der Compiler nicht weiß, ob <xref:System.String.Split%2A> das Array irgendwo speichert, wo es möglicherweise von anderem Code modifiziert wird, was sich auf spätere Aufrufe an `WriteFormattedDocComment` auswirken würde. Der Anruf an <xref:System.String.Split%2A> ordnet außerdem eine Zeichenfolge für jede Zeile in `text` zu und belegt anderen Speicher, um den Vorgang durchzuführen.
  
 `WriteFormattedDocComment` hat drei Aufrufe an die <xref:System.String.TrimStart%2A>-Methode. Zwei befinden sich in inneren Schleifen, die Arbeit und Zuordnungen duplizieren. Erschwerend kommt noch hinzu, dass beim Aufrufen der <xref:System.String.TrimStart%2A>-Methode ohne Argumente zusätzlich zum Zeichenfolgenergebnis ein leeres Array (für den Parameter `params`) zugeordnet wird.
  
 Und schließlich gibt es einen Aufruf an die <xref:System.String.Substring%2A>-Methode, der für gewöhnlich eine neue Zeichenfolge zuordnet.
  
 **Korrektur für Beispiel 3**  
  
 Im Gegensatz zu den vorherigen Beispiele können diese Zuordnungen nicht durch kleine Korrekturen behoben werden. Sie müssen zurückgehen, sich das Problem ansehen und es anders angehen. Sie werden beispielsweise bemerken, dass das Argument für `WriteFormattedDocComment()` eine Zeichenfolge ist, die alle Informationen enthält, die die Methode benötigt, sodass der Code mehr Indizierung anstelle der Zuordnung vieler Teilzeichenfolgen durchführen könnte.
  
 Das Leistungsteam für den Compiler hat all diese Zuordnungen mit einem Code wie dem folgenden gelöst:  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...
```  
  
 Die erste Version von `WriteFormattedDocComment()` hat ein Array, mehrere untergeordnete Zeichenfolgen und eine abgeschnittene Zeichenfolge zusammen mit einem leeren `params`-Array zugeordnet. Es wurde auch auf "///" überprüft. Der überarbeitete Code verwendet nur die Indizierung und ordnet nichts zu. Es findet das erste Zeichen, das kein Leerzeichen ist, und überprüft dann Zeichen für Zeichen, um zu sehen, ob die Zeichenfolge mit "///" beginnt. Der neue `IndexOfFirstNonWhiteSpaceChar` Code <xref:System.String.TrimStart%2A> verwendet anstelle des ersten Indexes (nach einem angegebenen Startindex), in dem ein Nicht-Leerzeichen auftritt. Die Korrektur ist nicht vollständig, aber Sie können sehen, wie Sie ähnliche Korrekturen für eine vollständige Lösung anwenden können. Durch Anwendung dieses Ansatzes im gesamten Code können Sie alle Zuordnungen in `WriteFormattedDocComment()` entfernen.
  
 **Beispiel 4: StringBuilder**  
  
 In diesem Beispiel wird ein <xref:System.Text.StringBuilder>-Objekt verwendet. Die folgende Funktion generiert einen vollständigen Typnamen für generische Typen:  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 Der Schwerpunkt liegt auf der Zeile, die eine neue <xref:System.Text.StringBuilder>-Instanz erstellt. Der Code verursacht eine Zuordnung für `sb.ToString()` und interne Zuordnungen in der <xref:System.Text.StringBuilder>-Implementierung, aber können diese Zuordnungen nicht steuern, wenn Sie das Zeichenfolgenergebnis wollen.
  
 **Korrektur für Beispiel 4**  
  
 Speichern Sie das Objekt zwischen, um die `StringBuilder`-Objektzuordnung zu korrigieren. Jedes Zwischenspeichern einer einzigen Instanz, die möglicherweise entfernt wird, kann die Leistung deutlich verbessern. Im Folgenden sehen Sie die neue Implementierung der Funktion, wobei der Code mit Ausnahme der neuen ersten und letzten Zeile ausgelassen wurde:  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 Die wichtigen Teile sind die neuen Funktionen `AcquireBuilder()` und `GetStringAndReleaseBuilder()`:  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 Da die neuen Compiler Threading verwenden, wird in diesen Implementierungen ein threadstatisches Feld (Attribut <xref:System.ThreadStaticAttribute>) verwendet, um <xref:System.Text.StringBuilder> zwischenzuspeichern, und Sie können die `ThreadStatic`-Deklaration wahrscheinlich übergehen. Das threadstatische Feld enthält einen eindeutigen Wert für jeden Thread, der diesen Code ausführt.
  
 `AcquireBuilder()` gibt die zwischengespeicherte <xref:System.Text.StringBuilder>-Instanz zurück, wenn eine vorhanden ist, nachdem sie gelöscht und das Feld oder der Cache auf Null festgelegt wurden. Andernfalls erstellt `AcquireBuilder()` eine neue Instanz und gibt sie zurück. Die Festlegung des Felds oder Caches auf Null wird dabei beibehalten.
  
 Wenn Sie mit <xref:System.Text.StringBuilder> fertig sind, rufen Sie `GetStringAndReleaseBuilder()` auf, um das Zeichenfolgenergebnis abzurufen, speichern die <xref:System.Text.StringBuilder>-Instanz im Feld oder Cache und geben dann das Ergebnis zurück. Für die Ausführung ist es möglich, diesen Code erneut einzugeben und mehrere <xref:System.Text.StringBuilder>-Objekte zu erstellen (obwohl dies selten geschieht). Der Code speichert nur die zuletzt freigegebene <xref:System.Text.StringBuilder>-Instanz zur späteren Verwendung. Diese einfache Zwischenspeicherstrategie reduziert Zuordnungen in den neuen Compilern deutlich. Teile von .NET Framework und MSBuild („MSBuild“) verwenden eine ähnliche Technik, um die Leistung zu verbessern.
  
 Diese einfache Zwischenspeicherstrategie entspricht einem guten Cachedesign, da sie über eine Größenbeschränkung verfügt. Jetzt ist jedoch mehr Code als im Original vorhanden, was höhere Wartungskosten bedeutet. Sie sollten die Zwischenspeicherstrategie nur übernehmen, wenn Sie ein Leistungsproblem gefunden haben und PerfView gezeigt hat, dass <xref:System.Text.StringBuilder>-Zuordnungen einen signifikanten Beitrag dazu leisten.
  
### <a name="linq-and-lambdas"></a>LINQ und Lambdas  
Language-Integrated Query (LINQ) in Verbindung mit Lambda-Ausdrücken ist ein Beispiel für ein Produktivitätsmerkmal. Die Verwendung kann sich jedoch im Laufe der Zeit erheblich auf die Leistung auswirken, und Sie müssen den Code möglicherweise neu schreiben.
  
 **Example 5: Lambdas, List\<T> und IEnumerable\<T>**  
  
 Dieses Beispiel verwendet [LINQ und Funktionsformatcode](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming), um ein Symbol im Modell des Compilers anhand einer Namenszeichenfolge zu finden:  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 Der neue Compiler und die darauf aufgebauten IDE-Erfahrungen rufen `FindMatchingSymbol()` sehr häufig auf, und es gibt mehrere verborgene Zuordnungen ein der einzigen Codezeile dieser Funktion. Um diese Zuordnungen zu untersuchen, teilen Sie die einzelne Codezeile der Funktion zunächst in zwei Zeilen auf:  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 In der ersten Zeile schließt der [Lambda-Ausdruck](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) `s => s.Name == name` [über](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) die lokale Variable `name`. Das bedeutet, dass zusätzlich zum Zuordnen eines Objekts für den[Delegaten](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type), den `predicate` speichert, der Code eine statische Klasse zuordnet, um die Umgebung zu speichern, die den Wert von `name` erfasst. Der Compiler generiert Code wie den folgenden:  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 Die zwei `new`-Zuordnungen (eine für die Umgebungsklasse und eine für den Delegaten) sind jetzt explizit.
  
 Sehen Sie sich jetzt den Aufruf an `FirstOrDefault` an. Diese Erweiterungsmethode für den <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Typ ruft ebenfalls eine Zuordnung hervor. Da `FirstOrDefault` ein <xref:System.Collections.Generic.IEnumerable%601>-Objekt als erstes Argument annimmt, können Sie den Aufruf in den folgenden Code erweitern (für die Darstellung etwas vereinfacht):  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 Die Variable `symbols` hat den Typ <xref:System.Collections.Generic.List%601>. Der <xref:System.Collections.Generic.List%601>-Auflistungstyp implementiert <xref:System.Collections.Generic.IEnumerable%601> und definiert auf clevere Weise einen Enumerator (<xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle), den <xref:System.Collections.Generic.List%601> mit einem `struct` implementiert. Die Verwendung einer Struktur anstelle einer Klasse bedeutet, dass Sie für gewöhnlich Heapzuordnungen vermeiden, was sich wiederum auf die Garbage Collection-Leistung auswirken kann. Enumeratoren werden normalerweise mit der `foreach`-Schleife der Sprache verwendet, die die Emulatorstruktur verwendet, wie sie auf den Aufrufstapel zurückgegeben wird. Das Erhöhen des Aufruflistenzeigers, um Platz für ein Objekt zu machen, wirkt sich nicht wie eine Heapzuordnung auf die GC aus.
  
 Bei einem erweiterten `FirstOrDefault`-Aufruf muss der Code `GetEnumerator()` auf einem <xref:System.Collections.Generic.IEnumerable%601> aufrufen. Beim Zuordnen von `symbols` zur `enumerable`-Variable des Typs `IEnumerable<Symbol>` geht die Information verloren, dass das tatsächliche Objekt ein <xref:System.Collections.Generic.List%601> ist. Das bedeutet, dass beim Abrufen des Enumerators durch den Code mit `enumerable.GetEnumerator()` .NET Framework die zurückgegebene Struktur verschachteln muss, um sie der Variable `enumerator` zuzuordnen.
  
 **Korrektur für Beispiel 5**  
  
 Die Korrektur besteht darin, `FindMatchingSymbol` wie folgt umzuschreiben und dabei die einzelne Codezeile durch sechs Codezeilen zu ersetzen, die immer noch präzise, einfach zu lesen und zu verstehen und leicht zu warten sind:  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 Dieser Code verwendet keine LINQ-Erweiterungsmethoden, Lambdas oder Enumeratoren und verursacht keine Zuordnungen. Es gibt keine Zuordnungen, weil der Compiler sehen kann, dass die `symbols`-Auflistung eine <xref:System.Collections.Generic.List%601> ist und den resultierenden Enumerator (eine Struktur) an eine lokale Variable des richtigen Typs binden kann, um ein Boxing zu vermeiden. Die ursprüngliche Version dieser Funktion war ein hervorragendes Beispiel für die Ausdrucksstärke von C# und die Produktivität von .NET Framework. Diese neue und effizientere Version behält diese Qualitäten bei, ohne komplexen Code hinzuzufügen, der gewartet werden muss.
  
### <a name="async-method-caching"></a>Zwischenspeichern der Async-Methode  

Das nächste Beispiel zeigt ein typisches Problem, wenn Sie versuchen, zwischengespeicherte Ergebnisse in einer [Async](../../csharp/programming-guide/concepts/async/index.md)-Methode zu verwenden.
  
 **Beispiel 6: Zwischenspeichern in Async-Methoden**  
  
 Die Visual Studio IDE-Funktionen, die auf den neuen C#- und Visual Basic-Compilern aufgebaut sind, rufen häufig Syntaxstrukturen auf, und die Compiler verwenden dabei Async, damit Visual Studio reaktionsfähig bleibt. Hier ist die erste Version des Codes, den Sie möglicherweise schreiben, um eine Syntaxstruktur abzurufen:  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 Sie sehen, dass durch das Aufrufen von `GetSyntaxTreeAsync()` ein `Parser` initiiert, der Code analysiert und dann ein <xref:System.Threading.Tasks.Task>-Objekt, `Task<SyntaxTree>`, zurückgegeben wird. Der ressourcenintensive Teil ist das Zuordnen der `Parser`-Instanz und das Analysieren des Codes. Die Funktion gibt einen <xref:System.Threading.Tasks.Task> zurück, sodass Aufrufer auf die Analysearbeit warten und den UI-Thread freigeben können, damit er auf Benutzereingaben reagiert.
  
 Möglicherweise versuchen mehrere Visual Studio-Funktionen, dieselbe Syntaxstruktur abzurufen, deshalb können Sie den folgenden Code schreiben, um die Analyseergebnisse zwischenzuspeichern und so Zeit und Zuordnungen zu sparen. Dieser Code ruft jedoch eine Zuordnung hervor:  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 Sie sehen, dass der neue Code mit Zwischenspeichern ein `SyntaxTree`-Feld mit dem Namen `cachedResult` hat. Wenn dieses Feld Null ist, übernimmt `GetSyntaxTreeAsync()` die Arbeit und speichert das Ergebnis im Cache. `GetSyntaxTreeAsync()` gibt das `SyntaxTree`-Objekt zurück. Wenn Sie eine `async`-Funktion des Typs `Task<SyntaxTree>` haben und einen Wert des Typs `SyntaxTree` zurückgeben, besteht das Problem darin, dass der Compiler Code ausgibt, um eine Aufgabe zuzuordnen, die das Ergebnis speichert (durch Verwendung von `Task<SyntaxTree>.FromResult()`). Die Aufgabe wird als abgeschlossen gekennzeichnet, und das Ergebnis ist sofort verfügbar. Im Code für die neuen Compiler kamen bereits abgeschlossene <xref:System.Threading.Tasks.Task>-Objekte so oft vor, dass eine Korrektur dieser Zuordnungen die Reaktionsfähigkeit merklich verbessert hat.
  
 **Korrektur für Beispiel 6**  
  
 Um die <xref:System.Threading.Tasks.Task> abgeschlossene Zuordnung zu entfernen, können Sie das Task-Objekt mit dem abgeschlossenen Ergebnis zwischenspeichern:  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 Dieser Code ändert den Typ von `cachedResult` in `Task<SyntaxTree>` und wendet eine `async`-Hilfsfunktion an, die den Originalcode von `GetSyntaxTreeAsync()` speichert. `GetSyntaxTreeAsync()` verwendet jetzt den [NULL-Sammeloperator](../../csharp/language-reference/operators/null-coalescing-operator.md), um `cachedResult` zurückzugeben, wenn es nicht NULL ist. Wenn `cachedResult` Null ist, ruft `GetSyntaxTreeAsync()``GetSyntaxTreeUncachedAsync()` auf und speichert das Ergebnis zwischen. Beachten Sie, dass `GetSyntaxTreeAsync()` nicht auf den Aufruf an `GetSyntaxTreeUncachedAsync()` wartet, wie es der Code normalerweise tun würde. Wenn await nicht verwendetet wird, bedeutet das, dass, wenn `GetSyntaxTreeUncachedAsync()` sein <xref:System.Threading.Tasks.Task>-Objekt zurückgibt, `GetSyntaxTreeAsync()` sofort <xref:System.Threading.Tasks.Task> zurückgibt. Jetzt ist das zwischengespeicherte Objekt ein <xref:System.Threading.Tasks.Task>, sodass keine Zuordnungen vorhanden sind, die das zwischengespeicherte Ergebnis zurückgeben.
  
### <a name="additional-considerations"></a>Weitere Überlegungen  
 Hier sind einige weitere Punkt zu potenziellen Problemen in großen Apps oder Apps, die viele Daten verarbeiten.
  
 **Wörterbücher**  
  
 Wörterbücher sind in vielen Programmen allgegenwärtig, denn sie sind sehr praktisch und an sich effizient. Aber oft werden sie nicht ordnungsgemäß verwendet. In Visual Studio und den Compilern zeigen Analysen, dass viele der Wörterbücher ein einziges Element enthielten oder leer waren. Ein leeres <xref:System.Collections.Generic.Dictionary%602> hat zehn Felder und belegt 48 Byte auf dem Heap in einem x86-Computer. Wörterbücher sind großartig, wenn Sie eine Zuordnung oder assoziative Datenstruktur mit konstanter Zeitsuche benötigen. Wenn Sie jedoch nur einige wenige Elemente haben, verschwenden Sie viel Speicherplatz, wenn Sie ein Wörterbuch verwenden. Stattdessen könnten Sie beispielsweise ebenso schnell iterativ ein `List<KeyValuePair\<K,V>>` durchsuchen. Wenn Sie ein Wörterbuch nur verwenden, um es mit Daten zu laden und dann daraus zu lesen (ein sehr übliches Muster), ist die Verwendung eines sortierten Arrays mit einer N(log(N))-Suche möglicherweise je nach Anzahl der verwendeten Elemente nahezu ebenso schnell.
  
 **Klassen im Vergleich zu Strukturen**  
  
 Auf eine gewisse Weise bieten Klassen und Strukturen einen klassischen Platz-/Zeitkompromiss für die Optimierung Ihrer Apps. Klassen verursachen 12 Byte Mehraufwand auf einem x86-Computer, selbst wenn sie keine Felder haben, allerdings ist das Übergeben nicht ressourcenintensiv, da nur ein Zeiger erforderlich ist, um auf eine Klasseninstanz zu verweisen. Strukturen verursachen keine Heapzuordnungen, wenn sie nicht verschachtelt sind, aber wenn Sie große Strukturen als Funktionsargumente oder Rückgabewerte übergeben, ist CPU-Zeit erforderlich, um alle Datenmitglieder der Strukturen atomisch zu kopieren. Achten Sie auf wiederholte Aufrufe an Eigenschaften, die Strukturen zurückgeben, und speichern Sie den Wert der Eigenschaft in einer lokalen Variable zwischen, um ein übermäßiges Kopieren von Daten zu vermeiden.
  
 **Caches**  
  
 Ein gängiger Leistungstrick besteht darin, Ergebnisse zwischenzuspeichern. Aber ein Cache ohne Größenbeschränkung oder Entsorgungsrichtlinie kann zu einem Speicherverlust führen. Wenn große Datenmengen verarbeitet werden und Sie viel Arbeitsspeicher in Caches speichern, kann die Garbage Collection die Vorteile Ihrer zwischengespeicherten Suchen aufheben.
  
 In diesem Artikel haben wir dargestellt, dass Ihnen Leistungsengpasssymptome bewusst sein sollten, die sich auf die Reaktionsfähigkeit Ihrer App auswirken können, insbesondere bei großen Systemen oder Systemen, die große Datenmengen verarbeiten. Zu den typischen Übeltätern gehören Boxing, Zeichenfolgenmanipulationen, LINQ und Lambda, das Zwischenspeichern in Async-Methoden, das Zwischenspeichern ohne Größenbeschränkung oder Entsorgungsrichtlinie, die nicht ordnungsgemäße Verwendung von Wörterbüchern und das Übergeben von Strukturen. Behalten Sie die vier Fakten für die Optimierung von Apps im Hinterkopf:  
  
- Keine vorzeitige Optimierung: Seien Sie produktiv, und optimieren Sie Ihre App, wenn Sie Probleme entdecken.
  
- Profile lügen nicht: Sie raten, wenn Sie nicht messen.
  
- Gute Tools machen einen großen Unterschied: Laden Sie PerfView herunter, und probieren Sie es aus.
  
- Es dreht sich alles um Zuordnungen: Hier hat das Compilerplattformteam die meiste Zeit mit der Optimierung der Leistung der neuen Compiler verbracht.
  
## <a name="see-also"></a>Weitere Informationen

- [Video mit einer Darstellung dieses Themas](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [Einführung in die Leistungsprofilerstellung](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [Leistung](index.md)
- [.NET-Leistungstipps](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))
- [Channel 9 PerfView-Tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [.NET Compiler Platform-SDK](../../csharp/roslyn-sdk/index.md)
- [dotnet/roslyn-Repository auf GitHub](https://github.com/dotnet/roslyn)
