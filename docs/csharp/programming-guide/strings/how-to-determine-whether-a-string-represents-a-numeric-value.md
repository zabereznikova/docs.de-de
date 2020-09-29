---
title: 'Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist. Hier finden Sie Codebeispiele und weitere Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: cbe0703ca39422ac0a9e7a93bf2cfc4c3f8528f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151427"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a>Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierleitfaden)

Verwenden Sie die statische `TryParse`-Methode, die von allen primitiven numerischen Typen sowie von Typen wie z.B. <xref:System.DateTime> und <xref:System.Net.IPAddress> implementiert wird, um zu bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist. In folgendem Beispiel wird gezeigt, wie Sie bestimmen können, ob „108“ eine zulässige [ganze Zahl](../../language-reference/builtin-types/integral-numeric-types.md) ist.  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Wenn die Zeichenfolge nicht numerische Zeichen enthält oder der numerische Wert für den Typ, den Sie angegeben haben, zu groß oder zu klein ist, gibt `TryParse` „FALSE“ zurück und legt den Parameter auf 0 (null) fest. Andernfalls wird „TRUE“ zurückgegeben und der Parameter auf den numerischen Wert der Zeichenfolge festgelegt.  
  
> [!NOTE]
> Eine Zeichenfolge kann auch nur numerische Zeichen enthalten und trotzdem für den Typ unzulässig sein, dessen `TryParse`-Methode Sie verwenden. Beispielsweise ist „256“ kein zulässiger Wert für `byte`, aber zulässig für `int`. „98,6“ ist kein zulässiger Wert für `int`, aber zulässig für `decimal`.  
  
## <a name="example"></a>Beispiel  

 In folgendem Beispiel wird gezeigt, wie Sie `TryParse` mit einer Zeichenfolgenrepräsentation von den Werten `long`, `byte` und `decimal` verwenden können.  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Primitive numerische Typen implementieren auch die statische `Parse`-Methode, die eine Ausnahme auslöst, wenn die Zeichenfolge keine zulässige Zahl ist. `TryParse` ist für gewöhnlich effizienter, da es einfach „FALSE“ zurückgibt, wenn die Zahl unzulässig ist.  
  
## <a name="net-security"></a>.NET-Sicherheit  

 Verwenden Sie immer die Methoden `TryParse` oder `Parse`, um Benutzereingaben von Steuerelementen wie Text- oder Kombinationsfeldern zu überprüfen.  
  
## <a name="see-also"></a>Siehe auch

- [Konvertieren eines Bytearrays in einen Typ „int“](../types/how-to-convert-a-byte-array-to-an-int.md)
- [Konvertieren einer Zeichenfolge in eine Zahl](../types/how-to-convert-a-string-to-a-number.md)
- [Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [Verarbeiten numerischer Zeichenfolgen](../../../standard/base-types/parsing-numeric.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
