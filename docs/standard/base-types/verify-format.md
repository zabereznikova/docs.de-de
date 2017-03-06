---
title: "Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen"
description: "Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6d735520-4059-4754-b34c-d117299d36f1
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 077a09152ac23c986a751f42c893e1dcca858291
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen

Im folgenden Beispiel wird mit einem regulären Ausdruck geprüft, ob eine Zeichenfolge ein gültiges E-Mail-Format aufweist.

## <a name="example"></a>Beispiel

Im Beispiel wird eine `IsValidEmail`-Methode definiert, die `true` zurückgibt, wenn die Zeichenfolge eine gültige E-Mail-Adresse enthält und andernfalls `false`; es wird jedoch keine andere Aktion ausgeführt. 

Um die Gültigkeit der E-Mail-Adresse zu überprüfen, ruft die `IsValidEmail`-Methode die [Regex.Replace(String, String, MatchEvaluator)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.Text.RegularExpressions.MatchEvaluator))-Methode mit dem regulären Ausdruck `(@)(.+)$` auf, um den Domänennamen von der E-Mail-Adresse zu trennen. Der dritte Parameter ist ein [MatchEvaluator](xref:System.Text.RegularExpressions.MatchEvaluator)-Delegat, der die Methode darstellt, die den gefundenen Text verarbeitet und ersetzt. Das Muster des regulären Ausdrucks wird wie folgt interpretiert: 

Muster | Beschreibung
------- | ----------- 
`(@)` | Das "@"-Zeichen wird als Übereinstimmung verwendet. Dies ist die erste Erfassungsgruppe.
`(.+)` | Ein- oder mehrmalige Übereinstimmung mit beliebigem Zeichen. Dies ist die zweite Erfassungsgruppe.
`$` | Beendet die Suche am Ende der Zeichenfolge.
 
Der Domänenname wird zusammen mit dem @-Zeichen der `DomainMapper`-Methode übergeben, die die [IdnMapping](xref:System.Globalization.IdnMapping)-Klasse verwendet, um Unicode-Zeichen, die außerhalb des US-ASCII-Zeichenbereichs liegen, in ihre Punycode-Entsprechungen zu übersetzen. Darüber hinaus legt die Methode auch das `invalid`-Flag auf `true` fest, wenn die [IdnMapping.GetAscii](xref:System.Globalization.IdnMapping.GetAscii(System.String))-Methode ein unzulässiges Zeichen im Domänennamen erkennt. Diese Methode gibt den Punycode-Domänennamen, der dem "@"-Zeichen vorangestellt ist, an die `IsValidEmail`-Methode zurück. 

Die `IsValidEmail`-Methode ruft dann die [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String))-Methode auf, um zu überprüfen, ob die Adresse dem Muster eines regulären Ausdrucks entspricht. 

Beachten Sie, dass die `IsValidEmail`-Methode keine Authentifizierung zur Überprüfung der E-Mail-Adresse durchführt. Sie bestimmt nur, ob das Format für eine E-Mail-Adresse gültig ist. Außerdem überprüft die `IsValidEmail`-Methode nicht, ob der Domänenname der obersten Ebene ein gültiger Domänenname ist, der in der [IANA Root Zone Database](https://www.iana.org/domains/root/db) aufgelistet ist, was einen Suchvorgang erfordern würde. Stattdessen verifiziert der reguläre Ausdruck nur, dass der Domänenname der obersten Ebene aus zwei bis&24; ASCII-Zeichen besteht, wobei das erste und letzte Zeichen alphanumerisch und die übrigen Zeichen alphanumerisch oder ein Bindestrich (-) sein müssen. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class RegexUtilities
{
   bool invalid = false;

   public bool IsValidEmail(string strIn)
   {
       invalid = false;
       if (String.IsNullOrEmpty(strIn))
          return false;

       // Use IdnMapping class to convert Unicode domain names.
       try {
          strIn = Regex.Replace(strIn, @"(@)(.+)$", this.DomainMapper,
                                RegexOptions.None, TimeSpan.FromMilliseconds(200));
       }
       catch (RegexMatchTimeoutException) {
         return false;
       }

        if (invalid)
           return false;

       // Return true if strIn is in valid e-mail format.
       try {
          return Regex.IsMatch(strIn,
                @"^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                @"(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250));
       }
       catch (RegexMatchTimeoutException) {
          return false;
       }
   }

   private string DomainMapper(Match match)
   {
      // IdnMapping class with default property values.
      IdnMapping idn = new IdnMapping();

      string domainName = match.Groups[2].Value;
      try {
         domainName = idn.GetAscii(domainName);
      }
      catch (ArgumentException) {
         invalid = true;
      }
      return match.Groups[1].Value + domainName;
   }
}
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Class RegexUtilities
   Dim invalid As Boolean = False

   public Function IsValidEmail(strIn As String) As Boolean
       invalid = False
       If String.IsNullOrEmpty(strIn) Then Return False

       ' Use IdnMapping class to convert Unicode domain names.
       Try
          strIn = Regex.Replace(strIn, "(@)(.+)$", AddressOf Me.DomainMapper, 
                                RegexOptions.None, TimeSpan.FromMilliseconds(200))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try

       If invalid Then Return False

       ' Return true if strIn is in valid e-mail format.
       Try
          Return Regex.IsMatch(strIn,
                 "^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                 "(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                 RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try  
   End Function

   Private Function DomainMapper(match As Match) As String
      ' IdnMapping class with default property values.
      Dim idn As New IdnMapping()

      Dim domainName As String = match.Groups(2).Value
      Try
         domainName = idn.GetAscii(domainName)
      Catch e As ArgumentException
         invalid = True      
      End Try      
      Return match.Groups(1).Value + domainName
   End Function
End Class
```

In diesem Beispiel kann das Muster des regulären Ausdrucks `^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~ \w])*)(?<=[0-9a-z])@))(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9 a-z] [-\w]*[0-9 a-z]*\.) + [a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$` wie in der folgenden Tabelle dargestellt interpretiert werden. Beachten Sie, dass der reguläre Ausdruck mit dem [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Flag kompiliert wurde.

Muster | Beschreibung
------- | ----------- 
`^` | Starten Sie den Vergleich am Beginn der Zeichenfolge.
`(?(")` | Ermittelt, ob es sich beim ersten Zeichen um ein Anführungszeichen handelt. `(?(")` ist der Anfang eines Alternierungskonstrukts.
`(?("")("".+?(?<!\\)""@)` | Wenn es sich beim ersten Zeichen um ein Anführungszeichen handelt, wird ein öffnendes Anführungszeichen als Übereinstimmung verwendet, dem mindestens ein beliebiges Zeichen und ein schließendes Anführungszeichen folgen. Dem schließenden Anführungszeichen darf kein umgekehrter Schrägstrich vorangestellt sein `(\). (?<!` ist der Anfang einer negativen Lookbehindassertion mit einer Breite von&0; (Null). Die Zeichenfolge muss mit einem "@"-Zeichen enden.
`&#124;(([0-9a-z] | Wenn es sich beim ersten Zeichen um kein Anführungszeichen handelt, wird ein beliebiges Buchstabenzeichen von a bis z oder A bis Z (die Groß-/Kleinschreibung wird nicht beachtet) oder ein beliebiges numerisches Zeichen von 0 bis 9 als Übereinstimmung verwendet.
`(\.(?!\.))` | Wenn es sich beim nächsten Zeichen um einen Punkt handelt, wird dieser als Übereinstimmung verwendet. Wenn es sich um keinen Punkt handelt, wird bis zum nächsten Zeichen weitergesucht und der Vergleich fortsetzt. `(?!\.)` ist eine negative Lookaheadassertion mit einer Breite von&0; (Null), die verhindert, dass im lokalen Teil einer E-Mail-Adresse zwei aufeinander folgende Punkte enthalten sind.
`&#124;[-!#\$%&'\*\+/=\?\^`\{\}\&#124;~\w] | Wenn es sich beim nächsten Zeichen um keinen Punkt handelt, wird ein beliebiges Wortzeichen oder eines der folgenden Zeichen als Übereinstimmung verwendet: -!#$%'*+=?^`{}&#124;~. 
`((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^`\{\}\&#124;~\w])* | 0 oder mehr Vorkommen des Alternierungsmusters werden als Übereinstimmung verwendet (ein Punkt, dem ein anderes Zeichen als ein Punkt oder eines aus einer Reihe von Zeichen folgt).
`@` | Das "@"-Zeichen wird als Übereinstimmung verwendet.
`(?<=[0-9a-z])` | Die Suche wird fortgesetzt, wenn es sich bei dem Zeichen, das dem @-Zeichen vorausgeht, ist, um eines der Zeichen A bis Z, a bis z oder 0 bis 9 handelt. Das `(?<=[0-9a-z])`-Konstrukt definiert eine positive Lookbehindassertion mit einer Breite von&0; (Null).
`(?(\[)` | Überprüfen Sie, ob es sich bei dem Zeichen, das @ folgt, um eine eckige Klammer links handelt.
`(\[(\d{1,3}\.){3}\d{1,3}\])` | Wenn es sich um eine eckige Klammer links handelt, wird die eckige Klammer links als Übereinstimmung verwendet, der eine IP-Adresse (vier Gruppen aus einer bis drei Ziffern, jeweils durch einen Punkt getrennt) und eine eckige Klammer rechts folgen.
`&#124;(([0-9a-z][-\w]*[0-9a-z]*\.)+` | Wenn es sich bei dem Zeichen, das @ folgt, um keine eckige Klammer links handelt, wird ein alphanumerisches Zeichen mit einem Wert von A-Z, a-z oder 0-9 als Übereinstimmung verwendet, dem 0 oder mehr Vorkommen eines Wortzeichens oder eines Bindestrichs und kein oder ein alphanumerisches Zeichen mit einem Wert von A-Z, a-z oder 0-9 sowie ein Punkt folgen. Dieses Muster kann ein- oder mehrmals wiederholt werden und der Domänenname der obersten Ebene muss darauf folgen. 
`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))` | Der Domänenname der obersten Ebene muss mit einem alphanumerischen Zeichen (a-z, A-Z und 0-9) beginnen und enden. Er kann außerdem 0 bis 22 ASCII-Zeichen enthalten, die entweder alphanumerische Zeichen oder Bindestriche sind. 
`$` | Beendet die Suche am Ende der Zeichenfolge.
 
Rufen Sie die Methoden `IsValidEmail` und `DomainMapper` mithilfe von Code wie dem folgenden auf:

```csharp
public class Application
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string[] emailAddresses = { "david.jones@proseware.com", "d.j@server1.proseware.com",
                                  "jones@ms1.proseware.com", "j.@server1.proseware.com",
                                  "j@proseware.com9", "js#internal@proseware.com",
                                  "j_9@[129.126.118.1]", "j..s@proseware.com",
                                  "js*@proseware.com", "js@proseware..com",
                                  "js@proseware.com9", "j.s@server1.proseware.com",
                                   "\"j\\\"s\\\"\"@proseware.com", "js@contoso.中国" };

      foreach (var emailAddress in emailAddresses) {
         if (util.IsValidEmail(emailAddress))
            Console.WriteLine("Valid: {0}", emailAddress);
         else
            Console.WriteLine("Invalid: {0}", emailAddress);
      }                                            
   }
}
// The example displays the following output:
//       Valid: david.jones@proseware.com
//       Valid: d.j@server1.proseware.com
//       Valid: jones@ms1.proseware.com
//       Invalid: j.@server1.proseware.com
//       Valid: j@proseware.com9
//       Valid: js#internal@proseware.com
//       Valid: j_9@[129.126.118.1]
//       Invalid: j..s@proseware.com
//       Invalid: js*@proseware.com
//       Invalid: js@proseware..com
//       Valid: js@proseware.com9
//       Valid: j.s@server1.proseware.com
//       Valid: "j\"s\""@proseware.com
//       Valid: js@contoso.ä¸­å›½
```

```vb
Public Class Application
   Public Shared Sub Main()
      Dim util As New RegexUtilities()
      Dim emailAddresses() As String = { "david.jones@proseware.com", "d.j@server1.proseware.com", _
                                         "jones@ms1.proseware.com", "j.@server1.proseware.com", _
                                         "j@proseware.com9", "js#internal@proseware.com", _
                                         "j_9@[129.126.118.1]", "j..s@proseware.com", _
                                         "js*@proseware.com", "js@proseware..com", _
                                         "js@proseware.com9", "j.s@server1.proseware.com",
                                         """j\""s\""""@proseware.com", "js@contoso.中国" }

      For Each emailAddress As String In emailAddresses
         If util.IsValidEmail(emailAddress) Then
            Console.WriteLine("Valid: {0}", emailAddress)
         Else
            Console.WriteLine("Invalid: {0}", emailAddress)
         End If      
      Next                                            
   End Sub
End Class
' The example displays the following output:
'       Valid: david.jones@proseware.com
'       Valid: d.j@server1.proseware.com
'       Valid: jones@ms1.proseware.com
'       Invalid: j.@server1.proseware.com
'       Valid: j@proseware.com9
'       Valid: js#internal@proseware.com
'       Valid: j_9@[129.126.118.1]
'       Invalid: j..s@proseware.com
'       Invalid: js*@proseware.com
'       Invalid: js@proseware..com
'       Valid: js@proseware.com9
'       Valid: j.s@server1.proseware.com
'       Valid: "j\"s\""@proseware.com
'       Valid: js@contoso.ä¸­å›½
```

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Beispiele für reguläre Ausdrücke](regex-examples.md)

