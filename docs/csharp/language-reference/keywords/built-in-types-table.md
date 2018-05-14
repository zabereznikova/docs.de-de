---
title: Tabelle integrierter Typen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 7407d18c58dd3d12337c6845627d83f02eaf7fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="built-in-types-table-c-reference"></a>Tabelle integrierter Typen (C#-Referenz)
Die folgende Tabelle zeigt die Schlüsselwörter für integrierte C#-Typen, bei denen es sich um Aliase der vordefinierten Typen im <xref:System>-Namespace handelt.  
  
|C#-Typ|.NET Framework-Typ|  
|--------------|-------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[object](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a>Hinweise  
 Mit Ausnahme von `object` und `string` werden alle in der Tabelle enthaltenen Typen als einfache Typen bezeichnet.  
  
 C#-Typschlüsselwörter und ihre Aliase sind austauschbar. So können Sie beispielsweise eine ganzzahlige Variable mit einer der beiden folgenden Deklarationen angeben:  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Um den tatsächlichen Typ eines C#-Typs anzuzeigen, verwenden Sie die native Methode `GetType()`. Durch die folgende Anweisung wird z.B. der Systemalias angezeigt, der den Typ von `myVariable` darstellt:  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 Sie können auch den Operator [typeof](../../../csharp/language-reference/keywords/typeof.md) verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)  
 [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
