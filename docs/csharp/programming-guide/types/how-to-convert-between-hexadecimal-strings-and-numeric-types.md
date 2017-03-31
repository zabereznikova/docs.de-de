---
title: 'Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5852e79f551ce88e0ca54de159abbc222d769234
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Gewusst wie: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)
In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:  
  
-   Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../../csharp/language-reference/keywords/string.md)  
  
-   Abrufen des [char](../../../csharp/language-reference/keywords/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht  
  
-   Konvertieren eines hexadezimalen `string` in [int](../../../csharp/language-reference/keywords/int.md)  
  
-   Konvertieren eines hexadezimalen `string` in [float](../../../csharp/language-reference/keywords/float.md)  
  
-   Konvertieren eines [Byte](../../../csharp/language-reference/keywords/byte.md)-Arrays in einen hexadezimalen `string`  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben. Zuerst wird der `string` in ein Array von Zeichen aufgegliedert. Dann wird auf jedem Zeichen <xref:System.Convert.ToInt32%28System.Char%29> aufgerufen, um dessen numerischen Wert zu erhalten. Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben. Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen. Dann wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, um den Hexadezimalwert in einen Dezimalwert zu konvertieren, der als [int](../../../csharp/language-reference/keywords/int.md) dargestellt wird. Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen. Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht. Die zweite Methode wandelt `int` explizit in ein [char](../../../csharp/language-reference/keywords/char.md) um.  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt einen anderen Weg, wie Sie einen hexadezimalen `string` durch Aufrufen der <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode in eine ganze Zahl konvertieren.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen hexadezimalen `string` mithilfe der <xref:System.BitConverter?displayProperty=fullName>-Klasse und der <xref:System.Int32.Parse%2A?displayProperty=fullName>-Methode in ein [float](../../../csharp/language-reference/keywords/float.md) konvertieren.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ein [Byte](../../../csharp/language-reference/keywords/byte.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=fullName>-Klasse in eine hexadezimale Zeichenfolge konvertieren.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Standardmäßige Zahlenformatzeichenfolgen](http://msdn.microsoft.com/library/580e57eb-ac47-4ffd-bccd-3a1637c2f467)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

