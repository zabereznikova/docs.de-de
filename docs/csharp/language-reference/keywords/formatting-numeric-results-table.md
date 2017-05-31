---
title: Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: a3e5d2eef3f0a76fc8e3faa52feca827070a9cab
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)
Sie können die numerischen Ergebnisse mithilfe der <xref:System.String.Format%2A?displayProperty=fullName>-Methode oder der <xref:System.Console.Write%2A?displayProperty=fullName>- oder <xref:System.Console.WriteLine%2A?displayProperty=fullName>-Methode formatieren, durch die `String.Format` aufgerufen wird. Das Format wird mithilfe von Formatzeichenfolgen angegeben. Die folgende Tabelle enthält die unterstützen Standardformatzeichenfolgen. Die Formatzeichenfolge nimmt die folgende Form an: `Axx`, wobei `A` der Formatbezeichner und `xx` die Genauigkeitsangabe ist. Der Formatbezeichner steuert den Formatierungstyp, der auf den numerischen Wert angewendet wird. Die Genauigkeitsangabe steuert die Anzahl signifikanter Stellen oder Dezimalstellen der formatierten Ausgabe. Der Wert der Genauigkeitsangabe liegt im Bereich 0–99.  
  
 Weitere Informationen zu standardmäßigen und benutzerdefinierten Formatierungszeichenfolgen finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md). Weitere Informationen zur `String.Format`-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=fullName>.  
  
|Formatbezeichner|Beschreibung|Beispiele|Ausgabe|  
|----------------------|-----------------|--------------|------------|  
|C oder c|Währung|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D oder d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E oder e|Wissenschaftlich|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F oder f|Festkomma|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G oder g|Allgemein|Console.Write("{0:G}", 2.5);|2.5|  
|N oder n|Anzahl|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X oder x|Hexadezimal|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md)   
 [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [string](../../../csharp/language-reference/keywords/string.md)
