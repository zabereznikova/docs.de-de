---
title: "Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken"
description: "Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cf9c83de791fa4990a991689a26d4bbdd84cfe7d
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="best-practices-for-regular-expressions"></a><span data-ttu-id="a6b69-104">Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a6b69-104">Best practices for regular expressions</span></span>

<span data-ttu-id="a6b69-105">Das Modul für reguläre Ausdrücke in .NET ist ein leistungsstarkes Tool mit vollem Funktionsumfang, das Texte auf Grundlage von Musterübereinstimmungen verarbeitet, anstatt Literaltext zu vergleichen und nach Übereinstimmungen mit diesem zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-105">The regular expression engine in .NET is a powerful, full-featured tool that processes text based on pattern matches rather than on comparing and matching literal text.</span></span> <span data-ttu-id="a6b69-106">In den meisten Fällen wird die Suche nach Musterabgleichen schnell und effizient ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-106">In most cases, it performs pattern matching rapidly and efficiently.</span></span> <span data-ttu-id="a6b69-107">Gelegentlich kann das Modul für reguläre Ausdrücke jedoch sehr langsam wirken.</span><span class="sxs-lookup"><span data-stu-id="a6b69-107">However, in some cases, the regular expression engine can appear to be very slow.</span></span> <span data-ttu-id="a6b69-108">In Extremfällen kann auch der Eindruck entstehen, dass das Modul nicht mehr reagiert, wenn für die Verarbeitung relativ kleiner Eingaben mehrere Stunden oder sogar Tage benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-108">In extreme cases, it can even appear to stop responding as it processes a relatively small input over the course of hours or even days.</span></span> 

<span data-ttu-id="a6b69-109">In diesem Thema werden einige Best Practices erläutert, mit denen Entwickler sicherstellen können, dass ihre regulären Ausdrücke optimale Leistung erzielen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-109">This topic outlines some of the best practices that developers can adopt to ensure that their regular expressions achieve optimal performance.</span></span> <span data-ttu-id="a6b69-110">Es enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="a6b69-110">It contains the following sections:</span></span>

* [<span data-ttu-id="a6b69-111">Bedenken der Eingabequelle</span><span class="sxs-lookup"><span data-stu-id="a6b69-111">Consider the input source</span></span>](#consider-the-input-source)

* [<span data-ttu-id="a6b69-112">Angemessene Behandlung der Objektinstanziierung</span><span class="sxs-lookup"><span data-stu-id="a6b69-112">Handle object instantiation appropriately</span></span>](#handle-object-instantiation-appropriately)

* [<span data-ttu-id="a6b69-113">Steuern der Rückverfolgung</span><span class="sxs-lookup"><span data-stu-id="a6b69-113">Take charge of backtracking</span></span>](#take-charge-of-backtracking)

* [<span data-ttu-id="a6b69-114">Verwenden von Timeoutwerten</span><span class="sxs-lookup"><span data-stu-id="a6b69-114">Use time-out values</span></span>](#use-time-out-values)

* [<span data-ttu-id="a6b69-115">Erfassungen nur bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="a6b69-115">Capture only when necessary</span></span>](#capture-only-when-necessary)

* [<span data-ttu-id="a6b69-116">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a6b69-116">Related topics</span></span>](#related-topics)

## <a name="consider-the-input-source"></a><span data-ttu-id="a6b69-117">Bedenken der Eingabequelle</span><span class="sxs-lookup"><span data-stu-id="a6b69-117">Consider the input source</span></span>

<span data-ttu-id="a6b69-118">Im Allgemeinen können reguläre Ausdrücke zwei Arten von Eingaben annehmen: eingeschränkte und nicht eingeschränkte.</span><span class="sxs-lookup"><span data-stu-id="a6b69-118">In general, regular expressions can accept two types of input: constrained or unconstrained.</span></span> <span data-ttu-id="a6b69-119">Bei eingeschränkten Eingaben handelt es sich um Text, der aus einer bekannten oder verlässlichen Quelle stammt und einem vordefinierten Format folgt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-119">Constrained input is text that originates from a known or reliable source and follows a predefined format.</span></span> <span data-ttu-id="a6b69-120">Eine nicht eingeschränkte Eingabe ist Text, der aus einer unzuverlässigen Quelle stammt, z. B. von einem Webbenutzer, und keinem vordefinierten oder erwarteten Format folgt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-120">Unconstrained input is text that originates from an unreliable source, such as a web user, and may not follow a predefined or expected format.</span></span>

<span data-ttu-id="a6b69-121">Muster regulärer Ausdrücke werden in der Regel für die Übereinstimmung mit gültigen Eingaben konzipiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-121">Regular expression patterns are typically written to match valid input.</span></span> <span data-ttu-id="a6b69-122">Das bedeutet, dass ein Entwickler den Text überprüft, mit dem eine Übereinstimmung erzielt werden soll, und anschließend ein entsprechendes Muster für reguläre Ausdrücke erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-122">That is, developers examine the text that they want to match and then write a regular expression pattern that matches it.</span></span> <span data-ttu-id="a6b69-123">Dann ermittelt der Entwickler, ob dieses Muster Korrekturen oder Ausarbeitungen erfordert, indem er es mit mehreren gültigen Eingabeelementen testet.</span><span class="sxs-lookup"><span data-stu-id="a6b69-123">Developers then determine whether this pattern requires correction or further elaboration by testing it with multiple valid input items.</span></span> <span data-ttu-id="a6b69-124">Wenn das Muster mit allen als gültig geltenden Eingaben übereinstimmt, gilt es als einsatzbereit und kann in eine veröffentlichte Anwendung eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-124">When the pattern matches all presumed valid inputs, it is declared to be production-ready and can be included in a released application.</span></span> <span data-ttu-id="a6b69-125">Somit ist das Muster für reguläre Ausdrücke geeignet für Übereinstimmungen mit eingeschränkten Eingaben.</span><span class="sxs-lookup"><span data-stu-id="a6b69-125">This makes a regular expression pattern suitable for matching constrained input.</span></span> <span data-ttu-id="a6b69-126">Allerdings ist es nicht geeignet für die Übereinstimmung mit nicht eingeschränkten Eingaben.</span><span class="sxs-lookup"><span data-stu-id="a6b69-126">However, it does not make it suitable for matching unconstrained input.</span></span>

<span data-ttu-id="a6b69-127">Für Übereinstimmungen mit nicht eingeschränkten Eingaben muss ein regulärer Ausdruck drei Arten von Text effizient verarbeiten können:</span><span class="sxs-lookup"><span data-stu-id="a6b69-127">To match unconstrained input, a regular expression must be able to efficiently handle three kinds of text:</span></span>

<span data-ttu-id="a6b69-128">• Text, der mit dem Muster eines regulären Ausdrucks übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-128">• Text that matches the regular expression pattern.</span></span>

<span data-ttu-id="a6b69-129">• Text, der nicht mit dem Muster eines regulären Ausdrucks übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-129">• Text that does not match the regular expression pattern.</span></span>

<span data-ttu-id="a6b69-130">• Text, der fast mit dem Muster eines regulären Ausdrucks übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-130">• Text that nearly matches the regular expression pattern.</span></span>

<span data-ttu-id="a6b69-131">Der letzte Texttyp ist besonders problematisch für reguläre Ausdrücke, die für die Behandlung eingeschränkter Eingaben vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="a6b69-131">The last text type is especially problematic for a regular expression that has been written to handle constrained input.</span></span> <span data-ttu-id="a6b69-132">Wenn ein solcher regulärer Ausdruck zudem auf umfangreicher [Rückverfolgung](backtracking.md) beruht, kann das Modul für reguläre Ausdrücke für die Verarbeitung von scheinbar harmlosem Text übermäßig lange Zeit brauchen (in manchen Fällen mehrere Stunden oder Tage).</span><span class="sxs-lookup"><span data-stu-id="a6b69-132">If that regular expression also relies on extensive [backtracking](backtracking.md), the regular expression engine can spend an inordinate amount of time (in some cases, many hours or days) processing seemingly innocuous text.</span></span> 

> [!WARNING]
> <span data-ttu-id="a6b69-133">Im folgenden Beispiel wird ein regulärer Ausdruck verwendet, der für übermäßige Rückverfolgung anfällig ist und wahrscheinlich gültige E-Mail-Adressen zurückweisen wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-133">The following example uses a regular expression that is prone to excessive backtracking and that is likely to reject valid email addresses.</span></span> <span data-ttu-id="a6b69-134">Er sollte nicht in einer E-Mail-Validierungsroutine nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-134">You should not use it in an email validation routine.</span></span> <span data-ttu-id="a6b69-135">Wenn Sie einen regulären Ausdruck zur Überprüfung von E-Mail-Adressen verwenden möchten, finden Sie entsprechende Informationen unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="a6b69-135">If you would like a regular expression that validates email addresses, see [How to: Verify that strings are in valid email format](verify-format.md).</span></span> 


<span data-ttu-id="a6b69-136">Als Beispiel dient hier ein sehr häufig verwendeter, jedoch äußerst problematischer regulärer Ausdruck zum Überprüfen des Alias einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="a6b69-136">For example, consider a very commonly used but extremely problematic regular expression for validating the alias of an email address.</span></span> <span data-ttu-id="a6b69-137">Der reguläre Ausdruck `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` wird konzipiert, um eine als gültig angenommene E-Mail-Adresse zu verarbeiten, die aus einem alphanumerischen Zeichen gefolgt von keinem oder weiteren Zeichen besteht, bei denen es sich um alphanumerische Zeichen, Punkte oder Bindestriche handeln kann.</span><span class="sxs-lookup"><span data-stu-id="a6b69-137">The regular expression `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` is written to process what is considered to be a valid email address, which consists of an alphanumeric character, followed by zero or more characters that can be alphanumeric, periods, or hyphens.</span></span> <span data-ttu-id="a6b69-138">Der reguläre Ausdruck muss mit einem alphanumerischen Zeichen enden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-138">The regular expression must end with an alphanumeric character.</span></span> <span data-ttu-id="a6b69-139">Die Verarbeitung von gültigen Eingaben durch diesen regulären Ausdruck erfolgt zwar reibungslos, aber das folgende Beispiel zeigt, dass die Leistung bei der Verarbeitung von fast gültigen Eingaben sehr schlecht ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-139">However, as the following example shows, although this regular expression handles valid input easily, its performance is very inefficient when it is processing nearly valid input.</span></span>

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

<span data-ttu-id="a6b69-140">Die Ausgabe im Beispiel zeigt, dass das Modul für reguläre Ausdrücke den gültigen E-Mail-Alias in etwa demselben Zeitintervall verarbeitet, unabhängig von dessen Länge.</span><span class="sxs-lookup"><span data-stu-id="a6b69-140">As the output from the example shows, the regular expression engine processes the valid email alias in about the same time interval regardless of its length.</span></span> <span data-ttu-id="a6b69-141">Wenn die fast gültige E-Mail-Adresse andererseits mehr als fünf Zeichen aufweist, wird die Verarbeitungszeit für jedes weitere Zeichen in der Zeichenfolge nahezu verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-141">On the other hand, when the nearly valid email address has more than five characters, processing time approximately doubles for each additional character in the string.</span></span> <span data-ttu-id="a6b69-142">Dies bedeutet, dass die Verarbeitung einer fast gültigen Zeichenfolge mit 28 Zeichen mehr als eine Stunde und die einer fast gültigen Zeichenfolge mit 33 Zeichen ungefähr einen Tag dauern würde.</span><span class="sxs-lookup"><span data-stu-id="a6b69-142">This means that a nearly valid 28-character string would take over an hour to process, and a nearly valid 33-character string would take nearly a day to process.</span></span> 

<span data-ttu-id="a6b69-143">Da dieser reguläre Ausdruck ausschließlich im Hinblick auf das Format der Eingaben entwickelt wurde, für die eine Übereinstimmung gefunden werden sollte, werden Eingaben, die nicht mit dem Muster übereinstimmen, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-143">Because this regular expression was developed solely by considering the format of input to be matched, it fails to take account of input that does not match the pattern.</span></span> <span data-ttu-id="a6b69-144">Dies kann wiederum dazu führen, dass nicht eingeschränkte Eingaben, die fast mit dem Muster für reguläre Ausdrücke übereinstimmen, die Leistung erheblich beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-144">This, in turn, can allow unconstrained input that nearly matches the regular expression pattern to significantly degrade performance.</span></span>

<span data-ttu-id="a6b69-145">Um dieses Problem zu beheben, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="a6b69-145">To solve this problem, you can do the following:</span></span>

* <span data-ttu-id="a6b69-146">Beim Erstellen eines Musters sollten Sie berücksichtigen, wie sich das Zurückverfolgen auf die Leistung des Moduls für reguläre Ausdrücke auswirken könnte. Dies gilt insbesondere, wenn ein regulärer Ausdruck für die Verarbeitung nicht eingeschränkter Eingaben vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-146">When developing a pattern, you should consider how backtracking might affect the performance of the regular expression engine, particularly if your regular expression is designed to process unconstrained input.</span></span> <span data-ttu-id="a6b69-147">Weitere Informationen finden Sie im Abschnitt [Steuern der Rückverfolgung](#take-charge-of-backtracking).</span><span class="sxs-lookup"><span data-stu-id="a6b69-147">For more information, see the [Take charge of backtracking](#take-charge-of-backtracking) section.</span></span>

* <span data-ttu-id="a6b69-148">Testen Sie den regulären Ausdruck sowohl mit ungültigen und fast gültigen Eingaben als auch mit gültigen Eingaben gründlich.</span><span class="sxs-lookup"><span data-stu-id="a6b69-148">Thoroughly test your regular expression using invalid and near-valid input as well as valid input.</span></span> <span data-ttu-id="a6b69-149">Um Eingaben für einen bestimmten regulären Ausdruck zufällig zu generieren, können Sie [Rex](http://research.microsoft.com/en-us/projects/rex/) verwenden, ein Tool für das Untersuchen von regulären Ausdrücken von Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="a6b69-149">To generate input for a particular regular expression randomly, you can use [Rex](http://research.microsoft.com/en-us/projects/rex/), which is a regular expression exploration tool from Microsoft Research.</span></span>

## <a name="handle-object-instantiation-appropriately"></a><span data-ttu-id="a6b69-150">Angemessene Behandlung der Objektinstanziierung</span><span class="sxs-lookup"><span data-stu-id="a6b69-150">Handle object instantiation appropriately</span></span>

<span data-ttu-id="a6b69-151">Den Kern des .NET-Objektmodells für reguläre Ausdrücke bildet die [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Klasse, die das Modul für reguläre Ausdrücke darstellt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-151">At the heart of .NET’s regular expression object model is the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) class, which represents the regular expression engine.</span></span> <span data-ttu-id="a6b69-152">Häufig ist die einzige Hauptursache für Leistungsbeeinträchtigungen bei regulären Ausdrücken die Art, wie das [Regex](xref:System.Text.RegularExpressions.Regex)-Modul verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-152">Often, the single greatest factor that affects regular expression performance is the way in which the [Regex](xref:System.Text.RegularExpressions.Regex) engine is used.</span></span> <span data-ttu-id="a6b69-153">Das Definieren eines regulären Ausdrucks beinhaltet das enge Verbinden des Moduls für reguläre Ausdrücke mit einem Muster für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="a6b69-153">Defining a regular expression involves tightly coupling the regular expression engine with a regular expression pattern.</span></span> <span data-ttu-id="a6b69-154">Hierzu wird ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt durch Übergeben des Konstruktors an ein reguläres Ausdrucksmuster instanziiert, oder eine statische Methode wird aufgerufen, indem das reguläre Ausdrucksmuster zusammen mit der zu analysierenden Zeichenfolge an sie übergeben wird. Somit ist dieser Verbindungsprozess zwangsläufig aufwändig.</span><span class="sxs-lookup"><span data-stu-id="a6b69-154">That coupling process, whether it involves instantiating a [Regex](xref:System.Text.RegularExpressions.Regex) object by passing its constructor a regular expression pattern or calling a static method by passing it the regular expression pattern along with the string to be analyzed, is by necessity an expensive one.</span></span>

<span data-ttu-id="a6b69-155">Sie können das Modul für reguläre Ausdrücke mit einem bestimmten Muster für reguläre Ausdrücke verknüpfen und das Modul dann verwenden, um Textübereinstimmungen auf verschiedene Weise zu suchen:</span><span class="sxs-lookup"><span data-stu-id="a6b69-155">You can couple the regular expression engine with a particular regular expression pattern and then use the engine to match text in several ways:</span></span>

* <span data-ttu-id="a6b69-156">Sie können eine statische Methode für Musterübereinstimmungen aufrufen, z.B. [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="a6b69-156">You can call a static pattern-matching method, such as [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span></span> <span data-ttu-id="a6b69-157">Hierfür ist keine Instanziierung des Objekts eines regulären Ausdrucks erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a6b69-157">This does not require instantiation of a regular expression object.</span></span>

* <span data-ttu-id="a6b69-158">Sie können ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines interpretierten regulären Ausdrucks aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-158">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of an interpreted regular expression.</span></span> <span data-ttu-id="a6b69-159">Dies ist die Standardmethode zum Binden des Moduls für reguläre Ausdrücke an ein Muster für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="a6b69-159">This is the default method for binding the regular expression engine to a regular expression pattern.</span></span> <span data-ttu-id="a6b69-160">Sie ist das Resultat, wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt ohne Optionsargument instanziiert wird, das das [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Flag enthält.</span><span class="sxs-lookup"><span data-stu-id="a6b69-160">It results when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated without an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

* <span data-ttu-id="a6b69-161">Sie können ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines kompilierten regulären Ausdrucks aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-161">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of a compiled regular expression.</span></span> <span data-ttu-id="a6b69-162">Objekte regulärer Ausdrücke stellen kompilierte Muster dar, wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt mit einem Optionsargument instanziiert wird, das das [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Flag enthält.</span><span class="sxs-lookup"><span data-stu-id="a6b69-162">Regular expression objects represent compiled patterns when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated with an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6b69-163">Die Art des Methodenaufrufs (statisch, interpretiert, kompiliert) wirkt sich auf die Leistung aus, wenn ein regulärer Ausdruck wiederholt in Methodenaufrufen verwendet wird oder wenn eine Anwendung umfassenden Gebrauch von Objekten regulärer Ausdrücke macht.</span><span class="sxs-lookup"><span data-stu-id="a6b69-163">The form of the method call (static, interpreted, compiled) affects performance if the same regular expression is used repeatedly in method calls, or if an application makes extensive use of regular expression objects.</span></span>
 
### <a name="static-regular-expressions"></a><span data-ttu-id="a6b69-164">Statische reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="a6b69-164">Static regular expressions</span></span>

<span data-ttu-id="a6b69-165">Statische Methoden für reguläre Ausdrücke werden als Alternative zum wiederholten Instanziieren eines Objekts für reguläre Ausdrücke mit demselben regulären Ausdruck empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-165">Static regular expression methods are recommended as an alternative to repeatedly instantiating a regular expression object with the same regular expression.</span></span> <span data-ttu-id="a6b69-166">Im Gegensatz zu Mustern regulärer Ausdrücke, die von Objekten regulärer Ausdrücke verwendet werden, werden die Vorgangscodes oder die kompilierte Microsoft Intermediate Language (MSIL) von in Instanzmethoden aufgerufenen Mustern vom Modul für reguläre Ausdrücke intern zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-166">Unlike regular expression patterns used by regular expression objects, either the operation codes or the compiled Microsoft intermediate language (MSIL) from patterns used in instance method calls is cached internally by the regular expression engine.</span></span> 

<span data-ttu-id="a6b69-167">Beispielsweise könnten Sie eine Methode zum Überprüfen von Benutzereingaben aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-167">For example, you might call a method to validate user input.</span></span> <span data-ttu-id="a6b69-168">In diesem Beispiel überprüft eine Methode mit dem Namen `IsValidCurrency`, ob der Benutzer ein Währungssymbol gefolgt von mindestens einer Dezimalziffer eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a6b69-168">In this example, a method named `IsValidCurrency` checks whether the user has entered a currency symbol followed by at least one decimal digit.</span></span> <span data-ttu-id="a6b69-169">Eine sehr ineffiziente Implementierung der `IsValidCurrency`-Methode wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-169">A very inefficient implementation of the `IsValidCurrency` method is shown in the following example.</span></span> <span data-ttu-id="a6b69-170">Beachten Sie, dass jeder Methodenaufruf ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt mit dem gleichen Muster erneut instanziiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-170">Note that each method call reinstantiates a [Regex](xref:System.Text.RegularExpressions.Regex) object with the same pattern.</span></span> <span data-ttu-id="a6b69-171">Dies bedeutet wiederum, dass das Muster für reguläre Ausdrücke bei jedem Aufruf der Methode erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a6b69-171">This, in turn, means that the regular expression pattern must be recompiled each time the method is called.</span></span>

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

<span data-ttu-id="a6b69-172">Sie sollten diesen ineffizienten Code durch einen Aufruf der statischen [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String))-Methode ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-172">You should replace this inefficient code with a call to the static [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) method.</span></span> <span data-ttu-id="a6b69-173">Dadurch entfällt die Notwendigkeit, jedes Mal ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt zu instanziieren, wenn Sie eine Methode für Musterübereinstimmungen aufrufen möchten. Außerdem kann das Modul für reguläre Ausdrücke eine kompilierte Version des regulären Ausdrucks aus dem Cache abrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-173">This eliminates the need to instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object each time you want to call a pattern-matching method, and enables the regular expression engine to retrieve a compiled version of the regular expression from its cache.</span></span>

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

<span data-ttu-id="a6b69-174">Standardmäßig werden die letzten 15 zuletzt verwendeten statischen Muster für reguläre Ausdrücke zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-174">By default, the last 15 most recently used static regular expression patterns are cached.</span></span> <span data-ttu-id="a6b69-175">Für Anwendungen, die eine größere Anzahl von zwischengespeicherten statischen regulären Ausdrücken benötigen, kann die Größe des Caches durch Festlegen der [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize)-Eigenschaft angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-175">For applications that require a larger number of cached static regular expressions, the size of the cache can be adjusted by setting the [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) property.</span></span>

<span data-ttu-id="a6b69-176">Der in diesem Beispiel verwendete reguläre Ausdruck `\p{Sc}+\s*\d+` überprüft, ob die Eingabezeichenfolge ein Währungssymbol und mindestens eine Dezimalziffer enthält.</span><span class="sxs-lookup"><span data-stu-id="a6b69-176">The regular expression `\p{Sc}+\s*\d+` that is used in this example verifies that the input string consists of a currency symbol and at least one decimal digit.</span></span> <span data-ttu-id="a6b69-177">Das Muster wird entsprechend der folgenden Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-177">The pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="a6b69-178">Muster</span><span class="sxs-lookup"><span data-stu-id="a6b69-178">Pattern</span></span> | <span data-ttu-id="a6b69-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-179">Description</span></span>
------- | -----------
`\p{Sc}+` | <span data-ttu-id="a6b69-180">Übereinstimmung mit mindestens einem Zeichen aus der Unicode-Kategorie Symbol, Währung.</span><span class="sxs-lookup"><span data-stu-id="a6b69-180">Match one or more characters in the Unicode Symbol, Currency category.</span></span>
`\s*` | <span data-ttu-id="a6b69-181">Sucht nach&0; (null) oder mehr Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-181">Match zero or more white-space characters.</span></span>
`\d+` | <span data-ttu-id="a6b69-182">Entsprechung für mindestens eine Dezimalstelle finden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-182">Match one or more decimal digits.</span></span>
 
### <a name="interpreted-vs-compiled-regular-expressions"></a><span data-ttu-id="a6b69-183">Interpretierte im Vergleich zu kompilierten regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a6b69-183">Interpreted vs. compiled regular expressions</span></span>

<span data-ttu-id="a6b69-184">Muster für reguläre Ausdrücke, die nicht durch Angabe der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option an das Modul für reguläre Ausdrücke gebunden sind, werden interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-184">Regular expression patterns that are not bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are interpreted.</span></span> <span data-ttu-id="a6b69-185">Wenn ein Objekt für reguläre Ausdrücke instanziiert wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck in einen Satz von Operationscodes.</span><span class="sxs-lookup"><span data-stu-id="a6b69-185">When a regular expression object is instantiated, the regular expression engine converts the regular expression to a set of operation codes.</span></span> <span data-ttu-id="a6b69-186">Beim Aufrufen einer Instanzmethode werden die Operationscodes in MSIL konvertiert und vom JIT-Compiler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-186">When an instance method is called, the operation codes are converted to MSIL and executed by the JIT compiler.</span></span> <span data-ttu-id="a6b69-187">Wenn eine statische Methode für reguläre Ausdrücke aufgerufen und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck ebenfalls in einen Satz von Operationscodes und speichert diese im Cache.</span><span class="sxs-lookup"><span data-stu-id="a6b69-187">Similarly, when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to a set of operation codes and stores them in the cache.</span></span> <span data-ttu-id="a6b69-188">Dann werden diese Operationscodes in MSIL konvertiert, damit der JIT-Compiler sie ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="a6b69-188">It then converts these operation codes to MSIL so that the JIT compiler can execute them.</span></span> <span data-ttu-id="a6b69-189">Interpretierte reguläre Ausdrücke reduzieren die Ladezeit, führen aber zu einer langsameren Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="a6b69-189">Interpreted regular expressions reduce startup time at the cost of slower execution time.</span></span> <span data-ttu-id="a6b69-190">Ihre Verwendung empfiehlt sich daher vor allem dann, wenn der reguläre Ausdruck in einer kleinen Anzahl von Methodenaufrufen verwendet wird oder wenn die genaue Anzahl von Aufrufen der Methoden mit regulären Ausdrücken zwar unbekannt, jedoch erwartungsgemäß niedrig ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-190">Because of this, they are best used when the regular expression is used in a small number of method calls, or if the exact number of calls to regular expression methods is unknown but is expected to be small.</span></span> <span data-ttu-id="a6b69-191">Wenn die Anzahl der Methodenaufrufe zunimmt, wird die durch die kürzere Startzeit erzielte Leistungssteigerung durch die langsamere Ausführungsgeschwindigkeit wieder ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-191">As the number of method calls increases, the performance gain from reduced startup time is outstripped by the slower execution speed.</span></span>

<span data-ttu-id="a6b69-192">Muster für reguläre Ausdrücke, die durch Angabe der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option an das Modul für reguläre Ausdrücke gebunden sind, werden kompiliert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-192">Regular expression patterns that are bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are compiled.</span></span> <span data-ttu-id="a6b69-193">Wenn also ein Objekt für reguläre Ausdrücke instanziiert oder eine statische Methode mit regulären Ausdrücken aufgerufen wird und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert das Modul für reguläre Ausdrücke den regulären Ausdruck in einen vorläufigen Satz von Operationscodes, der wiederum in MSIL konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-193">This means that, when a regular expression object is instantiated, or when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to an intermediary set of operation codes, which it then converts to MSIL.</span></span> <span data-ttu-id="a6b69-194">Wenn eine Methode aufgerufen wird, führt der JIT-Compiler die MSIL aus.</span><span class="sxs-lookup"><span data-stu-id="a6b69-194">When a method is called, the JIT compiler executes the MSIL.</span></span> <span data-ttu-id="a6b69-195">Im Gegensatz zu interpretierten regulären Ausdrücken erhöhen kompilierte reguläre Ausdrücke die Startzeit. Einzelne Methoden für Musterübereinstimmungen werden aber schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-195">In contrast to interpreted regular expressions, compiled regular expressions increase startup time but execute individual pattern-matching methods faster.</span></span> <span data-ttu-id="a6b69-196">Dadurch vergrößert sich der Leistungsvorteil, der sich aus dem Kompilieren eines regulären Ausdrucks ergibt, relativ zur Anzahl der aufgerufenen Methoden für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="a6b69-196">As a result, the performance benefit that results from compiling the regular expression increases in proportion to the number of regular expression methods called.</span></span>

<span data-ttu-id="a6b69-197">Zusammenfassend wird empfohlen, interpretierte reguläre Ausdrücke dann zu verwenden, wenn Sie relativ selten Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-197">To summarize, we recommend that you use interpreted regular expressions when you call regular expression methods with a specific regular expression relatively infrequently.</span></span> <span data-ttu-id="a6b69-198">Kompilierte reguläre Ausdrücke sollten Sie verwenden, wenn Sie relativ häufig Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-198">You should use compiled regular expressions when you call regular expression methods with a specific regular expression relatively frequently.</span></span> <span data-ttu-id="a6b69-199">Der genaue Schwellenwert, an dem die langsamere Ausführungsgeschwindigkeit interpretierter regulärer Ausdrücke die Vorteile der kürzen Startzeit aufhebt bzw. an dem die langsamere Startzeit kompilierter regulärer Ausdrücke die Vorteile der schnelleren Ausführungszeit aufhebt, ist schwer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-199">The exact threshold at which the slower execution speeds of interpreted regular expressions outweigh gains from their reduced startup time, or the threshold at which the slower startup times of compiled regular expressions outweigh gains from their faster execution speeds, is difficult to determine.</span></span> <span data-ttu-id="a6b69-200">Diese Schwellenwerte hängen von verschiedenen Faktoren ab, z. B. der Komplexität des regulären Ausdrucks und den spezifischen verarbeiteten Daten.</span><span class="sxs-lookup"><span data-stu-id="a6b69-200">It depends on a variety of factors, including the complexity of the regular expression and the specific data that it processes.</span></span> <span data-ttu-id="a6b69-201">Um zu bestimmen, ob interpretierte oder kompilierte reguläre Ausdrücke die optimale Leistung für Ihr spezifisches Anwendungsszenario bieten, können Sie die [Stopwatch](xref:System.Diagnostics.Stopwatch)-Klasse verwenden, um die jeweiligen Ausführungszeiten zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-201">To determine whether interpreted or compiled regular expressions offer the best performance for your particular application scenario, you can use the [Stopwatch](xref:System.Diagnostics.Stopwatch) class to compare their execution times.</span></span>

<span data-ttu-id="a6b69-202">Im folgenden Beispiel wird die Leistung von kompilierten und interpretierten regulären Ausdrücken beim Lesen der ersten zehn Sätze und beim Lesen aller Sätze im Text „The Financier“ von Theodore Dreiser verglichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-202">The following example compares the performance of compiled and interpreted regular expressions when reading the first ten sentences and when reading all the sentences in the text of Theodore Dreiser's The Financier.</span></span> <span data-ttu-id="a6b69-203">Die Ausgabe im Beispiel zeigt: Wenn nur zehn Aufrufe von Methoden für Übereinstimmungen mit regulären Ausdrücken erfolgen, bietet ein interpretierter regulärer Ausdruck eine bessere Leistung als ein kompilierter regulärer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a6b69-203">As the output from the example shows, when only ten calls are made to regular expression matching methods, an interpreted regular expression offers better performance than a compiled regular expression.</span></span> <span data-ttu-id="a6b69-204">Ein kompilierter regulärer Ausdruck bietet jedoch die bessere Leistung bei vielen Aufrufen (in diesem Fall über 13.000).</span><span class="sxs-lookup"><span data-stu-id="a6b69-204">However, a compiled regular expression offers better performance when a large number of calls (in this case, over 13,000) are made.</span></span> 

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

<span data-ttu-id="a6b69-205">Das im Beispiel verwendete Muster für reguläre Ausdrücke, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, wird entsprechend der folgenden Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-205">The regular expression pattern used in the example, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, is defined as shown in the following table.</span></span>

<span data-ttu-id="a6b69-206">Muster</span><span class="sxs-lookup"><span data-stu-id="a6b69-206">Pattern</span></span> | <span data-ttu-id="a6b69-207">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-207">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="a6b69-208">Der Vergleich beginnt an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="a6b69-208">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="a6b69-209">Übereinstimmung mit mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-209">Match one or more word characters.</span></span>
<span data-ttu-id="a6b69-210">\`(\r?\n)</span><span class="sxs-lookup"><span data-stu-id="a6b69-210">\`(\r?\n)</span></span>|<span data-ttu-id="a6b69-211">,?\s)\`</span><span class="sxs-lookup"><span data-stu-id="a6b69-211">,?\s)\`</span></span> | <span data-ttu-id="a6b69-212">Übereinstimmung mit entweder keinem oder einem Wagenrücklaufzeichen gefolgt von einem Zeilenumbruchzeichen oder mit keinem oder einem Komma gefolgt von einem Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-212">Match either zero or one carriage return followed by a newline character, or zero or one comma followed by a white-space character.</span></span>
<span data-ttu-id="a6b69-213">\`(\w+((\r?\n)</span><span class="sxs-lookup"><span data-stu-id="a6b69-213">\`(\w+((\r?\n)</span></span>|<span data-ttu-id="a6b69-214">,?\s))*\`</span><span class="sxs-lookup"><span data-stu-id="a6b69-214">,?\s))*\`</span></span> | <span data-ttu-id="a6b69-215">Übereinstimmung mit keinem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gefolgt von entweder keinem oder einem Wagenrücklaufzeichen und einem Zeilenumbruchzeichen oder von keinem oder einem Komma gefolgt von einem Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-215">Match zero or more occurrences of one or more word characters that are followed either by zero or one carriage return and a newline character, or by zero or one comma followed by a white-space character.</span></span>
`\w+` | <span data-ttu-id="a6b69-216">Übereinstimmung mit mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-216">Match one or more word characters.</span></span>
`[.?:;!]` | <span data-ttu-id="a6b69-217">Übereinstimmung mit einem Punkt, Fragezeichen, Doppelpunkt, Semikolon oder Ausrufezeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-217">Match a period, question mark, colon, semicolon, or exclamation point.</span></span>
 
## <a name="take-charge-of-backtracking"></a><span data-ttu-id="a6b69-218">Steuern der Rückverfolgung</span><span class="sxs-lookup"><span data-stu-id="a6b69-218">Take charge of backtracking</span></span>

<span data-ttu-id="a6b69-219">Normalerweise bewegt sich das Modul für reguläre Ausdrücke für den Vergleich mit einem regulären Ausdrucksmuster linear durch eine Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6b69-219">Ordinarily, the regular expression engine uses linear progression to move through an input string and compare it to a regular expression pattern.</span></span> <span data-ttu-id="a6b69-220">Wenn jedoch unbestimmte Quantifizierer, z.B. __*__, **+** und **?**</span><span class="sxs-lookup"><span data-stu-id="a6b69-220">However, when indeterminate quantifiers such as __*__, **+**, and **?**</span></span> <span data-ttu-id="a6b69-221">in einem Muster für reguläre Ausdrücke verwendet werden, gibt das Modul für reguläre Ausdrücke möglicherweise einen Teil der erfolgreichen Teilübereinstimmungen auf und kehrt zu einem zuvor gespeicherten Zustand zurück, um nach einer erfolgreichen Übereinstimmung mit dem gesamten Muster zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-221">are used in a regular expression pattern, the regular expression engine may give up a portion of successful partial matches and return to a previously saved state in order to search for a successful match for the entire pattern.</span></span> <span data-ttu-id="a6b69-222">Dieser Prozess wird als Rückverfolgung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a6b69-222">This process is known as backtracking.</span></span>

> [!NOTE]
> <span data-ttu-id="a6b69-223">Weitere Informationen zur Rückverfolgung finden Sie unter [Einzelheiten zum Verhalten regulärer Ausdrücke](regex-behavior.md) und [Rückverfolgung in regulären Ausdrücken](backtracking.md).</span><span class="sxs-lookup"><span data-stu-id="a6b69-223">For more information on backtracking, see [Details of regular expression behavior](regex-behavior.md) and [Backtracking in regular expressions](backtracking.md).</span></span>
 
<span data-ttu-id="a6b69-224">Durch die Unterstützung des Zurückverfolgens werden reguläre Ausdrücke leistungsstark und flexibel.</span><span class="sxs-lookup"><span data-stu-id="a6b69-224">Support for backtracking gives regular expressions power and flexibility.</span></span> <span data-ttu-id="a6b69-225">Außerdem wird die Steuerung der Ausführung des Moduls für reguläre Ausdrücke in die Hände der Entwickler von regulären Ausdrücken gelegt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-225">It also places the responsibility for controlling the operation of the regular expression engine in the hands of regular expression developers.</span></span> <span data-ttu-id="a6b69-226">Entwickler sind sich dieser Verantwortung oft nicht bewusst und verwenden die Rückverfolgung falsch oder übermäßig. Dies ist einer der Hauptfaktoren für die Beeinträchtigung der Leistung von regulären Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="a6b69-226">Because developers are often not aware of this responsibility, their misuse of backtracking or reliance on excessive backtracking often plays the most significant role in degrading regular expression performance.</span></span> <span data-ttu-id="a6b69-227">Im ungünstigsten Fall kann sich die Ausführungszeit für jedes zusätzliche Zeichen in der Eingabezeichenfolge verdoppeln.</span><span class="sxs-lookup"><span data-stu-id="a6b69-227">In a worst-case scenario, execution time can double for each additional character in the input string.</span></span> <span data-ttu-id="a6b69-228">Durch Verwendung der Rückverfolgung ist es tatsächlich leicht, eine programmatische Entsprechung einer Endlosschleife zu erstellen, wenn die Eingabe fast mit dem Muster für reguläre Ausdrücke übereinstimmt. Für die Verarbeitung einer relativ kurzen Eingabezeichenfolge kann das Modul mehrere Stunden oder sogar Tage brauchen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-228">In fact, by using backtracking excessively, it is easy to create the programmatic equivalent of an endless loop if input nearly matches the regular expression pattern; the regular expression engine may take hours or even days to process a relatively short input string.</span></span>

<span data-ttu-id="a6b69-229">Leistungseinbußen bei Anwendungen kommen häufig vor, wenn die Rückverfolgung verwendet wird, obwohl diese für eine Übereinstimmung nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-229">Often, applications pay a performance penalty for using backtracking despite the fact that backtracking is not essential for a match.</span></span> <span data-ttu-id="a6b69-230">Beispielsweise stimmt der reguläre Ausdruck `\b\p{Lu}\w*\b` mit allen Wörtern überein, die mit einem Großbuchstaben beginnen, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-230">For example, the regular expression `\b\p{Lu}\w*\b` matches all words that begin with an uppercase character, as the following table shows.</span></span>

<span data-ttu-id="a6b69-231">Muster</span><span class="sxs-lookup"><span data-stu-id="a6b69-231">Pattern</span></span> | <span data-ttu-id="a6b69-232">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-232">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="a6b69-233">Der Vergleich beginnt an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="a6b69-233">Begin the match at a word boundary.</span></span>
`\p{Lu}` | <span data-ttu-id="a6b69-234">Übereinstimmung mit einem Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="a6b69-234">Match an uppercase character.</span></span>
`\w*` | <span data-ttu-id="a6b69-235">Übereinstimmung mit keinem oder mehreren Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-235">Match zero or more word characters.</span></span>
`\b` | <span data-ttu-id="a6b69-236">Der Vergleich endet an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="a6b69-236">End the match at a word boundary.</span></span>
 
<span data-ttu-id="a6b69-237">Da eine Wortgrenze weder mit einem Wortzeichen identisch noch eine Teilmenge eines Wortzeichens ist, ist es nicht möglich, dass das Modul für reguläre Ausdrücke beim Abgleichen von Wortzeichen eine Wortgrenze überschreitet.</span><span class="sxs-lookup"><span data-stu-id="a6b69-237">Because a word boundary is not the same as, or a subset of, a word character, there is no possibility that the regular expression engine will cross a word boundary when matching word characters.</span></span> <span data-ttu-id="a6b69-238">Das bedeutet, dass das Zurückverfolgen für diesen regulären Ausdruck nie zum Gesamterfolg von Übereinstimmungen beitragen kann – lediglich die Leistung kann beeinträchtigt werden, da das Modul für reguläre Ausdrücke gezwungen wird, den Zustand für jede erfolgreiche vorläufige Übereinstimmung eines Wortzeichens zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a6b69-238">This means that for this regular expression, backtracking can never contribute to the overall success of any match -- it can only degrade performance, because the regular expression engine is forced to save its state for each successful preliminary match of a word character.</span></span>

<span data-ttu-id="a6b69-239">Wenn Sie feststellen, dass das Zurückverfolgen nicht notwendig ist, können Sie es mithilfe des Sprachelements **(?>**_subexpression_**)** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6b69-239">If you determine that backtracking is not necessary, you can disable it by using the **(?>**_subexpression_**)** language element.</span></span> <span data-ttu-id="a6b69-240">Im folgenden Beispiel wird eine Eingabezeichenfolge unter Verwendung von zwei regulären Ausdrücken analysiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-240">The following example parses an input string by using two regular expressions.</span></span> <span data-ttu-id="a6b69-241">Der erste, `\b\p{Lu}\w*\b`, beruht auf Rückverfolgung.</span><span class="sxs-lookup"><span data-stu-id="a6b69-241">The first, `\b\p{Lu}\w*\b`, relies on backtracking.</span></span> <span data-ttu-id="a6b69-242">Der zweite, `\b\p{Lu}(?>\w*)\b`, deaktiviert die Rückverfolgung.</span><span class="sxs-lookup"><span data-stu-id="a6b69-242">The second, `\b\p{Lu}(?>\w*)\b`, disables backtracking.</span></span> <span data-ttu-id="a6b69-243">Wie die Ausgabe im Beispiel zeigt, liefern beide dasselbe Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="a6b69-243">As the output from the example shows, they both produce the same result.</span></span>

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

<span data-ttu-id="a6b69-244">In vielen Fällen ist das Zurückverfolgen wichtig, um ein Muster für reguläre Ausdrücke mit dem Eingabetext abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-244">In many cases, backtracking is essential for matching a regular expression pattern to input text.</span></span> <span data-ttu-id="a6b69-245">Eine übermäßige Rückverfolgung kann jedoch die Leistung erheblich beeinträchtigen und den Eindruck erwecken, dass eine Anwendung nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-245">However, excessive backtracking can severely degrade performance and create the impression that an application has stopped responding.</span></span> <span data-ttu-id="a6b69-246">Dies geschieht insbesondere dann, wenn Quantifizierer geschachtelt sind und der Text, der dem äußeren Teilausdruck entspricht, eine Teilmenge des Texts ist, der dem inneren Teilausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="a6b69-246">In particular, this happens when quantifiers are nested and the text that matches the outer subexpression is a subset of the text that matches the inner subexpression.</span></span> 

> [!WARNING]
> <span data-ttu-id="a6b69-247">Vermeiden Sie übermäßige Rückverfolgung, und verwenden Sie außerdem die Timeoutfunktion, um sicherzustellen, dass eine übermäßige Rückverfolgung die Leistung von regulären Ausdrücken nicht zu sehr beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-247">In addition to avoiding excessive backtracking, you should use the timeout feature to ensure that excessive backtracking does not severely degrade regular expression performance.</span></span> <span data-ttu-id="a6b69-248">Weitere Informationen finden Sie im Abschnitt [Verwenden von Timeoutwerten](#use-time-out-values).</span><span class="sxs-lookup"><span data-stu-id="a6b69-248">For more information, see the [Use time-out values](#use-time-out-values) section.</span></span>
 
<span data-ttu-id="a6b69-249">Beispielsweise soll das Muster für reguläre Ausdrücke `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` einer Teilenummer entsprechen, die aus mindestens einem alphanumerischen Zeichen besteht.</span><span class="sxs-lookup"><span data-stu-id="a6b69-249">For example, the regular expression pattern `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` is intended to match a part number that consists of at least one alphanumeric character.</span></span> <span data-ttu-id="a6b69-250">Alle zusätzlichen Zeichen können aus einem alphanumerischen Zeichen, einem Bindestrich, einem Unterstrich oder einem Punkt bestehen. Das letzte Zeichen muss jedoch alphanumerisch sein.</span><span class="sxs-lookup"><span data-stu-id="a6b69-250">Any additional characters can consist of an alphanumeric character, a hyphen, an underscore, or a period, though the last character must be alphanumeric.</span></span> <span data-ttu-id="a6b69-251">Ein Dollarzeichen beendet die Teilenummer.</span><span class="sxs-lookup"><span data-stu-id="a6b69-251">A dollar sign terminates the part number.</span></span> <span data-ttu-id="a6b69-252">In einigen Fällen kann dieses Muster für reguläre Ausdrücke eine sehr schlechte Leistung aufweisen, da die Quantifizierer geschachtelt sind und der Teilausdruck `[0-9A-Z]` eine Teilmenge des Teilausdrucks `[-.\w]*` ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-252">In some cases, this regular expression pattern can exhibit extremely poor performance because quantifiers are nested, and because the subexpression `[0-9A-Z]` is a subset of the subexpression `[-.\w]*`.</span></span>

<span data-ttu-id="a6b69-253">In diesen Fällen können Sie die Leistung regulärer Ausdrücke optimieren, indem Sie die geschachtelten Quantifizierer entfernen und den äußeren Teilausdruck durch eine Lookahead- oder Lookbehindassertion mit einer Breite von&0; ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-253">In these cases, you can optimize regular expression performance by removing the nested quantifiers and replacing the outer subexpression with a zero-width lookahead or lookbehind assertion.</span></span> <span data-ttu-id="a6b69-254">Lookahead- und Lookbehindassertionen sind Anker, d. h., sie bewegen nicht den Mauszeiger in der Eingabezeichenfolge, sondern überprüfen in Vorwärts- bzw. Rückwärtsrichtung, ob eine bestimmte Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-254">Lookahead and lookbehind assertions are anchors; they do not move the pointer in the input string, but instead look ahead or behind to check whether a specified condition is met.</span></span> <span data-ttu-id="a6b69-255">Beispielsweise kann der reguläre Ausdruck für die Teilenummer wie folgt umgeschrieben werden: `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span><span class="sxs-lookup"><span data-stu-id="a6b69-255">For example, the part number regular expression can be rewritten as `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span></span> <span data-ttu-id="a6b69-256">Dieses Muster für den regulären Ausdruck wird entsprechend der folgenden Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-256">This regular expression pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="a6b69-257">Muster</span><span class="sxs-lookup"><span data-stu-id="a6b69-257">Pattern</span></span> | <span data-ttu-id="a6b69-258">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-258">Description</span></span>
------- | -----------
`^` | <span data-ttu-id="a6b69-259">Beginnt den Vergleich am Anfang der Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6b69-259">Begin the match at the beginning of the input string.</span></span>
`[0-9A-Z]` | <span data-ttu-id="a6b69-260">Übereinstimmung mit einem alphanumerischen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-260">Match an alphanumeric character.</span></span> <span data-ttu-id="a6b69-261">Die Teilenummer muss aus mindestens diesem Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-261">The part number must consist of at least this character.</span></span>
`[-.\w]*` | <span data-ttu-id="a6b69-262">Übereinstimmung mit keinem oder mehreren Vorkommen eines beliebigen Wortzeichens, eines Bindestrichs oder eines Punkts.</span><span class="sxs-lookup"><span data-stu-id="a6b69-262">Match zero or more occurrences of any word character, hyphen, or period.</span></span>
<span data-ttu-id="a6b69-263">\`\$]</span><span class="sxs-lookup"><span data-stu-id="a6b69-263">\`\$]</span></span> | <span data-ttu-id="a6b69-264">Übereinstimmung mit einem Dollarzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-264">Match a dollar sign.</span></span>
`(?<=[0-9A-Z])` | <span data-ttu-id="a6b69-265">Lookahead-Überprüfung am beendenden Dollarzeichen, um sicherzustellen, dass das vorherige Zeichen alphanumerisch ist.</span><span class="sxs-lookup"><span data-stu-id="a6b69-265">Look ahead of the ending dollar sign to ensure that the previous character is alphanumeric.</span></span>
<span data-ttu-id="a6b69-266">`$` Ende des Abgleichs am Ende der Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6b69-266">`$` End the match at the end of the input string.</span></span>
 
<span data-ttu-id="a6b69-267">Im folgenden Beispiel wird die Verwendung dieses regulären Ausdrucks veranschaulicht, um ein Array abzugleichen, das mögliche Teilenummern enthält.</span><span class="sxs-lookup"><span data-stu-id="a6b69-267">The following example illustrates the use of this regular expression to match an array containing possible part numbers.</span></span>

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

<span data-ttu-id="a6b69-268">Die Sprache für reguläre Ausdrücke in .NET beinhaltet die folgenden Sprachelemente, die Sie verwenden können, um geschachtelte Quantifizierer zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-268">The regular expression language in .NET includes the following language elements that you can use to eliminate nested quantifiers.</span></span> <span data-ttu-id="a6b69-269">Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).</span><span class="sxs-lookup"><span data-stu-id="a6b69-269">For more information, see [Grouping constructs in regular expressions](grouping.md).</span></span>

<span data-ttu-id="a6b69-270">Sprachelement</span><span class="sxs-lookup"><span data-stu-id="a6b69-270">Language element</span></span> | <span data-ttu-id="a6b69-271">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-271">Description</span></span>
---------------- | ----------- 
<span data-ttu-id="a6b69-272">**(?**=_Teilausdruck_**)**</span><span class="sxs-lookup"><span data-stu-id="a6b69-272">**(?**=_subexpression_**)**</span></span> | <span data-ttu-id="a6b69-273">Positives Lookahead mit einer Breite von&0;.</span><span class="sxs-lookup"><span data-stu-id="a6b69-273">Zero-width positive lookahead.</span></span> <span data-ttu-id="a6b69-274">Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* mit der Eingabezeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-274">Look ahead of the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="a6b69-275">**(?!**_Teilausdruck_**)**</span><span class="sxs-lookup"><span data-stu-id="a6b69-275">**(?!**_subexpression_**)**</span></span> | <span data-ttu-id="a6b69-276">Negatives Lookahead mit einer Breite von&0;.</span><span class="sxs-lookup"><span data-stu-id="a6b69-276">Zero-width negative lookahead.</span></span> <span data-ttu-id="a6b69-277">Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* nicht mit der Eingabezeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-277">Look ahead of the current position to determine whether *subexpression* does not match the input string.</span></span>
<span data-ttu-id="a6b69-278">**(?<**=_Teilausdruck_**)**</span><span class="sxs-lookup"><span data-stu-id="a6b69-278">**(?<**=_subexpression_**)**</span></span> | <span data-ttu-id="a6b69-279">Positives Lookbehind mit einer Breite von&0;.</span><span class="sxs-lookup"><span data-stu-id="a6b69-279">Zero-width positive lookbehind.</span></span> <span data-ttu-id="a6b69-280">Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* mit der Eingabezeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-280">Look behind the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="a6b69-281">**(?<!**_Teilausdruck_**)**</span><span class="sxs-lookup"><span data-stu-id="a6b69-281">**(?<!**_subexpression_**)**</span></span> | <span data-ttu-id="a6b69-282">Negatives Lookbehind mit einer Breite von&0;.</span><span class="sxs-lookup"><span data-stu-id="a6b69-282">Zero-width negative lookbehind.</span></span> <span data-ttu-id="a6b69-283">Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob *Teilausdruck* nicht mit der Eingabezeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-283">Look behind the current position to determine whether *subexpression* does not match the input string.</span></span>
 
## <a name="use-time-out-values"></a><span data-ttu-id="a6b69-284">Verwenden von Timeoutwerten</span><span class="sxs-lookup"><span data-stu-id="a6b69-284">Use time-out values</span></span>

<span data-ttu-id="a6b69-285">Wenn Ihre regulären Ausdrücke Eingaben verarbeiten, die annähernd mit dem Muster des regulären Ausdrucks übereinstimmen, wird häufig übermäßige Rückverfolgung verwendet. Dies beeinträchtigt die Leistung signifikant.</span><span class="sxs-lookup"><span data-stu-id="a6b69-285">If your regular expressions processes input that nearly matches the regular expression pattern, it can often rely on excessive backtracking, which impacts its performance significantly.</span></span> <span data-ttu-id="a6b69-286">Sie sollten die Verwendung der Rückverfolgung sorgfältig abwägen und den regulären Ausdruck mit annähernd übereinstimmenden Eingaben testen. Legen Sie darüber hinaus einen Timeoutwert fest, um ggf. die Beeinträchtigung durch übermäßige Rückverfolgung zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="a6b69-286">In addition to carefully considering your use of backtracking and testing the regular expression against near-matching input, you should always set a time-out value to ensure that the impact of excessive backtracking, if it occurs, is minimized.</span></span>

<span data-ttu-id="a6b69-287">Das Timeoutintervall des regulären Ausdrucks definiert den Zeitraum bis zum Timeout, für den das Modul für reguläre Ausdrücke nach einer einzelnen Übereinstimmung sucht.</span><span class="sxs-lookup"><span data-stu-id="a6b69-287">The regular expression time-out interval defines the period of time that the regular expression engine will look for a single match before it times out.</span></span> <span data-ttu-id="a6b69-288">Das Standardtimeoutintervall ist [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout). Dies bedeutet, dass für den regulären Ausdruck kein Timeout erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-288">The default time-out interval is [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), which means that the regular expression will not time out.</span></span> <span data-ttu-id="a6b69-289">Sie können diesen Wert folgendermaßen überschreiben und ein Timeoutintervall definieren:</span><span class="sxs-lookup"><span data-stu-id="a6b69-289">You can override this value and define a time-out interval as follows:</span></span> 

* <span data-ttu-id="a6b69-290">Stellen Sie beim Instanziieren eines [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts einen Timeoutwert bereit, indem Sie den [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan))-Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-290">By providing a time-out value when you instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object by calling the [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) constructor.</span></span>

* <span data-ttu-id="a6b69-291">Durch Aufrufen einer statischen Mustervergleichsmethode, z.B. [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) oder [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), die einen *matchTimeout*-Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="a6b69-291">By calling a static pattern matching method, such as [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) or [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), that includes a *matchTimeout* parameter.</span></span>

<span data-ttu-id="a6b69-292">Wenn Sie ein Timeoutintervall definiert haben und am Ende dieses Intervalls keine Übereinstimmung gefunden wird, löst die Methode des regulären Ausdrucks eine [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException)-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a6b69-292">If you have defined a time-out interval and a match is not found at the end of that interval, the regular expression method throws a [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) exception.</span></span> <span data-ttu-id="a6b69-293">In Ihrem Ausnahmehandler können Sie auswählen, dass erneut ein Abgleich mit einem längeren Timeoutintervall versucht wird, dass der Versuch abgebrochen und davon ausgegangen wird, dass keine Übereinstimmung vorhanden ist, oder dass der Versuch abgebrochen und die Ausnahmeinformationen für eine zukünftige Analyse protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-293">In your exception handler, you can choose to retry the match with a longer time-out interval, abandon the match attempt and assume that there is no match, or abandon the match attempt and log the exception information for future analysis.</span></span>

<span data-ttu-id="a6b69-294">Im folgenden Beispiel wird eine `GetWordData`-Methode definiert, die einen regulären Ausdruck mit einem Timeoutintervall von 350 Millisekunden instanziiert, um für ein Textdokument die Anzahl der Wörter und die durchschnittliche Anzahl der Zeichen pro Wort zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-294">The following example defines a `GetWordData` method that instantiates a regular expression with a time-out interval of 350 milliseconds to calculate the number of words and average number of characters in a word in a text document.</span></span> <span data-ttu-id="a6b69-295">Wenn ein Timout für den entsprechenden Vorgang erfolgt, wird das Timeoutintervall um 350 Millisekunden erhöht und das [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt erneut instanziiert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-295">If the matching operation times out, the time-out interval is increased by 350 milliseconds and the [Regex](xref:System.Text.RegularExpressions.Regex) object is re-instantiated.</span></span> <span data-ttu-id="a6b69-296">Wenn das neue Timeoutintervall 1 Sekunde übersteigt, löst die Methode für den Aufrufer erneut eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a6b69-296">If the new time-out interval exceeds 1 second, the method re-throws the exception to the caller.</span></span>

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

## <a name="capture-only-when-necessary"></a><span data-ttu-id="a6b69-297">Erfassungen nur bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="a6b69-297">Capture only when necessary</span></span>

<span data-ttu-id="a6b69-298">Reguläre Ausdrücke in .NET unterstützen eine Reihe von Gruppierungskonstrukten, mit denen Sie ein Muster für reguläre Ausdrücke in einen Teilausdruck oder in mehrere Teilausdrücke gruppieren können.</span><span class="sxs-lookup"><span data-stu-id="a6b69-298">Regular expressions in .NET support a number of grouping constructs, which let you group a regular expression pattern into one or more subexpressions.</span></span> <span data-ttu-id="a6b69-299">Die am häufigsten verwendeten Gruppierungskonstrukte in der .NET-Sprache für reguläre Ausdrücke sind **(**_Teilausdruck_**)** zum Definieren einer nummerierten Erfassungsgruppe und **(?<*_Name_**>**_Teilausdruck_**)** zum Definieren einer benannten Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="a6b69-299">The most commonly used grouping constructs in .NET regular expression language are **(**_subexpression_**)**, which defines a numbered capturing group, and **(?<*_name_**>**_subexpression_**)**, which defines a named capturing group.</span></span> <span data-ttu-id="a6b69-300">Gruppierungskonstrukte sind wichtig für das Erstellen von Rückverweisen und für das Definieren eines Teilausdrucks, auf den ein Quantifizierer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-300">Grouping constructs are essential for creating backreferences and for defining a subexpression to which a quantifier is applied.</span></span> 

<span data-ttu-id="a6b69-301">Die Verwendung dieser Sprachelemente hat jedoch auch Nachteile.</span><span class="sxs-lookup"><span data-stu-id="a6b69-301">However, the use of these language elements has a cost.</span></span> <span data-ttu-id="a6b69-302">Sie führen dazu, dass das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegebene [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt mit den neuesten unbenannten oder benannten Erfassungen aufgefüllt wird. Wenn ein einzelnes Gruppierungskonstrukt mehrere Teilzeichenfolgen in der Eingabezeichenfolge erfasst hat, wird auch das von der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft einer bestimmten Erfassungsgruppe zurückgegebene [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt mit mehreren [Capture](xref:System.Text.RegularExpressions.Capture)-Objekten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-302">They cause the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property to be populated with the most recent unnamed or named captures, and if a single grouping construct has captured multiple substrings in the input string, they also populate the [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) object returned by the [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) property of a particular capturing group with multiple [Capture](xref:System.Text.RegularExpressions.Capture) objects.</span></span>

<span data-ttu-id="a6b69-303">Gruppierungskonstrukte werden häufig nur in einem regulären Ausdruck verwendet, damit Quantifizierer auf sie angewendet werden können. Die von diesen Teilausdrücken erfassten Gruppen werden später nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6b69-303">Often, grouping constructs are used in a regular expression only so that quantifiers can be applied to them, and the groups captured by these subexpressions are not subsequently used.</span></span> <span data-ttu-id="a6b69-304">Beispielsweise soll der reguläre Ausdruck `\b(\w+[;,]?\s?)+[.?!]` einen vollständigen Satz erfassen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-304">For example, the regular expression `\b(\w+[;,]?\s?)+[.?!]` is designed to capture an entire sentence.</span></span> <span data-ttu-id="a6b69-305">In der folgenden Tabelle werden die Sprachelemente in diesem regulären Ausdrucksmuster und ihre Auswirkungen auf die [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Auflistung und die [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Auflistung des [Match](xref:System.Text.RegularExpressions.Match)-Objekts beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6b69-305">The following table describes the language elements in this regular expression pattern and their effect on the [Match](xref:System.Text.RegularExpressions.Match) object's [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) and [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) collections.</span></span>

<span data-ttu-id="a6b69-306">Muster</span><span class="sxs-lookup"><span data-stu-id="a6b69-306">Pattern</span></span> | <span data-ttu-id="a6b69-307">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-307">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="a6b69-308">Der Vergleich beginnt an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="a6b69-308">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="a6b69-309">Übereinstimmung mit mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-309">Match one or more word characters.</span></span>
`[;,]?` | <span data-ttu-id="a6b69-310">Übereinstimmung mit keinem oder einem Komma oder Semikolon.</span><span class="sxs-lookup"><span data-stu-id="a6b69-310">Match zero or one comma or semicolon.</span></span>
`\s?` | <span data-ttu-id="a6b69-311">Übereinstimmung mit keinem oder einem Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-311">Match zero or one white-space character.</span></span>
`(\w+[;,]?\s?)+` | <span data-ttu-id="a6b69-312">Übereinstimmung mit einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen, gefolgt von einem optionalen Komma oder Semikolon, gefolgt von einem optionalen Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-312">Match one or more occurrences of one or more word characters followed by an optional comma or semicolon followed by an optional white-space character.</span></span> <span data-ttu-id="a6b69-313">Hiermit wird die erste Erfassungsgruppe definiert. Dies ist erforderlich, damit die Kombination mehrerer Wortzeichen (d. h. ein Wort) gefolgt von einem optionalen Interpunktionssymbol wiederholt wird, bis das Modul für reguläre Ausdrücke das Ende eines Satzes erreicht.</span><span class="sxs-lookup"><span data-stu-id="a6b69-313">This defines the first capturing group, which is necessary so that the combination of multiple word characters (that is, a word) followed by an optional punctuation symbol will be repeated until the regular expression engine reaches the end of a sentence.</span></span>
`[.?!]` | <span data-ttu-id="a6b69-314">Übereinstimmung mit einem Punkt, Fragezeichen oder Ausrufezeichen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-314">Match a period, question mark, or exclamation point.</span></span>
 
<span data-ttu-id="a6b69-315">Wie im folgenden Beispiel gezeigt, werden das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt und das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt mit Erfassungen aus der Übereinstimmungssuche aufgefüllt, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-315">As the following example shows, when a match is found, both the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) objects are populated with captures from the match.</span></span> <span data-ttu-id="a6b69-316">In diesem Fall wird die Erfassungsgruppe `(\w+[;,]?\s?)` angegeben, damit der **+**-Quantifizierer darauf angewendet werden kann, wodurch das Muster für reguläre Ausdrücke Übereinstimmungen für jedes Wort in einem Satz erfassen kann.</span><span class="sxs-lookup"><span data-stu-id="a6b69-316">In this case, the capturing group `(\w+[;,]?\s?)` exists so that the **+** quantifier can be applied to it, which enables the regular expression pattern to match each word in a sentence.</span></span> <span data-ttu-id="a6b69-317">Andernfalls würde es mit dem letzten Wort in einem Satz abgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-317">Otherwise, it would match the last word in a sentence.</span></span>

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

<span data-ttu-id="a6b69-318">Wenn Sie Teilausdrücke nur verwenden, um Quantifizierer darauf anzuwenden, und den erfassten Text nicht benötigen, sollten Sie Gruppenerfassungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6b69-318">When you use subexpressions only to apply quantifiers to them, and you are not interested in the captured text, you should disable group captures.</span></span> <span data-ttu-id="a6b69-319">Zum Beispiel verhindert das Sprachelement **(?:**_Teilausdruck_**)**, dass die Gruppe, auf die es angewendet wird, übereinstimmende Teilzeichenfolgen erfasst.</span><span class="sxs-lookup"><span data-stu-id="a6b69-319">For example, the **(?:**_subexpression_**)** language element prevents the group to which it applies from capturing matched substrings.</span></span> <span data-ttu-id="a6b69-320">Im folgenden Beispiel wird das Muster eines regulären Ausdrucks aus dem vorherigen Beispiel in `\b(?:\w+[;,]?\s?)+[.?!]` geändert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-320">In the following example, the regular expression pattern from the previous example is changed to `\b(?:\w+[;,]?\s?)+[.?!]`.</span></span> <span data-ttu-id="a6b69-321">Hiermit wird verhindert, dass das Modul für reguläre Ausdrücke die [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Auflistung und die [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Auflistung auffüllt, wie die Ausgabe im Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="a6b69-321">As the output shows, it prevents the regular expression engine from populating the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) collections.</span></span>

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

<span data-ttu-id="a6b69-322">Erfassungen können Sie auf eine der folgenden Arten deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a6b69-322">You can disable captures in one of the following ways:</span></span>

* <span data-ttu-id="a6b69-323">Verwenden des Sprachelements **(?:**_Teilausdruck_**)**.</span><span class="sxs-lookup"><span data-stu-id="a6b69-323">Use the **(?:**_subexpression_**)** language element.</span></span> <span data-ttu-id="a6b69-324">Dieses Element verhindert die Erfassung übereinstimmender Teilzeichenfolge in der Gruppe, auf die es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6b69-324">This element prevents the capture of matched substrings in the group to which it applies.</span></span> <span data-ttu-id="a6b69-325">Die Erfassung von Teilzeichenfolgen in geschachtelten Gruppen wird nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-325">It does not disable substring captures in any nested groups.</span></span>

* <span data-ttu-id="a6b69-326">Verwenden der Option [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture).</span><span class="sxs-lookup"><span data-stu-id="a6b69-326">Use the [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) option.</span></span> <span data-ttu-id="a6b69-327">Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen im Muster für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="a6b69-327">It disables all unnamed or implicit captures in the regular expression pattern.</span></span> <span data-ttu-id="a6b69-328">Wenn Sie diese Option verwenden, können nur Teilzeichenfolgen erfasst werden, die mit benannten Gruppen übereinstimmen, die mit dem Sprachelement **(?<**_Name_**>**_Teilausdruck_**)** definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-328">When you use this option, only substrings that match named groups defined with the **(?<**_name_**>**_subexpression_**)** language element can be captured.</span></span> <span data-ttu-id="a6b69-329">Das [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)-Flag kann dem Optionsparameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder dem Optionsparameter einer statischen [Regex](xref:System.Text.RegularExpressions.Regex)-Methode für Übereinstimmung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6b69-329">The [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) flag can be passed to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) class constructor or to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) static matching method.</span></span>

* <span data-ttu-id="a6b69-330">Verwenden Sie die **n**-Option im Sprachelement **(?imnsx)**.</span><span class="sxs-lookup"><span data-stu-id="a6b69-330">Use the **n** option in the **(?imnsx)** language element.</span></span> <span data-ttu-id="a6b69-331">Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen ab dem Punkt im Muster für reguläre Ausdrücke, an dem das Element erscheint.</span><span class="sxs-lookup"><span data-stu-id="a6b69-331">This option disables all unnamed or implicit captures from the point in the regular expression pattern at which the element appears.</span></span> <span data-ttu-id="a6b69-332">Erfassungen werden entweder bis zum Ende des Musters oder so lange deaktiviert, bis die **(-n)**-Option unbenannte oder implizite Erfassungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-332">Captures are disabled either until the end of the pattern or until the **(-n)** option enables unnamed or implicit captures.</span></span> <span data-ttu-id="a6b69-333">Weitere Informationen finden Sie unter [Verschiedene Konstrukte in regulären Ausdrücken](miscellaneous.md).</span><span class="sxs-lookup"><span data-stu-id="a6b69-333">For more information, see [Miscellaneous constructs in regular expressions](miscellaneous.md).</span></span>

* <span data-ttu-id="a6b69-334">Verwenden Sie die **n**-Option im Sprachelement **(?imnsx:**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="a6b69-334">Use the **n** option in the **(?imnsx:**_subexpression_**)** language element.</span></span> <span data-ttu-id="a6b69-335">Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen in *Teilausdruck*.</span><span class="sxs-lookup"><span data-stu-id="a6b69-335">This option disables all unnamed or implicit captures in *subexpression*.</span></span> <span data-ttu-id="a6b69-336">Erfassungen von allen unbenannten oder impliziten geschachtelten Erfassungsgruppen werden ebenfalls deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6b69-336">Captures by any unnamed or implicit nested capturing groups are disabled as well.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6b69-337">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a6b69-337">Related topics</span></span>

<span data-ttu-id="a6b69-338">Titel</span><span class="sxs-lookup"><span data-stu-id="a6b69-338">Title</span></span> | <span data-ttu-id="a6b69-339">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b69-339">Description</span></span>
----- | ----------- 
[<span data-ttu-id="a6b69-340">Einzelheiten zum Verhalten regulärer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="a6b69-340">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="a6b69-341">Überprüft die Implementierung des Moduls für reguläre Ausdrücke in .NET.</span><span class="sxs-lookup"><span data-stu-id="a6b69-341">Examines the implementation of the regular expression engine in .NET.</span></span> <span data-ttu-id="a6b69-342">Schwerpunkt dieses Themas ist die Flexibilität regulärer Ausdrücke. Außerdem wird die Verantwortung des Entwicklers erläutert, das effiziente und stabile Ausführen des Moduls für reguläre Ausdrücke sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6b69-342">The topic focuses on the flexibility of regular expressions and explains the developer's responsibility for ensuring the efficient and robust operation of the regular expression engine.</span></span>
[<span data-ttu-id="a6b69-343">Backtracking in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a6b69-343">Backtracking in regular expressions</span></span>](backtracking.md) | <span data-ttu-id="a6b69-344">Erläutert die Rückverfolgung und deren Auswirkungen auf die Leistung von regulären Ausdrücken. Zudem werden Sprachelemente beschrieben, die Alternativen zum Zurückverfolgen bieten.</span><span class="sxs-lookup"><span data-stu-id="a6b69-344">Explains what backtracking is and how it affects regular expression performance, and examines language elements that provide alternatives to backtracking.</span></span>
[<span data-ttu-id="a6b69-345">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="a6b69-345">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="a6b69-346">Beschreibt die Elemente der Sprache für reguläre Ausdrücke in .NET und enthält Links zu ausführlichen Dokumentationen für jedes Sprachelement.</span><span class="sxs-lookup"><span data-stu-id="a6b69-346">Describes the elements of the regular expression language in .NET and provides links to detailed documentation for each language element.</span></span>
 


