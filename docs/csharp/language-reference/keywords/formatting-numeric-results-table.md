---
title: Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 8d034955d5d5d31788eafc0c21246451d7fd1f35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474293"
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)
Sie können numerische Ergebnisse mithilfe der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode, durch die Methoden <xref:System.Console.Write%2A?displayProperty=nameWithType> und <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, die `String.Format` aufrufen, oder durch die [Zeichenfolgeninterpolation](../tokens/interpolated.md) formatieren. Das Format wird mithilfe von Formatzeichenfolgen angegeben. Die folgende Tabelle enthält die unterstützen Standardformatzeichenfolgen. Die Formatzeichenfolge nimmt die folgende Form an: `Axx`, wobei `A` der Formatbezeichner und `xx` die Genauigkeitsangabe ist. Der Formatbezeichner steuert den Formatierungstyp, der auf den numerischen Wert angewendet wird. Die Genauigkeitsangabe steuert die Anzahl signifikanter Stellen oder Dezimalstellen der formatierten Ausgabe. Der Wert der Genauigkeitsangabe liegt im Bereich 0–99.  
  
 Weitere Informationen zu standardmäßigen und benutzerdefinierten Formatierungszeichenfolgen finden Sie unter [Formatierung von Typen](../../../standard/base-types/formatting-types.md).
  
|Formatbezeichner|Beschreibung |Beispiele|Ausgabe|  
|----------------------|-----------------|--------------|------------|  
|C oder c|Währung|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D oder d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E oder e|Wissenschaftlich|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F oder f|Festkomma|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G oder g|Allgemein|Console.Write("{0:G}", 2.5);|2.5|  
|N oder n|Anzahl|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X oder x|Hexadezimal|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md)  
- [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [string](../../../csharp/language-reference/keywords/string.md)
