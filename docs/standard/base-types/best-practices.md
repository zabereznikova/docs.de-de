---
title: "Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken"
description: "Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: d92549bf46f1c7a728bc6e2ac7cb183251115084

---

# <a name="best-practices-for-regular-expressions"></a>Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken

Das Modul für reguläre Ausdrücke in .NET ist ein leistungsstarkes Tool mit vollem Funktionsumfang, das Texte auf Grundlage von Musterübereinstimmungen verarbeitet, anstatt Literaltext zu vergleichen und nach Übereinstimmungen mit diesem zu suchen. In den meisten Fällen wird die Suche nach Musterabgleichen schnell und effizient ausgeführt. Gelegentlich kann das Modul für reguläre Ausdrücke jedoch sehr langsam wirken. In Extremfällen kann auch der Eindruck entstehen, dass das Modul nicht mehr reagiert, wenn für die Verarbeitung relativ kleiner Eingaben mehrere Stunden oder sogar Tage benötigt werden. 

In diesem Thema werden einige Best Practices erläutert, mit denen Entwickler sicherstellen können, dass ihre regulären Ausdrücke optimale Leistung erzielen. Es enthält die folgenden Abschnitte:

* [Bedenken der Eingabequelle](#consider-the-input-source)

* [Angemessene Behandlung der Objektinstanziierung](#handle-object-instantiation-appropriately)

* [Steuern der Rückverfolgung](#take-charge-of-backtracking)

* [Verwenden von Timeoutwerten](#use-time-out-values)

* [Erfassungen nur bei Bedarf](#capture-only-when-necessary)

* [Verwandte Themen](#related-topics)

## <a name="consider-the-input-source"></a>Bedenken der Eingabequelle

Im Allgemeinen können reguläre Ausdrücke zwei Arten von Eingaben annehmen: eingeschränkte und nicht eingeschränkte. Bei eingeschränkten Eingaben handelt es sich um Text, der aus einer bekannten oder verlässlichen Quelle stammt und einem vordefinierten Format folgt. Eine nicht eingeschränkte Eingabe ist Text, der aus einer unzuverlässigen Quelle stammt, z. B. von einem Webbenutzer, und keinem vordefinierten oder erwarteten Format folgt.

Muster regulärer Ausdrücke werden in der Regel für die Übereinstimmung mit gültigen Eingaben konzipiert. Das bedeutet, dass ein Entwickler den Text überprüft, mit dem eine Übereinstimmung erzielt werden soll, und anschließend ein entsprechendes Muster für reguläre Ausdrücke erstellt. Dann ermittelt der Entwickler, ob dieses Muster Korrekturen oder Ausarbeitungen erfordert, indem er es mit mehreren gültigen Eingabeelementen testet. Wenn das Muster mit allen als gültig geltenden Eingaben übereinstimmt, gilt es als einsatzbereit und kann in eine veröffentlichte Anwendung eingeschlossen werden. Somit ist das Muster für reguläre Ausdrücke geeignet für Übereinstimmungen mit eingeschränkten Eingaben. Allerdings ist es nicht geeignet für die Übereinstimmung mit nicht eingeschränkten Eingaben.

Für Übereinstimmungen mit nicht eingeschränkten Eingaben muss ein regulärer Ausdruck drei Arten von Text effizient verarbeiten können:

• Text, der mit dem Muster eines regulären Ausdrucks übereinstimmt.

• Text, der nicht mit dem Muster eines regulären Ausdrucks übereinstimmt.

• Text, der fast mit dem Muster eines regulären Ausdrucks übereinstimmt.

Der letzte Texttyp ist besonders problematisch für reguläre Ausdrücke, die für die Behandlung eingeschränkter Eingaben vorgesehen sind. Wenn ein solcher regulärer Ausdruck zudem auf umfangreicher [Rückverfolgung](backtracking.md) beruht, kann das Modul für reguläre Ausdrücke für die Verarbeitung von scheinbar harmlosem Text übermäßig lange Zeit brauchen (in manchen Fällen mehrere Stunden oder Tage). 

> [!WARNING]
> Im folgenden Beispiel wird ein regulärer Ausdruck verwendet, der für übermäßige Rückverfolgung anfällig ist und wahrscheinlich gültige E-Mail-Adressen zurückweisen wird. Er sollte nicht in einer E-Mail-Validierungsroutine nicht verwendet werden. Wenn Sie einen regulären Ausdruck zur Überprüfung von E-Mail-Adressen verwenden möchten, finden Sie entsprechende Informationen unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](verify-format.md). 


Als Beispiel dient hier ein sehr häufig verwendeter, jedoch äußerst problematischer regulärer Ausdruck zum Überprüfen des Alias einer E-Mail-Adresse. Der reguläre Ausdruck `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` wird konzipiert, um eine als gültig angenommene E-Mail-Adresse zu verarbeiten, die aus einem alphanumerischen Zeichen gefolgt von keinem oder weiteren Zeichen besteht, bei denen es sich um alphanumerische Zeichen, Punkte oder Bindestriche handeln kann. Der reguläre Ausdruck muss mit einem alphanumerischen Zeichen enden. Die Verarbeitung von gültigen Eingaben durch diesen regulären Ausdruck erfolgt zwar reibungslos, aber das folgende Beispiel zeigt, dass die Leistung bei der Verarbeitung von fast gültigen Eingaben sehr schlecht ist.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

Die Ausgabe im Beispiel zeigt, dass das Modul für reguläre Ausdrücke den gültigen E-Mail-Alias in etwa demselben Zeitintervall verarbeitet, unabhängig von dessen Länge. Wenn die fast gültige E-Mail-Adresse andererseits mehr als fünf Zeichen aufweist, wird die Verarbeitungszeit für jedes weitere Zeichen in der Zeichenfolge nahezu verdoppelt. Dies bedeutet, dass die Verarbeitung einer fast gültigen Zeichenfolge mit 28 Zeichen mehr als eine Stunde und die einer fast gültigen Zeichenfolge mit 33 Zeichen ungefähr einen Tag dauern würde. 

Da dieser reguläre Ausdruck ausschließlich im Hinblick auf das Format der Eingaben entwickelt wurde, für die eine Übereinstimmung gefunden werden sollte, werden Eingaben, die nicht mit dem Muster übereinstimmen, nicht berücksichtigt. Dies kann wiederum dazu führen, dass nicht eingeschränkte Eingaben, die fast mit dem Muster für reguläre Ausdrücke übereinstimmen, die Leistung erheblich beeinträchtigen.

Um dieses Problem zu beheben, können Sie wie folgt vorgehen:

* Beim Erstellen eines Musters sollten Sie berücksichtigen, wie sich das Zurückverfolgen auf die Leistung des Moduls für reguläre Ausdrücke auswirken könnte. Dies gilt insbesondere, wenn ein regulärer Ausdruck für die Verarbeitung nicht eingeschränkter Eingaben vorgesehen ist. Weitere Informationen finden Sie im Abschnitt [Steuern der Rückverfolgung](#take-charge-of-backtracking).

* Testen Sie den regulären Ausdruck sowohl mit ungültigen und fast gültigen Eingaben als auch mit gültigen Eingaben gründlich. Um Eingaben für einen bestimmten regulären Ausdruck zufällig zu generieren, können Sie [Rex](http://research.microsoft.com/en-us/projects/rex/) verwenden, ein Tool für das Untersuchen von regulären Ausdrücken von Microsoft Research.

## <a name="handle-object-instantiation-appropriately"></a>Angemessene Behandlung der Objektinstanziierung

Den Kern des .NET-Objektmodells für reguläre Ausdrücke bildet die [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Klasse, die das Modul für reguläre Ausdrücke darstellt. Häufig ist die einzige Hauptursache für Leistungsbeeinträchtigungen bei regulären Ausdrücken die Art, wie das [Regex](xref:System.Text.RegularExpressions.Regex)-Modul verwendet wird. Das Definieren eines regulären Ausdrucks beinhaltet das enge Verbinden des Moduls für reguläre Ausdrücke mit einem Muster für reguläre Ausdrücke. Hierzu wird ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt durch Übergeben des Konstruktors an ein reguläres Ausdrucksmuster instanziiert, oder eine statische Methode wird aufgerufen, indem das reguläre Ausdrucksmuster zusammen mit der zu analysierenden Zeichenfolge an sie übergeben wird. Somit ist dieser Verbindungsprozess zwangsläufig aufwändig.

Sie können das Modul für reguläre Ausdrücke mit einem bestimmten Muster für reguläre Ausdrücke verknüpfen und das Modul dann verwenden, um Textübereinstimmungen auf verschiedene Weise zu suchen:

* Sie können eine statische Methode für Musterübereinstimmungen aufrufen, z.B. [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)). Hierfür ist keine Instanziierung des Objekts eines regulären Ausdrucks erforderlich.

* Sie können ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines interpretierten regulären Ausdrucks aufrufen. Dies ist die Standardmethode zum Binden des Moduls für reguläre Ausdrücke an ein Muster für reguläre Ausdrücke. Sie ist das Resultat, wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt ohne Optionsargument instanziiert wird, das das [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Flag enthält.

* Sie können ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines kompilierten regulären Ausdrucks aufrufen. Objekte regulärer Ausdrücke stellen kompilierte Muster dar, wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt mit einem Optionsargument instanziiert wird, das das [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Flag enthält.

> [!IMPORTANT]
> Die Art des Methodenaufrufs (statisch, interpretiert, kompiliert) wirkt sich auf die Leistung aus, wenn ein regulärer Ausdruck wiederholt in Methodenaufrufen verwendet wird oder wenn eine Anwendung umfassenden Gebrauch von Objekten regulärer Ausdrücke macht.
 
### <a name="static-regular-expressions"></a>Statische reguläre Ausdrücke

Statische Methoden für reguläre Ausdrücke werden als Alternative zum wiederholten Instanziieren eines Objekts für reguläre Ausdrücke mit demselben regulären Ausdruck empfohlen. Im Gegensatz zu Mustern regulärer Ausdrücke, die von Objekten regulärer Ausdrücke verwendet werden, werden die Vorgangscodes oder die kompilierte Microsoft Intermediate Language (MSIL) von in Instanzmethoden aufgerufenen Mustern vom Modul für reguläre Ausdrücke intern zwischengespeichert. 

Beispielsweise könnten Sie eine Methode zum Überprüfen von Benutzereingaben aufrufen. In diesem Beispiel überprüft eine Methode mit dem Namen `IsValidCurrency`, ob der Benutzer ein Währungssymbol gefolgt von mindestens einer Dezimalziffer eingegeben hat. Eine sehr ineffiziente Implementierung der `IsValidCurrency`-Methode wird im folgenden Beispiel gezeigt. Beachten Sie, dass jeder Methodenaufruf ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt mit dem gleichen Muster erneut instanziiert. Dies bedeutet wiederum, dass das Muster für reguläre Ausdrücke bei jedem Aufruf der Methode erneut kompiliert werden muss.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

Sie sollten diesen ineffizienten Code durch einen Aufruf der statischen [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String))-Methode ersetzen. Dadurch entfällt die Notwendigkeit, jedes Mal ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt zu instanziieren, wenn Sie eine Methode für Musterübereinstimmungen aufrufen möchten. Außerdem kann das Modul für reguläre Ausdrücke eine kompilierte Version des regulären Ausdrucks aus dem Cache abrufen.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

Standardmäßig werden die letzten 15 zuletzt verwendeten statischen Muster für reguläre Ausdrücke zwischengespeichert. Für Anwendungen, die eine größere Anzahl von zwischengespeicherten statischen regulären Ausdrücken benötigen, kann die Größe des Caches durch Festlegen der [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize)-Eigenschaft angepasst werden.

Der in diesem Beispiel verwendete reguläre Ausdruck `\p{Sc}+\s*\d+` überprüft, ob die Eingabezeichenfolge ein Währungssymbol und mindestens eine Dezimalziffer enthält. Das Muster wird entsprechend der folgenden Tabelle definiert.

Muster | Beschreibung
------- | -----------
`\p{Sc}+` | Übereinstimmung mit mindestens einem Zeichen aus der Unicode-Kategorie Symbol, Währung.
`\s*` | Sucht nach 0 (null) oder mehr Leerzeichen.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
 
### <a name="interpreted-vs-compiled-regular-expressions"></a>Interpretierte im Vergleich zu kompilierten regulären Ausdrücken

Muster für reguläre Ausdrücke, die nicht durch Angabe der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option an das Modul für reguläre Ausdrücke gebunden sind, werden interpretiert. Wenn ein Objekt für reguläre Ausdrücke instanziiert wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck in einen Satz von Operationscodes. Beim Aufrufen einer Instanzmethode werden die Operationscodes in MSIL konvertiert und vom JIT-Compiler ausgeführt. Wenn eine statische Methode für reguläre Ausdrücke aufgerufen und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck ebenfalls in einen Satz von Operationscodes und speichert diese im Cache. Dann werden diese Operationscodes in MSIL konvertiert, damit der JIT-Compiler sie ausführen kann. Interpretierte reguläre Ausdrücke reduzieren die Ladezeit, führen aber zu einer langsameren Ausführungszeit. Ihre Verwendung empfiehlt sich daher vor allem dann, wenn der reguläre Ausdruck in einer kleinen Anzahl von Methodenaufrufen verwendet wird oder wenn die genaue Anzahl von Aufrufen der Methoden mit regulären Ausdrücken zwar unbekannt, jedoch erwartungsgemäß niedrig ist. Wenn die Anzahl der Methodenaufrufe zunimmt, wird die durch die kürzere Startzeit erzielte Leistungssteigerung durch die langsamere Ausführungsgeschwindigkeit wieder ausgeglichen.

Muster für reguläre Ausdrücke, die durch Angabe der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option an das Modul für reguläre Ausdrücke gebunden sind, werden kompiliert. Wenn also ein Objekt für reguläre Ausdrücke instanziiert oder eine statische Methode mit regulären Ausdrücken aufgerufen wird und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck in einen vorläufigen Satz von Operationscodes, der wiederum in MSIL konvertiert wird. Wenn eine Methode aufgerufen wird, führt der JIT-Compiler die MSIL aus. Im Gegensatz zu interpretierten regulären Ausdrücken erhöhen kompilierte reguläre Ausdrücke die Startzeit. Einzelne Methoden für Musterübereinstimmungen werden aber schneller ausgeführt. Dadurch vergrößert sich der Leistungsvorteil, der sich aus dem Kompilieren eines regulären Ausdrucks ergibt, relativ zur Anzahl der aufgerufenen Methoden für reguläre Ausdrücke.

Zusammenfassend wird empfohlen, interpretierte reguläre Ausdrücke dann zu verwenden, wenn Sie relativ selten Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen. Kompilierte reguläre Ausdrücke sollten Sie verwenden, wenn Sie relativ häufig Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen. Der genaue Schwellenwert, an dem die langsamere Ausführungsgeschwindigkeit interpretierter regulärer Ausdrücke die Vorteile der kürzen Startzeit aufhebt bzw. an dem die langsamere Startzeit kompilierter regulärer Ausdrücke die Vorteile der schnelleren Ausführungszeit aufhebt, ist schwer festzulegen. Diese Schwellenwerte hängen von verschiedenen Faktoren ab, z. B. der Komplexität des regulären Ausdrucks und den spezifischen verarbeiteten Daten. Um zu bestimmen, ob interpretierte oder kompilierte reguläre Ausdrücke die optimale Leistung für Ihr spezifisches Anwendungsszenario bieten, können Sie die [Stopwatch](xref:System.Diagnostics.Stopwatch)-Klasse verwenden, um die jeweiligen Ausführungszeiten zu vergleichen.

Im folgenden Beispiel wird die Leistung von kompilierten und interpretierten regulären Ausdrücken beim Lesen der ersten zehn Sätze und beim Lesen aller Sätze im Text „The Financier“ von Theodore Dreiser verglichen. Die Ausgabe im Beispiel zeigt: Wenn nur zehn Aufrufe von Methoden für Übereinstimmungen mit regulären Ausdrücken erfolgen, bietet ein interpretierter regulärer Ausdruck eine bessere Leistung als ein kompilierter regulärer Ausdruck. Ein kompilierter regulärer Ausdruck bietet jedoch die bessere Leistung bei vielen Aufrufen (in diesem Fall über 13.000). 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

Das im Beispiel verwendete Muster für reguläre Ausdrücke, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, wird entsprechend der folgenden Tabelle definiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`(\r?\n)|,?\s)` | Übereinstimmung mit entweder keinem oder einem Wagenrücklaufzeichen gefolgt von einem Zeilenumbruchzeichen oder mit keinem oder einem Komma gefolgt von einem Leerzeichen.
`(\w+((\r?\n)|,?\s))*` | Übereinstimmung mit keinem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gefolgt von entweder keinem oder einem Wagenrücklaufzeichen und einem Zeilenumbruchzeichen oder von keinem oder einem Komma gefolgt von einem Leerzeichen.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`[.?:;!]` | Übereinstimmung mit einem Punkt, Fragezeichen, Doppelpunkt, Semikolon oder Ausrufezeichen.
 
## <a name="take-charge-of-backtracking"></a>Steuern der Rückverfolgung

Normalerweise bewegt sich das Modul für reguläre Ausdrücke für den Vergleich mit einem regulären Ausdrucksmuster linear durch eine Eingabezeichenfolge. Wenn jedoch unbestimmte Quantifizierer, z.B. __*__, **+** und **?** in einem Muster für reguläre Ausdrücke verwendet werden, gibt das Modul für reguläre Ausdrücke möglicherweise einen Teil der erfolgreichen Teilübereinstimmungen auf und kehrt zu einem zuvor gespeicherten Zustand zurück, um nach einer erfolgreichen Übereinstimmung mit dem gesamten Muster zu suchen. Dieser Prozess wird als Rückverfolgung bezeichnet.

> [!NOTE]
> Weitere Informationen zur Rückverfolgung finden Sie unter [Einzelheiten zum Verhalten regulärer Ausdrücke](regex-behavior.md) und [Rückverfolgung in regulären Ausdrücken](backtracking.md).
 
Durch die Unterstützung des Zurückverfolgens werden reguläre Ausdrücke leistungsstark und flexibel. Außerdem wird die Steuerung der Ausführung des Moduls für reguläre Ausdrücke in die Hände der Entwickler von regulären Ausdrücken gelegt. Entwickler sind sich dieser Verantwortung oft nicht bewusst und verwenden die Rückverfolgung falsch oder übermäßig. Dies ist einer der Hauptfaktoren für die Beeinträchtigung der Leistung von regulären Ausdrücken. Im ungünstigsten Fall kann sich die Ausführungszeit für jedes zusätzliche Zeichen in der Eingabezeichenfolge verdoppeln. Durch Verwendung der Rückverfolgung ist es tatsächlich leicht, eine programmatische Entsprechung einer Endlosschleife zu erstellen, wenn die Eingabe fast mit dem Muster für reguläre Ausdrücke übereinstimmt. Für die Verarbeitung einer relativ kurzen Eingabezeichenfolge kann das Modul mehrere Stunden oder sogar Tage brauchen.

Leistungseinbußen bei Anwendungen kommen häufig vor, wenn die Rückverfolgung verwendet wird, obwohl diese für eine Übereinstimmung nicht erforderlich ist. Beispielsweise stimmt der reguläre Ausdruck `\b\p{Lu}\w*\b` mit allen Wörtern überein, die mit einem Großbuchstaben beginnen, wie in der folgenden Tabelle dargestellt.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\p{Lu}` | Übereinstimmung mit einem Großbuchstaben.
`\w*` | Übereinstimmung mit keinem oder mehreren Wortzeichen.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Da eine Wortgrenze weder mit einem Wortzeichen identisch noch eine Teilmenge eines Wortzeichens ist, ist es nicht möglich, dass das Modul für reguläre Ausdrücke beim Abgleichen von Wortzeichen eine Wortgrenze überschreitet. Das bedeutet, dass das Zurückverfolgen für diesen regulären Ausdruck nie zum Gesamterfolg von Übereinstimmungen beitragen kann – lediglich die Leistung kann beeinträchtigt werden, da das Modul für reguläre Ausdrücke gezwungen wird, den Zustand für jede erfolgreiche vorläufige Übereinstimmung eines Wortzeichens zu speichern.

Wenn Sie feststellen, dass das Zurückverfolgen nicht notwendig ist, können Sie es mithilfe des Sprachelements **(?>**_subexpression_**)** deaktivieren. Im folgenden Beispiel wird eine Eingabezeichenfolge unter Verwendung von zwei regulären Ausdrücken analysiert. Der erste, `\b\p{Lu}\w*\b`, beruht auf Rückverfolgung. Der zweite, `\b\p{Lu}(?>\w*)\b`, deaktiviert die Rückverfolgung. Wie die Ausgabe im Beispiel zeigt, liefern beide dasselbe Ergebnis.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

In vielen Fällen ist das Zurückverfolgen wichtig, um ein Muster für reguläre Ausdrücke mit dem Eingabetext abzugleichen. Eine übermäßige Rückverfolgung kann jedoch die Leistung erheblich beeinträchtigen und den Eindruck erwecken, dass eine Anwendung nicht mehr reagiert. Dies geschieht insbesondere dann, wenn Quantifizierer geschachtelt sind und der Text, der dem äußeren Teilausdruck entspricht, eine Teilmenge des Texts ist, der dem inneren Teilausdruck entspricht. 

> [!WARNING]
> Vermeiden Sie übermäßige Rückverfolgung, und verwenden Sie außerdem die Timeoutfunktion, um sicherzustellen, dass eine übermäßige Rückverfolgung die Leistung von regulären Ausdrücken nicht zu sehr beeinträchtigt. Weitere Informationen finden Sie im Abschnitt [Verwenden von Timeoutwerten](#use-time-out-values).
 
Beispielsweise soll das Muster für reguläre Ausdrücke `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` einer Teilenummer entsprechen, die aus mindestens einem alphanumerischen Zeichen besteht. Alle zusätzlichen Zeichen können aus einem alphanumerischen Zeichen, einem Bindestrich, einem Unterstrich oder einem Punkt bestehen. Das letzte Zeichen muss jedoch alphanumerisch sein. Ein Dollarzeichen beendet die Teilenummer. In einigen Fällen kann dieses Muster für reguläre Ausdrücke eine sehr schlechte Leistung aufweisen, da die Quantifizierer geschachtelt sind und der Teilausdruck `[0-9A-Z]` eine Teilmenge des Teilausdrucks `[-.\w]*` ist.

In diesen Fällen können Sie die Leistung regulärer Ausdrücke optimieren, indem Sie die geschachtelten Quantifizierer entfernen und den äußeren Teilausdruck durch eine Lookahead- oder Lookbehindassertion mit einer Breite von 0 ersetzen. Lookahead- und Lookbehindassertionen sind Anker, d. h., sie bewegen nicht den Mauszeiger in der Eingabezeichenfolge, sondern überprüfen in Vorwärts- bzw. Rückwärtsrichtung, ob eine bestimmte Bedingung erfüllt ist. Beispielsweise kann der reguläre Ausdruck für die Teilenummer wie folgt umgeschrieben werden: `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`. Dieses Muster für den regulären Ausdruck wird entsprechend der folgenden Tabelle definiert.

Muster | Beschreibung
------- | -----------
`^` | Beginnt den Vergleich am Anfang der Eingabezeichenfolge.
`[0-9A-Z]` | Übereinstimmung mit einem alphanumerischen Zeichen. Die Teilenummer muss aus mindestens diesem Zeichen bestehen.
`[-.\w]*` | Übereinstimmung mit keinem oder mehreren Vorkommen eines beliebigen Wortzeichens, eines Bindestrichs oder eines Punkts.
`\$] | Übereinstimmung mit einem Dollarzeichen.
`(?<=[0-9A-Z])` | Lookahead-Überprüfung am beendenden Dollarzeichen, um sicherzustellen, dass das vorherige Zeichen alphanumerisch ist.
`$` Ende des Abgleichs am Ende der Eingabezeichenfolge.
 
Im folgenden Beispiel wird die Verwendung dieses regulären Ausdrucks veranschaulicht, um ein Array abzugleichen, das mögliche Teilenummern enthält.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

Die Sprache für reguläre Ausdrücke in .NET beinhaltet die folgenden Sprachelemente, die Sie verwenden können, um geschachtelte Quantifizierer zu vermeiden. Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

Sprachelement | Beschreibung
---------------- | ----------- 
**(?**=_Teilausdruck_**)** | Positives Lookahead mit einer Breite von 0. Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* mit der Eingabezeichenfolge übereinstimmt.
**(?!**_Teilausdruck_**)** | Negatives Lookahead mit einer Breite von 0. Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* nicht mit der Eingabezeichenfolge übereinstimmt.
**(?<**=_Teilausdruck_**)** | Positives Lookbehind mit einer Breite von 0. Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* mit der Eingabezeichenfolge übereinstimmt.
**(?<!**_Teilausdruck_**)** | Negatives Lookbehind mit einer Breite von 0. Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* nicht mit der Eingabezeichenfolge übereinstimmt.
 
## <a name="use-time-out-values"></a>Verwenden von Timeoutwerten

Wenn Ihre regulären Ausdrücke Eingaben verarbeiten, die annähernd mit dem Muster des regulären Ausdrucks übereinstimmen, wird häufig übermäßige Rückverfolgung verwendet. Dies beeinträchtigt die Leistung signifikant. Sie sollten die Verwendung der Rückverfolgung sorgfältig abwägen und den regulären Ausdruck mit annähernd übereinstimmenden Eingaben testen. Legen Sie darüber hinaus einen Timeoutwert fest, um ggf. die Beeinträchtigung durch übermäßige Rückverfolgung zu minimieren.

Das Timeoutintervall des regulären Ausdrucks definiert den Zeitraum bis zum Timeout, für den das Modul für reguläre Ausdrücke nach einer einzelnen Übereinstimmung sucht. Das Standardtimeoutintervall ist [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout). Dies bedeutet, dass für den regulären Ausdruck kein Timeout erfolgt. Sie können diesen Wert folgendermaßen überschreiben und ein Timeoutintervall definieren: 

* Stellen Sie beim Instanziieren eines [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts einen Timeoutwert bereit, indem Sie den [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan))-Konstruktor aufrufen.

* Durch Aufrufen einer statischen Mustervergleichsmethode, z.B. [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) oder [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), die einen *matchTimeout*-Parameter enthält.

Wenn Sie ein Timeoutintervall definiert haben und am Ende dieses Intervalls keine Übereinstimmung gefunden wird, löst die Methode des regulären Ausdrucks eine [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException)-Ausnahme aus. In Ihrem Ausnahmehandler können Sie auswählen, dass erneut ein Abgleich mit einem längeren Timeoutintervall versucht wird, dass der Versuch abgebrochen und davon ausgegangen wird, dass keine Übereinstimmung vorhanden ist, oder dass der Versuch abgebrochen und die Ausnahmeinformationen für eine zukünftige Analyse protokolliert werden.

Im folgenden Beispiel wird eine `GetWordData`-Methode definiert, die einen regulären Ausdruck mit einem Timeoutintervall von 350 Millisekunden instanziiert, um für ein Textdokument die Anzahl der Wörter und die durchschnittliche Anzahl der Zeichen pro Wort zu berechnen. Wenn ein Timout für den entsprechenden Vorgang erfolgt, wird das Timeoutintervall um 350 Millisekunden erhöht und das [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt erneut instanziiert. Wenn das neue Timeoutintervall 1 Sekunde übersteigt, löst die Methode für den Aufrufer erneut eine Ausnahme aus.

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a>Erfassungen nur bei Bedarf

Reguläre Ausdrücke in .NET unterstützen eine Reihe von Gruppierungskonstrukten, mit denen Sie ein Muster für reguläre Ausdrücke in einen Teilausdruck oder in mehrere Teilausdrücke gruppieren können. Die am häufigsten verwendeten Gruppierungskonstrukte in der .NET-Sprache für reguläre Ausdrücke sind **(**_Teilausdruck_**)** zum Definieren einer nummerierten Erfassungsgruppe und **(?<*_Name_**>**_Teilausdruck_**)** zum Definieren einer benannten Erfassungsgruppe. Gruppierungskonstrukte sind wichtig für das Erstellen von Rückverweisen und für das Definieren eines Teilausdrucks, auf den ein Quantifizierer angewendet wird. 

Die Verwendung dieser Sprachelemente hat jedoch auch Nachteile. Sie führen dazu, dass das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegebene [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt mit den neuesten unbenannten oder benannten Erfassungen aufgefüllt wird. Wenn ein einzelnes Gruppierungskonstrukt mehrere Teilzeichenfolgen in der Eingabezeichenfolge erfasst hat, wird auch das von der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft einer bestimmten Erfassungsgruppe zurückgegebene [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt mit mehreren [Capture](xref:System.Text.RegularExpressions.Capture)-Objekten aufgefüllt.

Gruppierungskonstrukte werden häufig nur in einem regulären Ausdruck verwendet, damit Quantifizierer auf sie angewendet werden können. Die von diesen Teilausdrücken erfassten Gruppen werden später nicht verwendet. Beispielsweise soll der reguläre Ausdruck `\b(\w+[;,]?\s?)+[.?!]` einen vollständigen Satz erfassen. In der folgenden Tabelle werden die Sprachelemente in diesem regulären Ausdrucksmuster und ihre Auswirkungen auf die [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Auflistung und die [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Auflistung des [Match](xref:System.Text.RegularExpressions.Match)-Objekts beschrieben.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`[;,]?` | Übereinstimmung mit keinem oder einem Komma oder Semikolon.
`\s?` | Übereinstimmung mit keinem oder einem Leerzeichen.
`(\w+[;,]?\s?)+` | Übereinstimmung mit einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen, gefolgt von einem optionalen Komma oder Semikolon, gefolgt von einem optionalen Leerzeichen. Hiermit wird die erste Erfassungsgruppe definiert. Dies ist erforderlich, damit die Kombination mehrerer Wortzeichen (d. h. ein Wort) gefolgt von einem optionalen Interpunktionssymbol wiederholt wird, bis das Modul für reguläre Ausdrücke das Ende eines Satzes erreicht.
`[.?!]` | Übereinstimmung mit einem Punkt, Fragezeichen oder Ausrufezeichen.
 
Wie im folgenden Beispiel gezeigt, werden das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt und das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt mit Erfassungen aus der Übereinstimmungssuche aufgefüllt, wenn eine Übereinstimmung gefunden wird. In diesem Fall wird die Erfassungsgruppe `(\w+[;,]?\s?)` angegeben, damit der **+**-Quantifizierer darauf angewendet werden kann, wodurch das Muster für reguläre Ausdrücke Übereinstimmungen für jedes Wort in einem Satz erfassen kann. Andernfalls würde es mit dem letzten Wort in einem Satz abgeglichen werden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

Wenn Sie Teilausdrücke nur verwenden, um Quantifizierer darauf anzuwenden, und den erfassten Text nicht benötigen, sollten Sie Gruppenerfassungen deaktivieren. Zum Beispiel verhindert das Sprachelement **(?:**_Teilausdruck_**)**, dass die Gruppe, auf die es angewendet wird, übereinstimmende Teilzeichenfolgen erfasst. Im folgenden Beispiel wird das Muster eines regulären Ausdrucks aus dem vorherigen Beispiel in `\b(?:\w+[;,]?\s?)+[.?!]` geändert. Hiermit wird verhindert, dass das Modul für reguläre Ausdrücke die [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Auflistung und die [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Auflistung auffüllt, wie die Ausgabe im Beispiel zeigt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

Erfassungen können Sie auf eine der folgenden Arten deaktivieren:

* Verwenden des Sprachelements **(?:**_Teilausdruck_**)**. Dieses Element verhindert die Erfassung übereinstimmender Teilzeichenfolge in der Gruppe, auf die es angewendet wird. Die Erfassung von Teilzeichenfolgen in geschachtelten Gruppen wird nicht deaktiviert.

* Verwenden der Option [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture). Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen im Muster für reguläre Ausdrücke. Wenn Sie diese Option verwenden, können nur Teilzeichenfolgen erfasst werden, die mit benannten Gruppen übereinstimmen, die mit dem Sprachelement **(?<**_Name_**>**_Teilausdruck_**)** definiert wurden. Das [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)-Flag kann dem Optionsparameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder dem Optionsparameter einer statischen [Regex](xref:System.Text.RegularExpressions.Regex)-Methode für Übereinstimmung übergeben werden.

* Verwenden Sie die **n**-Option im Sprachelement **(?imnsx)**. Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen ab dem Punkt im Muster für reguläre Ausdrücke, an dem das Element erscheint. Erfassungen werden entweder bis zum Ende des Musters oder so lange deaktiviert, bis die **(-n)**-Option unbenannte oder implizite Erfassungen aktiviert. Weitere Informationen finden Sie unter [Verschiedene Konstrukte in regulären Ausdrücken](miscellaneous.md).

* Verwenden Sie die **n**-Option im Sprachelement **(?imnsx:**_subexpression_**)**. Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen in *Teilausdruck*. Erfassungen von allen unbenannten oder impliziten geschachtelten Erfassungsgruppen werden ebenfalls deaktiviert.

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | ----------- 
[Einzelheiten zum Verhalten regulärer Ausdrücke](regex-behavior.md) | Überprüft die Implementierung des Moduls für reguläre Ausdrücke in .NET. Schwerpunkt dieses Themas ist die Flexibilität regulärer Ausdrücke. Außerdem wird die Verantwortung des Entwicklers erläutert, das effiziente und stabile Ausführen des Moduls für reguläre Ausdrücke sicherzustellen.
[Backtracking in regulären Ausdrücken](backtracking.md) | Erläutert die Rückverfolgung und deren Auswirkungen auf die Leistung von regulären Ausdrücken. Zudem werden Sprachelemente beschrieben, die Alternativen zum Zurückverfolgen bieten.
[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md) | Beschreibt die Elemente der Sprache für reguläre Ausdrücke in .NET und enthält Links zu ausführlichen Dokumentationen für jedes Sprachelement.
 




<!--HONumber=Nov16_HO3-->


