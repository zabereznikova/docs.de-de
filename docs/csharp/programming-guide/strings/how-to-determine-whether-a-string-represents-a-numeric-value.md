---
title: "Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Numerische Zeichenfolgen [C#]"
  - "Zeichenfolgen [C#], Numerisch"
  - "Valisieren der numerischen Eingabe [C#]"
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierhandbuch)
Um zu bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist, verwenden Sie die statische `TryParse`\-Methode, die von allen primitiven numerischen Typen und von Typen, wie z. B. <xref:System.DateTime> und <xref:System.Net.IPAddress>, implementiert werden.  Im folgenden Beispiel wird gezeigt, wie Sie bestimmen können, ob "108" eine gültige [int](../../../csharp/language-reference/keywords/int.md) ist.  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Wenn die Zeichenfolge nicht\-numerische Zeichen enthält oder der numerische Wert zu groß bzw. zu klein für den angegebenen Typ ist, gibt `TryParse` den Wert false zurück und legt den out\-Parameter auf Null fest.  Andernfalls wird true zurückgegeben, und der out\-Parameter wird auf den numerischen Wert der Zeichenfolge festgelegt.  
  
> [!NOTE]
>  Eine Zeichenfolge kann nur numerische Zeichen enthalten und dennoch nicht für den Typ, dessen `TryParse`\-Methode Sie verwenden, gültig sein.  "256" ist beispielsweise kein gültiger Wert für `byte`, aber es ist für `int` gültig. "  98,6" ist kein gültiger Wert für `int`, ist jedoch für `decimal` gültig.  
  
## Beispiel  
 In den folgenden Beispielen wird gezeigt, wie Sie `TryParse` mit Zeichenfolgenentsprechungen von `long`, `byte` und `decimal` verwenden können.  
  
 [!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#14)]  
  
## Robuste Programmierung  
 Primitive numerische Typen implementieren auch die statische `Parse`\-Methode, die eine Ausnahme auslöst, wenn die Zeichenfolge keine gültige Zahl ist.  `TryParse` ist im Allgemeinen effektiver, da es nur den Wert false zurückgibt, wenn die Zahl nicht gültig ist.  
  
## .NET Framework-Sicherheit  
 Verwenden Sie immer die `TryParse`\- oder die `Parse`\-Methode, um die Benutzereingaben in Steuerelementen wie Textfelder und Kombinationsfelder zu überprüfen.  
  
## Siehe auch  
 [Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)   
 [Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)   
 [Gewusst wie: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)   
 [Verarbeiten numerischer Zeichenfolgen](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)   
 [Formatierung von Typen](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)