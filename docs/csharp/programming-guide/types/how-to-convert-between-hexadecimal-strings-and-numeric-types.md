---
title: 'Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: e5013891db827e27b3cda55135fff4ee287cfcb4
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423138"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen (C#-Programmierhandbuch)
In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:  
  
- Abrufen des Hexadezimalwerts jedes Zeichens in einer [Zeichenfolge](../../language-reference/builtin-types/reference-types.md)  
  
- Abrufen des [char](../../language-reference/keywords/char.md), das jedem Wert in einer Hexadezimalzeichenfolge entspricht  
  
- Konvertieren eines hexadezimalen `string` in [int](../../language-reference/builtin-types/integral-numeric-types.md)  
  
- Konvertieren eines hexadezimalen `string` in [float](../../language-reference/builtin-types/floating-point-numeric-types.md)  
  
- Konvertieren eines [Byte](../../language-reference/builtin-types/integral-numeric-types.md)-Arrays in einen hexadezimalen `string`  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Hexadezimalwert jedes Zeichens in einem `string` ausgegeben. Zuerst wird der `string` in ein Array von Zeichen aufgegliedert. Danach wird <xref:System.Convert.ToInt32%28System.Char%29> auf jedem Zeichen aufgerufen, um dessen numerischen Wert zu erhalten. Abschließend wird die Zahl als Hexadezimaldarstellung in einem `string` formatiert.  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein `string` von Hexadezimalwerten analysiert, und die den einzelnen Hexadezimalwerten entsprechenden Zeichen werden ausgegeben. Zuerst wird die [Split(Char\[\])](xref:System.String.Split(System.Char[]))-Methode aufgerufen, um jeden Hexadezimalwert als einzelnen `string` in einem Array abzurufen. Anschließend wird <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> aufgerufen, damit der Hexadezimalwert in einen Dezimalwert konvertiert, der als [int](../../language-reference/builtin-types/integral-numeric-types.md) dargestellt wird. Es werden zwei verschiedene Arten gezeigt, um das diesem Zeichencode entsprechende Zeichen abzurufen. Die erste Methode verwendet <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, wodurch das Zeichen zurückgegeben wird, das dem ganzzahligen Argument als `string` entspricht. Die zweite Methode wandelt `int` explizit in ein [char](../../language-reference/keywords/char.md) um.  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a>Beispiel  
 Diese Beispiel stellt eine andere Möglichkeit dar, eine hexadezimale `string` in einen Integer zu konvertieren, indem die <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>-Methode aufgerufen wird.  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine hexadezimale `string` in [float](../../language-reference/builtin-types/floating-point-numeric-types.md) konvertiert wird, indem die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse und die <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>-Methode verwendet wird.  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ein [Byte](../../language-reference/builtin-types/integral-numeric-types.md)-Array mithilfe der <xref:System.BitConverter?displayProperty=nameWithType>-Klasse in eine hexadezimale Zeichenfolge konvertieren.  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a>Siehe auch

- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
- [Typen](./index.md)
- [Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
