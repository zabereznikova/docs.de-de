---
title: 'Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL'
description: Extrahieren eines Protokolls und einer Portnummer aus einer URL
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d2462fb4-6d61-44ab-8466-73f1f06c3058
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 578b70412e876001f4462e2409739acf3609097b
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL

Das folgende Beispiel extrahiert ein Protokoll und eine Portnummer aus einer URL. 

## <a name="example"></a>Beispiel

Das Beispiel verwendet die [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methode, um das Protokoll, gefolgt von einem Doppelpunkt und der Portnummer, zurückzugeben. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string url = "http://www.contoso.com:8080/letters/readme";

      Regex r = new Regex(@"^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                          RegexOptions.None, TimeSpan.FromMilliseconds(150));
      Match m = r.Match(url);
      if (m.Success)
         Console.WriteLine(r.Match(url).Result("${proto}${port}")); 
   }
}
// The example displays the following output:
//       http:8080
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim url As String = "http://www.contoso.com:8080/letters/readme.html" 
      Dim r As New Regex("^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                         RegexOptions.None, TimeSpan.FromMilliseconds(150))

      Dim m As Match = r.Match(url)
      If m.Success Then
         Console.WriteLine(r.Match(url).Result("${proto}${port}"))
      End If   
   End Sub
End Module
' The example displays the following output:
'       http:8080
```

Das Muster für reguläre Ausdrücke `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle dargestellt interpretiert werden.

Muster | Beschreibung
------- | ----------- 
`^` | Starten Sie den Vergleich am Beginn der Zeichenfolge.
`(?<proto>\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Als Name der Gruppe wird „proto“ festgelegt.
`://` | Übereinstimmung mit einem Doppelpunkt, gefolgt von zwei Schrägstrichen.
`[^/]+?` | Übereinstimmung mit mindestens einem Vorkommen (jedoch so wenigen wie möglich) eines beliebigen Zeichens außer einem Schrägstrich.
`(?<port>:\d+)?` | Übereinstimmung mit keinem oder einem Vorkommen eines Doppelpunkts, gefolgt von mindestens einem Ziffernzeichen. Als Name der Gruppe wird „port“ festgelegt.
`/` | Übereinstimmung mit einem Schrägstrich.
 
Die [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methode erweitert die `${proto}${port}`-Ersatzsequenz, die den Wert der beiden benannten Gruppen verkettet, die im Muster für reguläre Ausdrücke erfasst wurden. Das ist eine praktische Alternative zum expliziten Verketten der Zeichenfolgen, die aus dem von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegebenen Auflistungsobjekt abgerufen werden.

Das Beispiel verwendet die [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methode mit zwei Ersetzungen, `${proto}` und `${port}`, um die erfassten Gruppen in die Ausgabezeichenfolge einzuschließen. Sie können die erfassten Gruppen stattdessen aus dem [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt der Übereinstimmung abrufen, wie im folgenden Code gezeigt.

```csharp
Console.WriteLine(m.Groups["proto"].Value + m.Groups["port"].Value); 
```

```vb
Console.WriteLine(m.Groups("proto").Value + m.Groups("port").Value)
```

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Beispiele für reguläre Ausdrücke](regex-examples.md)

