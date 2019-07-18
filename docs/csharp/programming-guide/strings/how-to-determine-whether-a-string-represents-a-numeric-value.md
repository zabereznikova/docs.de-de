---
title: 'Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 626fce590ba08bbdabf27ac33287a0b46b592f9c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423616"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a>Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierhandbuch)
Verwenden Sie die statische `TryParse`-Methode, die von allen primitiven numerischen Typen sowie von Typen wie z.B. <xref:System.DateTime> und <xref:System.Net.IPAddress> implementiert wird, um zu bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist. In folgendem Beispiel wird gezeigt, wie Sie bestimmen können, ob „108“ eine zulässige [ganze Zahl](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) ist.  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Wenn die Zeichenfolge nicht numerische Zeichen enthält oder der numerische Wert für den Typ, den Sie angegeben haben, zu groß oder zu klein ist, gibt `TryParse` „FALSE“ zurück und legt den Parameter auf 0 (null) fest. Andernfalls wird „TRUE“ zurückgegeben und der Parameter auf den numerischen Wert der Zeichenfolge festgelegt.  
  
> [!NOTE]
>  Eine Zeichenfolge kann auch nur numerische Zeichen enthalten und trotzdem für den Typ unzulässig sein, dessen `TryParse`-Methode Sie verwenden. Beispielsweise ist „256“ kein zulässiger Wert für `byte`, aber zulässig für `int`. „98,6“ ist kein zulässiger Wert für `int`, aber zulässig für `decimal`.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird gezeigt, wie Sie `TryParse` mit einer Zeichenfolgenrepräsentation von den Werten `long`, `byte` und `decimal` verwenden können.  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Primitive numerische Typen implementieren auch die statische `Parse`-Methode, die eine Ausnahme auslöst, wenn die Zeichenfolge keine zulässige Zahl ist. `TryParse` ist für gewöhnlich effizienter, da es einfach „FALSE“ zurückgibt, wenn die Zahl unzulässig ist.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Verwenden Sie immer die Methoden `TryParse` oder `Parse`, um Benutzereingaben von Steuerelementen wie Text- oder Kombinationsfeldern zu überprüfen.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)
- [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
- [Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [Verarbeiten numerischer Zeichenfolgen](../../../standard/base-types/parsing-numeric.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
