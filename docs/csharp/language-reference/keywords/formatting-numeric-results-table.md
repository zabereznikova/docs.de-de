---
title: "Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Formatierung [C#]"
  - "Numerische Formatierung [C#]"
  - "String.Format-Methode"
  - "Console.Write-Methode"
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)
Sie können die numerischen Ergebnisse mit der <xref:System.String.Format%2A?displayProperty=fullName>\-Methode formatieren oder mit der <xref:System.Console.Write%2A?displayProperty=fullName>\-Methode oder der <xref:System.Console.WriteLine%2A?displayProperty=fullName>\-Methode, die `String.Format` aufruft.  Das Format wird mittels Formatzeichenfolgen angegeben.  In der folgenden Tabelle sind die unterstützten Standardformatzeichenfolgen aufgeführt.  Die Formatierungszeichenfolge nimmt die folgende Form an: `Axx`, wobei `A` der Formatbezeichner und `xx` der Genauigkeitsbezeichner ist.  Der Formatbezeichner steuert die auf den numerischen Wert angewendete Formatierung, und der Genauigkeitsbezeichner steuert die Anzahl der signifikanten Stellen oder Dezimalstellen in der formatierten Ausgabe.  Der Wert der Genauigkeitsangabe reicht von 0 bis 99.  
  
 Weitere Informationen über die standardmäßigen und benutzerdefinierten Formatierungszeichenfolgen, finden Sie unter [Formatierung von Typen](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  Weitere Informationen zur `String.Format`\-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=fullName>.  
  
|Formatbezeichner|Beschreibung|Beispiele|Ausgabe|  
|----------------------|------------------|---------------|-------------|  
|C oder c|Währung|Console.Write\("{0:C}", 2.5\);<br /><br /> Console.Write\("{0:C}", \-2.5\);|$2.50<br /><br /> \($2.50\)|  
|D oder d|Decimal|Console.Write\("{0:D5}", 25\);|00025|  
|E oder e|Wissenschaftlich|Console.Write\("{0:E}", 250000\);|2.500000E\+005|  
|F oder f|Festkomma|Console.Write\("{0:F2}", 25\);<br /><br /> Console.Write\("{0:F0}", 25\);|25.00<br /><br /> 25|  
|G oder g|Allgemein|Console.Write\("{0:G}", 2.5\);|2.5|  
|N oder n|Number|Console.Write\("{0:N}", 2500000\);|2,500,000.00|  
|X oder x|Hexadezimal|Console.Write\("{0:X}", 250\);<br /><br /> Console.Write\("{0:X}", 0xffff\);|FA<br /><br /> FFFF|  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Standardmäßige Zahlenformatzeichenfolgen](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [string](../../../csharp/language-reference/keywords/string.md)