---
title: "Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen"
description: "Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 057faa0ad78dfb0a600dad2a1f0aeea240f33282

---

# <a name="best-practices-for-using-strings"></a>Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen

.NET bietet umfangreiche Unterstützung für das Entwickeln von lokalisierten und globalisierten Anwendungen und erleichtert bei der Ausführung allgemeiner Operationen das Übernehmen von Konventionen der aktuellen oder einer anderen Kultur, beispielsweise bei der Sortierung und Anzeige von Zeichenfolgen. Das Sortieren oder Vergleichen von Zeichenfolgen stellt jedoch nicht immer eine kulturabhängige Operation dar. Beispielsweise sollten interne Zeichenfolgen von Anwendungen i. d. R. in allen Kulturen gleich behandelt werden. Wenn kulturabhängige Zeichenfolgendaten, z. B. XML-Tags, HTML-Tags, Benutzernamen, Dateipfade und Systemobjektnamen, kulturabhängig interpretiert werden, können Fehler im Anwendungscode auftreten, die Leistung kann sich verschlechtern, und in einigen Fällen kann es zu Sicherheitsproblemen kommen.

In diesem Artikel werden die Methoden für die Sortierung, den Vergleich und die Schreibweise von Zeichenfolgen in .NET untersucht. Darüber hinaus werden Empfehlungen zum Auswählen einer entsprechenden Zeichenfolgen-Behandlungsmethode gegeben und weitere Informationen dazu bereitgestellt. Er wird außerdem untersucht, wie formatierte Daten, z. B. numerische Daten und Datums-/Uhrzeitdaten, für die Anzeige und Speicherung behandelt werden. 

Dieser Artikel enthält folgende Abschnitte:

* [Empfehlungen zur Zeichenfolgenverwendung](#recommendations-for-string-usage)

* [Explizites Angeben von Zeichenfolgenvergleichen](#specifying-string-comparisons-explicitly)

* [Details zum Zeichenfolgenvergleich](#the-details-of-string-comparison)

* [Auswählen eines StringComparison-Members für den Methodenaufruf](#choosing-a-stringcomparison-member-for-your-method-call)

* [Allgemeine Methoden für den Zeichenfolgenvergleich](#common-string-comparison-methods)

* [Methoden für den indirekten Zeichenfolgenvergleich](#methods-that-perform-string-comparison-indirectly)

* [Anzeigen und Beibehalten von formatierten Daten](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a>Empfehlungen zur Zeichenfolgenverwendung

Beachten Sie folgende grundlegende Empfehlungen zur Verwendung von Zeichenfolgen bei der Entwicklung mit .NET: 

* Verwenden Sie Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen explizit angeben. Normalerweise müssen Sie dazu eine Methodenüberladung mit einem Parameter vom Typ [StringComparison](xref:System.StringComparison) aufrufen.

* Verwenden Sie [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) als Ihre sichere Standardeinstellung für kulturunabhängige Zeichenfolgenvergleiche.

* Verwenden Sie Vergleiche mit [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) für eine bessere Leistung.

* Verwenden Sie Zeichenfolgenoperationen, die auf [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) basieren, um die Ausgabe für Benutzer anzuzeigen.

* Verwenden Sie die nicht linguistischen Werte [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) anstelle von Zeichenfolgenoperationen, die auf [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) basieren, wenn der Vergleich linguistisch nicht relevant ist (z.B. symbolisch).

* Verwenden Sie die [String.ToUpperInvariant](xref:System.String.ToUpperInvariant)-Methode anstelle der [String.ToLowerInvariant](xref:System.String.ToLowerInvariant)-Methode, wenn Sie Zeichenfolgen für einen Vergleich normalisieren.

* Verwenden Sie eine Überladung der [String](xref:System.String)`Equals`-Methode, um zu überprüfen, ob zwei Zeichenfolgen übereinstimmen.

* Verwenden Sie eine Überladung von der [String](xref:System.String)`Compare`- und [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode zum Sortieren von Zeichenfolgen, nicht zur Überprüfung auf Gleichheit.

* Verwenden Sie kulturabhängige Formatierung, um Daten, die keine Zeichenfolge sind, z. B. Zahlen und Datumsangaben, auf einer Benutzeroberfläche anzuzeigen. Verwenden Sie Formatierung mit der invarianten Kultur, um Daten, die keine Zeichenfolge sind, im Zeichenfolgenformat beizubehalten.

Vermeiden Sie folgende Vorgehensweisen bei der Verwendung von Zeichenfolgen:

* Verwenden Sie keine Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen nicht explizit oder implizit angeben. 

* Verwenden Sie keine Überladung der [String](xref:System.String)`Compare`-Methode oder der [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode, und führen Sie eine Überprüfung mit einem Rückgabewert von 0 (null) durch, um zu bestimmen, ob zwei Zeichenfolgen übereinstimmen.

* Verwenden Sie nicht kulturabhängige Formatierung, um numerische Daten oder Datums-/Uhrzeitdaten im Zeichenfolgenformat beizubehalten.

## <a name="specifying-string-comparisons-explicitly"></a>Explizites Angeben von Zeichenfolgenvergleichen

Die Methoden zum Bearbeiten von Zeichenfolgen in .NET werden i.d.R. überladen. Während einige Überladungen normalerweise Standardwerte akzeptieren, geben andere Überladungen exakt an, wie Zeichenfolgen verglichen oder bearbeitet werden sollen. Methoden, die keine Standardwerte verwenden, enthalten i.d.R einen Parameter vom Typ [StringComparison](xref:System.StringComparison). Dabei handelt es sich um eine Enumeration, die explizit Regeln für Zeichenfolgenvergleiche anhand von Kultur und Schreibweise angibt. In der folgenden Tabelle werden die Member der [StringComparison](xref:System.StringComparison)-Enumeration beschrieben. 

StringComparison-Member | Beschreibung
----------------------- | -----------
[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) | Führt einen Vergleich mit der aktuellen Kultur unter Beachtung der Groß- und Kleinschreibung durch.
[CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) | Führt einen Vergleich mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung durch.
[StringComparison.Ordinal](xref:System.StringComparison.Ordinal) | Führt einen Ordinalvergleich durch.
[StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) | Führt einen Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung durch.

Die [String](xref:System.String)`IndexOf`-Methode, die den Index einer Teilzeichenfolge in einem [String](xref:System.String)-Objekt zurückgibt, das einem Zeichen oder einer Zeichenfolge entspricht, weist beispielsweise neun Überladungen auf:

* [IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) und [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)) führen standardmäßig eine kulturunabhängige Ordinalsuche nach einem Zeichen in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.

* [IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) und [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)) führen standardmäßig eine kulturunabhängige Ordinalsuche nach einer Teilzeichenfolge in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.

* [IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) und [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)) enthalten einen Parameter vom Typ StringComparison, mit dem die Form des Vergleichs angegeben werden kann.

Aus den folgenden Gründen wird empfohlen, eine Überladung ohne Standardwerte auszuwählen:

* Einige Überladungen mit Standardparametern (die in der Zeichenfolgeninstanz nach einem [Char](xref:System.Char) suchen) führen einen Ordinalvergleich durch, während andere Überladungen (die in der Zeichenfolgeninstanz nach einer Zeichenfolge suchen) kulturabhängig sind. Es ist nicht leicht, sich zu merken, welche Methode welchen Standardwert verwendet, und Überladungen können schnell verwechselt werden.

* Der Zweck des Codes, der Standardwerte für Methodenaufrufe verwendet, ist nicht klar. Im folgenden Beispiel werden Standardwerte verwendet. Dabei ist nicht klar, ob der Entwickler tatsächlich einen ordinalen oder linguistischen Vergleich zweier Zeichenfolgen durchführen wollte oder ob der Unterschied in der Groß- und Kleinschreibung zwischen `protocol` und "http" möglicherweise dazu führt, dass bei einer Überprüfung auf Gleichheit `false` zurückgegeben wird.

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http") Then
  ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

Im Allgemeinen empfiehlt es sich, eine Methode aufzurufen, die keine Standardwerte verwendet, da der Zweck des Codes andernfalls möglicherweise nicht eindeutig ist. Dies erleichtert wiederum das Lesen, Verwalten und Debuggen des Codes. Im folgenden Beispiel wird auf die Fragen eingegangen, die sich zum vorherigen Beispiel stellen. Es wird deutlich gemacht, dass der Ordinalvergleich verwendet wird und dass Unterschiede in der Groß- und Kleinschreibung ignoriert werden. 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a>Details zum Zeichenfolgenvergleich

Zeichenfolgenvergleiche bilden den Kern zahlreicher Operationen, die sich auf Zeichenfolgen beziehen; dies gilt insbesondere für Sortierungen und Überprüfungen auf Gleichheit. Zeichenfolgen werden in einer bestimmten Reihenfolge sortiert: Wenn "my" in einer sortierten Zeichenfolgenliste vor "string" angezeigt wird, muss "my" bei einem Vergleich einen kleineren oder gleichen Wert wie "string" haben. Darüber hinaus wird beim Vergleich implizit Gleichheit definiert. Die Vergleichsoperation gibt 0 (null) für Zeichenfolgen zurück, die als gleich betrachtet werden. Dies kann so interpretiert werden, dass keine Zeichenfolge kleiner ist als die andere. Sinnvolle Operationen mit Zeichenfolgen schließen i. d. R. mindestens eines der folgenden Verfahren ein: Vergleich mit einer anderen Zeichenfolge und Ausführen eines genau definierten Sortiervorgangs.

Die Überprüfung der Sortierreihenfolge zweier Zeichenfolgen oder ihre Überprüfung auf Gleichheit ergibt jedoch nicht ein einzelnes richtiges Ergebnis. Das Ergebnis ist vielmehr abhängig von den Kriterien, die dem Zeichenfolgenvergleich zugrunde liegen. Insbesondere können Zeichenfolgenvergleiche zu unterschiedlichen Ergebnissen führen, die Ordinalvergleiche darstellen oder auf der Schreibweise und den Sortierungskonventionen der aktuellen oder der invarianten Kultur (eine auf der englischen Sprache basierende Kultur, die nicht von einem Gebietsschema abhängig ist) basieren.

### <a name="string-comparisons-that-use-the-current-culture"></a>Zeichenfolgenvergleiche mit der aktuellen Kultur

Ein Kriterium für Zeichenfolgenvergleiche stellt die Verwendung der Konventionen der aktuellen Kultur dar. Vergleiche, die auf der aktuellen Kultur basieren, verwenden die aktuelle Kultur oder das aktuelle Gebietsschema des Threads. Vergleiche, die auf der aktuellen Kultur basieren, sollten immer dann verwendet werden, wenn Daten linguistisch relevant sind und kulturabhängige Interaktionen von Benutzern widerspiegeln. 

Das Verhalten im Hinblick auf Vergleiche und die Groß- und Kleinschreibung in .NET ändert sich jedoch, wenn sich die Kultur ändert. Dies ist der Fall, wenn eine Anwendung auf einem Computer mit einer anderen Kultur ausgeführt wird, als der Computer, auf dem die Anwendung entwickelt wurde, oder wenn der ausführende Thread seine Kultur ändert. Dieses Verhalten ist beabsichtigt, für viele Entwickler jedoch nicht offensichtlich. Im folgenden Beispiel werden die Unterschiede zwischen den Sortierreihenfolgen in der englischen (amerikanisch, "en-US") und schwedischen ("sv-SE") Kultur herausgestellt. Beachten Sie, dass die Wörter „ångström“, „Windows“ und „Visual Studio“ in den sortierten Zeichenfolgenarrays an unterschiedlichen Positionen angezeigt werden.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

Vergleiche mit der aktuellen Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, entsprechen kulturabhängigen Vergleichen, ignorieren jedoch die Schreibweise, die von der aktuellen Kultur des Threads vorgegeben wird. Dieses Verhalten zeigt sich möglicherweise auch bei Sortierreihenfolgen. 

Vergleiche mit der Semantik der aktuellen Kultur werden standardmäßig für folgende Methoden verwendet:

* [String](xref:System.String)`Compare`-Überladungen, die keinen [StringComparison](xref:System.StringComparison)-Parameter enthalten.

* [String.CompareTo](xref:System.String.CompareTo(System.String))-Überladungen.

* Die standardmäßige [String.StartsWith(String)](xref:System.String.StartsWith(System.String))-Methode. 

* Die standardmäßige [String.EndsWith(String)](xref:System.String.EndsWith(System.String))-Methode.

* [String](xref:System.String)`IndexOf`-Überladungen, die einen [String](xref:System.String) als Suchparameter akzeptieren und keinen [StringComparison](xref:System.StringComparison)-Parameter aufweisen.

* [String](xref:System.String)`LastIndexOf`-Überladungen, die einen [String](xref:System.String) als Suchparameter akzeptieren und keinen [StringComparison](xref:System.StringComparison)-Parameter aufweisen.

In jedem Fall sollten Sie eine Überladung mit einem [StringComparison](xref:System.StringComparison)-Parameter aufrufen, um den Zweck des Methodenaufrufs eindeutig anzugeben. 

Wenn nicht linguistische Zeichenfolgendaten linguistisch interpretiert werden, oder wenn Zeichenfolgendaten in einer bestimmten Kultur mit den Konventionen einer anderen Kultur interpretiert werden, können offensichtliche und nur schwer erkennbare Fehler auftreten. Kanonisches Beispiel ist das Problem mit dem Zeichen "I" im Türkischen.

In beinahe allen lateinischen Alphabetarten,  einschließlich des englischen (USA) Alphabets, ist das Zeichen "i" (\u0069) die Kleinschreibungsvariante des Zeichens "I" (\u0049). Diese Regel zur Groß- und Kleinschreibung wird von Entwicklern, die in den entsprechenden Kulturen programmieren, leicht als Standard zugrunde gelegt. Das türkische Alphabet („tr-TR“) enthält jedoch ein „I“ mit einem Punkt („İ“ bzw. \u0130), welches den Großbuchstaben des Zeichens „i“ darstellt. Ferner verfügt Türkisch auch über ein kleines „i ohne Punkt“ („ı“ bzw. \u0131), dessen Entsprechung als Großbuchstabe das Zeichen „I“ ist. Die Kultur Aserbaidschanisch (az-AZ) weist ein analoges Verhalten auf.

Annahmen über die Großschreibung von "i" oder die Kleinschreibung von "I" sind daher nicht für alle Kulturen gleichermaßen gültig. Wenn Sie die Standardüberladungen für Zeichenfolgenvergleichsroutinen verwenden, weisen diese je nach der zugrunde liegenden Kultur Unterschiede auf. Bei einem Vergleich nicht linguistischer Daten kann die Verwendung der Standardüberladungen zu unerwünschten Ergebnissen führen. Dies wird durch den folgenden Versuch veranschaulicht, einen Vergleich der Zeichenfolgen "file" und "FILE" ohne Beachtung der Groß- und Kleinschreibung durchzuführen.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

Dieser Vergleich kann signifikante Probleme verursachen, wenn die Kultur versehentlich in sicherheitsrelevanten Einstellungen verwendet wird, wie im folgenden Beispiel veranschaulicht. Ein Methodenaufruf wie `IsFileURI("file:")` gibt `true` zurück, wenn die aktuelle Kultur "Englisch (USA)" ist und `false`, wenn die aktuelle Kultur "Türkisch" ist. In einem System mit der Kultur "Türkisch" wäre es daher vorstellbar, dass Sicherheitsvorkehrungen umgangen werden, die den Zugriff auf URIs blockieren, die mit "FILE:" beginnen und nicht zwischen Groß- und Kleinschreibung unterscheiden.

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

Stattdessen sollte der Code daher in diesem Fall wie im folgenden Beispiel geschrieben werden, da "file:" als nicht linguistischer und kulturunabhängiger Bezeichner interpretiert werden soll.

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a>Ordinalzeichenfolgenoperationen

Der [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)- oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)-Wert in einem Methodenaufruf kennzeichnet einen nicht linguistischen Vergleich, in dem die Features von natürlichen Sprachen ignoriert werden. Bei Methoden, die mit diesen [StringComparison](xref:System.StringComparison)-Werten aufgerufen werden, werden für Entscheidungen bezüglich Zeichenfolgenoperation einfache Bytevergleiche anstelle von Groß- und Kleinschreibung oder nach Kultur parametrisierten Entsprechungstabellen zugrunde gelegt. In aller Regel ist diese Vorgehensweise am besten für die beabsichtigte Interpretation von Zeichenfolgen geeignet und macht den Code sicherer und zuverlässiger. 

Ordinalvergleiche sind Zeichenfolgenvergleiche, in denen die einzelnen Bytes einer Zeichenfolge ohne linguistische Interpretation verglichen werden, z. B. entspricht "windows" nicht "Windows". Verwenden Sie diesen Vergleich, wenn der Kontext eine exakte Entsprechung von Zeichenfolgen oder eine konservative Entsprechungsrichtlinie verlangt. Darüber hinaus werden Ordinalvergleiche am schnellsten durchgeführt, da beim Bestimmen eines Ergebnisses keine linguistischen Regeln verwendet werden.

Zeichenfolgen in .NET können eingebettete NULL-Zeichen aufweisen. Einer der auffälligsten Unterschiede zwischen einem ordinalen und einem kulturabhängigen Vergleich (einschließlich Vergleichen, die die invariante Kultur verwenden) betrifft die Behandlung von eingebetteten NULL-Zeichen in einer Zeichenfolge. Wenn Sie die [String](xref:System.String)`Compare`-Methode und die [String](xref:System.String)`Equals`-Methode verwenden, um kulturabhängige Vergleiche (einschließlich Vergleichen, die die invariante Kultur verwenden) durchzuführen, werden diese Zeichen ignoriert. Bei kulturabhängigen Vergleichen können Zeichenfolgen mit eingebetteten NULL-Zeichen daher als gleichwertig mit Zeichenfolgen ohne diese Zeichen angesehen werden. 

> [!IMPORTANT]
> Auch wenn eingebettete NULL-Zeichen von Zeichenfolgenvergleichs-Methoden ignoriert werden, bei Zeichenfolgensuch-Methoden wie z.B. [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) und [String.StartsWith](xref:System.String.StartsWith(System.String)) ist dies nicht der Fall. 

Im folgenden Beispiel wird ein kulturabhängiger Vergleich der Zeichenfolge "Aa" mit einer ähnlichen Zeichenfolge durchgeführt, die mehrere eingebettete NULL-Zeichen zwischen "A" und "a" enthält, und es wird angezeigt, inwieweit die beiden Zeichenfolgen als gleich betrachtet werden. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

Bei einem Ordinalvergleich werden die Zeichenfolgen jedoch nicht als gleich betrachtet, wie das folgende Beispiel zeigt.

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

Ordinalvergleiche, bei denen die Groß- und Kleinschreibung nicht beachtet wird, folgen als nächster konservativer Ansatz. Diese Vergleichen ignorieren die Groß- und Kleinschreibung i. d. R.; "windows" entspricht dann beispielsweise "Windows". Im Hinblick auf ASCII-Zeichen entspricht diese Richtlinie [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), mit der Ausnahme, dass die üblichen ASCII-Schreibungsregeln nicht beachtet werden. Ein beliebiges Zeichen in \[A, Z\] (\u0041-\u005A) entspricht daher dem zugehörigen Zeichen in \[a, z\] (\u0061-\007A). Die Groß- und Kleinschreibung außerhalb des ASCII-Bereichs verwendet die Tabellen der invarianten Kultur. Daher entspricht der folgende Vergleich

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

dem nachstehenden Vergleich (ist jedoch schneller): 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

Diese Vergleiche werden immer noch sehr schnell durchgeführt.

Sowohl [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) als auch [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) verwendet die Binärwerte direkt und eignet sich am besten für Vergleiche. Wenn Sie nicht sicher über die Vergleichseinstellungen sind, verwenden Sie einen dieser beiden Werte. Da hier jedoch ein Vergleich auf Byteebene durchgeführt wird, erfolgt die Sortierung nicht anhand einer linguistischen Sortierreihenfolge (analog zu einem englischen Wörterbuch), sondern anhand einer binären Rangfolge. Die Ergebnisse erscheinen Benutzern möglicherweise in den meisten Kontexten seltsam.

Ordinalsemantik ist die Standardeinstellung für [String](xref:System.String)`Equals`-Überladungen, die kein [StringComparison](xref:System.StringComparison)-Argument (einschließlich des Gleichheitsoperators) enthalten. In jedem Fall wird empfohlen, eine Überladung mit einem [StringComparison](xref:System.StringComparison)-Parameter aufzurufen.

### <a name="string-operations-that-use-the-invariant-culture"></a>Zeichenfolgenoperationen mit der invarianten Kultur

Vergleiche mit der invarianten Kultur verwenden die [CompareInfo](xref:System.Globalization.CompareInfo)-Eigenschaft, die von der statischen [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft zurückgegeben wird. Dieses Verhalten ist in allen Systemen gleich: Zeichen außerhalb des Bereichs werden in Zeichen übersetzt, von denen angenommen wird, dass es sich um die invarianten Entsprechungen handelt. Diese Richtlinie kann für das kulturübergreifende Beibehalten eines Satzes von Zeichenfolgenverhalten hilfreich sein, führt jedoch oftmals zu unerwarteten Ergebnissen.

Vergleiche mit der invarianten Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, verwenden für Vergleichsinformationen ebenfalls die statische [CompareInfo](xref:System.Globalization.CompareInfo)-Eigenschaft, die von der statischen [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft zurückgegeben wird. Alle Unterschiede bezüglich der Groß- und Kleinschreibung in den übersetzten Zeichen werden ignoriert.

Das [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Objekt führt dazu, dass eine [String](xref:System.String)`Compare`-Methode bestimmte Zeichensätze als äquivalent interpretiert. Die folgende Äquivalenz ist beispielsweise in der invarianten Kultur gültig:

InvariantCulture: a + ̊ = å

Der lateinische Kleinbuchstabe „a“ (\u0061) wird, wenn er sich neben dem kombinierenden übergesetzten Ring "+ " ̊" (\u030a) befindet, als lateinischer Kleinbuchstabe mit übergesetztem Ring „å“ (\u00e5) interpretiert. Wie das folgende Beispiel zeigt, unterscheidet sich dieses Verhalten vom Ordinalvergleich.

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

Wenn sie Dateinamen, Cookies oder andere Elemente interpretieren, die eine Kombination wie „å“ enthalten können, bieten Ordinalvergleiche immer noch das transparenteste und am besten geeignete Verhalten an.

Insgesamt verfügt die invariante Kultur nur über sehr wenige Eigenschaften, die für einen Vergleich hilfreich sind. Sie führt Vergleiche mit linguistischer Relevanz durch und kann daher keine vollständige symbolische Äquivalenz garantieren, eignet sich jedoch nicht unbedingt für die Anzeige in einer beliebigen Kultur. Wenn beispielsweise eine große Datendatei mit einer Liste sortierter Anzeigebezeichner einer Anwendung angehört, würde das Hinzufügen von Elementen zu dieser Liste einen Einfügevorgang mit invarianter Sortierung erfordern.

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a>Auswählen eines StringComparison-Members für den Methodenaufruf

In der folgenden Tabelle wird die Zuordnung von semantischem Zeichenfolgenkontext zu einem [StringComparison](xref:System.StringComparison)-Enumerationsmember beschrieben.

Daten | Verhalten | System.StringComparison-Entsprechungswert
---- | -------- | -------------------------------------------
Interne Bezeichner, die Groß-/Kleinschreibung beachten, Bezeichner in Standards wie XML und HTTP, die Groß-/Kleinschreibung beachten, oder sicherheitsbezogene Einstellungen, die Groß-/Kleinschreibung beachten. | Ein nicht linguistischer Bezeichner mit exakt übereinstimmenden Bytes. | [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)
Interne Bezeichner, die Groß-/Kleinschreibung beachten, Bezeichner in Standards wie XML und HTTP, Dateipfade, Registrierungsschlüssel und Werte, Umgebungsvariablen, Ressourcenbezeichner (z.B. Handlenamen), die Groß-/Kleinschreibung beachten, oder sicherheitsbezogene Einstellungen, die Groß-/Kleinschreibung beachten. | Ein nicht linguistischer Bezeichner, wo die Groß-/Kleinschreibung irrelevant ist. | [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)
Daten, die für den Benutzer angezeigt werden, oder die meisten Benutzereingaben. | Daten, die lokale linguistische Regeln erfordern. | [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) oder [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)

## <a name="common-string-comparison-methods"></a>Allgemeine Methoden für den Zeichenfolgenvergleich

In den folgenden Abschnitten werden die Methoden beschrieben, die am häufigsten für Zeichenfolgenvergleiche verwendet werden.

### <a name="stringcompare"></a>String.Compare

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Der Aufruf dieser Methode stellt die zentrale Operation für Zeichenfolgeninterpretation dar. Aus diesem Grund sollten alle Instanzen von Methodenaufrufen untersucht werden, um zu bestimmen, ob Zeichenfolgen anhand der aktuellen Kultur oder unabhängig von der Kultur (symbolisch) interpretiert werden sollen. Üblicherweise handelt es sich um eine symbolische Interpretation, und stattdessen sollte ein [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)-Vergleich verwendet werden.

Die [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo)-Klasse, die von der [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo)-Eigenschaft zurückgegeben wird, enthält auch eine [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions))-Methode, die zahlreiche Vergleichsoptionen (ordinal, ohne Leerraumzeichen, ohne Zeichen vom Typ Kana usw.) über die [CompareOptions](xref:System.Globalization.CompareOptions)-Flagenumeration zur Verfügung stellt. 

### <a name="stringcompareto"></a>String.CompareTo

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Diese Methode bietet derzeit keine Überladung an, die einen [StringComparison](xref:System.StringComparison)-Typ angibt. Es ist in der Regel möglich, diese Methode in die empfohlene [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison))-Form zu konvertieren.

Diese Methode wird von Typen implementiert, die die [IComparable](xref:System.IComparable)- und [IComparable&lt;T&gt;](xref:System.IComparable%601)-Schnittstelle implementieren. Da der [StringComparison](xref:System.StringComparison)-Parameter hier nicht verfügbar ist, ermöglichen implementierende Typen oftmals das Angeben eines [StringComparer](xref:System.StringComparer) im entsprechenden Konstruktor. Im folgenden Beispiel wird eine `FileName`-Klasse definiert, deren Klassenkonstruktor einen [StringComparer](xref:System.StringComparer)-Parameter enthält. Dieses [StringComparer](xref:System.StringComparer)-Objekt wird dann in der `FileName.CompareTo`-Methode verwendet.

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a>String.Equals

Standardinterpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

Mit der [String](xref:System.String)-Klasse können Sie eine Überprüfung auf Gleichheit durchführen, indem Sie die Überladungen der statischen `Equals`-Methode oder der entsprechenden Instanzenmethode aufrufen, oder indem Sie den statischen Gleichheitsoperator verwenden. Die Überladungen und der Operator verwenden standardmäßig einen Ordinalvergleich . Unabhängig davon wird jedoch empfohlen, eine Überladung aufzurufen, die den [StringComparison](xref:System.StringComparison)-Typ explizit angibt; dies gilt auch, wenn Sie einen Ordinalvergleich ausführen möchten. Auf diese Weise können bestimmte Zeichenfolgeninterpretationen leichter in Code gefunden werden. 

### <a name="stringtoupper-and-stringtolower"></a>String.ToUpper und String.ToLower

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Diese Methoden sollten mit besonderer Sorgfalt verwendet werden, da das Erzwingen der Groß- oder Kleinschreibung einer Zeichenfolge oftmals unabhängig von der Schreibweise als kleine Normalisierung für Zeichenfolgenvergleiche verwendet wird. Wenn dies der Fall ist, sollten Sie einen Vergleich ohne Beachtung der Groß- und Kleinschreibung in Erwägung ziehen. 

Die [String.ToUpperInvariant](xref:System.String.ToUpperInvariant)- und [String.ToLowerInvariant](xref:System.String.ToLowerInvariant)-Methode sind ebenfalls verfügbar. [ToUpperInvariant](xref:System.String.ToUpperInvariant) wird standardmäßig zur Normalisierung der Schreibweise verwendet. Mit [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) durchgeführte Vergleiche entsprechen der Zusammensetzung von zwei Aufrufen: Aufruf von [ToUpperInvariant](xref:System.String.ToUpperInvariant) für beide Zeichenfolgenargumente und ein Vergleich mithilfe von [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

Überladungen sind auch für die Konvertierung in Groß- und Kleinschreibung in einer bestimmten Kultur verfügbar. Dazu wird ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt übergeben, das die Kultur für die Methode darstellt.

### <a name="chartoupper-and-chartolower"></a>Char.ToUpper und Char.ToLower

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Diese Methoden funktionieren ähnlich wie die [String.ToUpper](xref:System.String.ToUpper)-Methode und [String.ToLower](xref:System.String.ToLower)-Methode, die im vorherigen Abschnitt beschrieben werden.

### <a name="stringstartswith-and-stringendswith"></a>String.StartsWith und String.EndsWith

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Standardmäßig führen beide Methoden einen kulturabhängigen Vergleich durch.

### <a name="stringindexof-and-stringlastindexof"></a>String.IndexOf und String.LastIndexOf

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Die Durchführung von Vergleichen durch die Standardüberladungen dieser Methoden ist nicht konsistent. Alle [String](xref:System.String)`IndexOf`- und [String](xref:System.String)`LastIndexOf`-Methoden mit einem [Char](xref:System.Char)-Parameter führen einen Ordinalvergleich durch. Die [String](xref:System.String)`IndexOf`- und die [String`](xref:System.String) `LastIndexOf`-Methode mit einem [String](xref:System.String)-Parameter führen dagegen einen kulturabhängigen Vergleich durch. 

Wenn Sie die ` `IndexOf-` or `LastIndexOf`-Methode aufrufen und eine Zeichenfolge übergeben, die in der aktuellen Instanz gesucht werden soll, empfiehlt es sich, eine Überladung aufrufen, die den [StringComparison](xref:System.StringComparison)-Typ explizit angibt. Mit den Überladungen, die ein [Char](xref:System.Char)-Argument enthalten, können Sie keinen [StringComparison](xref:System.StringComparison)-Typ angeben.

## <a name="methods-that-perform-string-comparison-indirectly"></a>Methoden für den indirekten Zeichenfolgenvergleich

Einige Methoden, die keine Zeichenfolgenmethoden darstellen, und deren zentrale Operation ein Zeichenfolgenvergleich ist, verwenden den [StringComparer](xref:System.StringComparer)-Typ. Die [StringComparer](xref:System.StringComparer)-Klasse enthält vier statische Eigenschaften, die [StringComparer](xref:System.StringComparer)-Instanzen zurückgeben, deren `Compare`-Methoden folgende Arten von Zeichenfolgenvergleichen durchführen:

* Kulturabhängige Zeichenfolgenvergleiche mit der aktuellen Kultur. Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture)-Eigenschaft zurückgegeben.

* Vergleiche mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung. Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase)-Eigenschaft zurückgegeben.

* Ordinalvergleich. Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.Ordinal](xref:System.StringComparer.Ordinal)-Eigenschaft zurückgegeben. 

* Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung. Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)-Eigenschaft zurückgegeben.

### <a name="arraysort-and-arraybinarysearch"></a>Array.Sort und Array.BinarySearch

Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Wenn Sie Daten in einer Auflistung speichern oder beibehaltene Daten aus einer Datei oder einer Datenbank in eine Auflistung lesen, können die Invarianten in der Auflistung durch einen Wechsel der aktuellen Kultur ungültig werden. Die [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object))-Methode geht davon aus, dass die Elemente im zu durchsuchenden Array bereits sortiert wurden. Um die einzelnen Zeichenfolgenelemente im Array zu sortieren, ruft die [Array.Sort](xref:System.Array.Sort(System.Array))-Methode die String.`Compare`-Methode auf. Kulturabhängige Vergleich bergen ein gewisses Risiko, falls sich die Kultur zwischen dem Zeitpunkt der Sortierung des Arrays und dem Durchsuchen des Inhalts ändert. Im folgenden Code wird das Speichern und Abrufen beispielsweise für den Comparer ausgeführt, der implizit von der `Thread.CurrentThread.CurrentCulture`-Eigenschaft bereitgestellt wird. Wenn sich die Kultur zwischen dem Aufruf von `StoreNames` und dem Aufruf von `DoesNameExist` möglicherweise ändert, kann bei der binären Suche ein Fehler auftreten; dies gilt insbesondere, wenn der Arrayinhalt zwischen den beiden Methodenaufrufen beibehalten wird. 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

Eine empfohlene Variante wird im folgenden Beispiel angezeigt, in dem die gleiche (kulturunabhängige) Ordinalvergleichsmethode verwendet wird, um das Array zu sortieren und zu durchsuchen. Der Änderungscode wird in den zwei Beispielen in den Zeilen mit der Bezeichnung `Line A` und `Line B` angezeigt.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

Wenn diese Daten beibehalten und zwischen Kulturen verschoben werden, und wenn eine Sortierung verwendet wird, um die Daten für den Benutzer anzuzeigen, können Sie `StringComparison.InvariantCulture` verwenden, da durch die linguistische Verarbeitung eine bessere Benutzerausgabe erzielt wird und Änderungen der Kultur keine Auswirkungen haben. Im folgenden Beispiel werden die zwei vorherigen Beispiele geändert, um die invariante Kultur zum Sortieren und Durchsuchen des Arrays zu verwenden.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a>Beispiel für Auflistungen: Hashtable-Konstruktor

Auch beim Hashen von Zeichenfolgen können sich, je nachdem, wie die Zeichenfolgen verglichen werden, Auswirkungen auf die Operation ergeben. 

Im folgenden Beispiel wird ein [Hashtable](xref:System.Collections.Hashtable)-Objekt durch Übergabe des [StringComparer](xref:System.StringComparer)-Objekts instanziiert, das von der [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)-Eigenschaft zurückgegeben wird. Da eine Klasse [StringComparer](xref:System.StringComparer), die von [StringComparer](xref:System.StringComparer) abgeleitet wird, die [IEqualityComparer](xref:System.Collections.IEqualityComparer)-Schnittstelle implementiert, wird die [GetHashCode](xref:System.Collections.IEqualityComparer)-Methode verwendet, um den Hashcode von Zeichenfolgen in der Hashtabelle zu berechnen.

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a>Anzeigen und Beibehalten von formatierten Daten

Wenn Sie Benutzern Daten anzeigen, die keine Zeichenfolge sind, z. B. Zahlen sowie Datumsangaben und Zeitangaben, formatieren Sie diese den Kultureinstellungen des Benutzers entsprechend. Standardmäßig verwenden die [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode und die `ToString`-Methoden der numerischen Typen und der Datums- und Uhrzeittypen die aktuelle Threadkultur für Formatierungsvorgänge. Um explizit anzugeben, dass die Formatierungsmethode die aktuelle Kultur verwenden soll, können Sie eine Überladung einer Formatierungsmethode mit einem Provider-Parameter aufrufen, wie z.B. [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) oder [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), und ihr die [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture)-Eigenschaft übergeben. 

Sie können Daten, die keine Zeichenfolge sind, entweder als Binärdaten oder als formatierte Daten beibehalten. Wenn Sie möchten, dass sie als formatierte Daten gespeichert werden, sollten Sie eine Überladung einer Formatierungsmethode aufrufen, die einen *Provider*-Parameter einschließt, und ihr die [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft übergeben. Die invariante Kultur stellt ein konsistentes Format für formatierte Daten bereit, das unabhängig von der Kultur und dem Computers ist. Im Gegensatz dazu bringt das Beibehalten von Daten, die mit anderen Kulturen als der invarianten Kultur formatiert werden, einige Einschränkungen mit sich: 

* Die Daten sind wahrscheinlich unbrauchbar, wenn sie auf einem System mit einer andere Kultur abgerufen werden oder wenn der Benutzer des aktuellen Systems die aktuelle Kultur ändert und versucht, die Daten abzurufen. 

* Die Eigenschaften einer Kultur auf einem bestimmten Computer können von den Standardwerten abweichen. Ein Benutzer kann kulturabhängige Anzeigeeinstellungen jederzeit anpassen. Aufgrund dessen können formatierte Daten, die in einem System gespeichert sind, möglicherweise nicht mehr gelesen werden, wenn der Benutzer die Kultureinstellungen anpasst. Die computerübergreifende Portabilität von formatierten Daten wird wahrscheinlich sogar noch eingeschränkter. 

* Internationale, regionale oder nationale Standards, die die Formatierung von Zahlen oder Datumsangaben und Uhrzeiten regeln, ändern sich mit der Zeit, und diese Änderungen werden in Betriebssystemupdates integriert. Wenn sich die Formatierungskonventionen ändern, können Daten, die anhand früherer Konventionen formatiert wurden, möglicherweise nicht mehr gelesen werden. 

Das folgende Beispiel veranschaulicht die eingeschränkte Portabilität, die sich aus der Verwendung von kulturabhängiger Formatierung zum Beibehalten von Daten ergibt. In dem Beispiel wird ein Array von Daten- und Uhrzeitwerten in einer Datei gespeichert. Diese werden anhand der Konventionen der Kultur Englisch (USA) formatiert. Nachdem die aktuelle Threadkultur der Anwendung in Französisch (Schweiz) geändert wird, versucht die Anwendung, die gespeicherten Werte mithilfe der Formatierungskonventionen der aktuellen Kultur zu lesen. Der Versuch, zwei der Datenelemente zu lesen, löst eine [FormatException](xref:System.FormatException)-Ausnahme aus, und das Array von Datumsangaben enthält nun zwei falsche Elemente, die [MinValue](xref:System.DateTime.MinValue) entsprechen. 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

Wenn Sie jedoch die [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture)-Eigenschaft in den Aufrufen von [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) und [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)) durch [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) ersetzen, werden die beibehaltenen Datums- und Uhrzeitdaten erfolgreich wiederhergestellt, wie die folgende Ausgabe zeigt.

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Zeichenfolgen](manipulating-strings.md)



<!--HONumber=Jan17_HO3-->


