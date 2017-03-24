---
title: "char (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "char"
  - "char_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "char-Datentyp [C#]"
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# char (C#-Referenz)
Das `char`\-Schlüsselwort wird verwendet, um eine Instanz der <xref:System.Char?displayProperty=fullName>\-Struktur zu deklarieren, der .NET Framework verwendet, um ein Unicode\-Zeichen darzustellen.  Der Wert eines \- Objekts `Char` ist ein numerischer \(Ordnungszahlen\) 16\-Bit\-Wert.  
  
 Unicode\-Zeichen werden verwendet, um die meisten Schriftsprachen weltweit darzustellen.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`char`|U\+0000 bis U\+FFFF|16\-Bit\-Unicode\-Zeichen|<xref:System.Char?displayProperty=fullName>|  
  
## Literale  
 Konstanten vom Typ `char` können als Zeichenliterale, als hexadezimale Escapesequenz oder in Unicode\-Darstellung geschrieben werden.  Sie können auch eine Typumwandlung der ganzzahligen Zeichencodes durchführen.  Im folgenden Beispiel werden vier `char`\-Variablen mit dem gleichen Zeichen `X` initialisiert:  
  
 [!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## Konvertierungen  
 Ein `char` kann implizit konvertiert werden in [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  Es finden jedoch keine impliziten Konvertierungen von anderen Datentypen in den `char`\-Typ statt.  
  
 Der <xref:System.Char?displayProperty=fullName>\-Typ stellt mehrere statische Methoden zum Arbeiten mit `char`\-Werten bereit.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Char>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)