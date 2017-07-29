---
title: 'Gewusst wie: Analysieren von Zeichenfolgen mithilfe von String.Split (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0ef96f1cb074c32208457c192d53c69d95a102d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a>Gewusst wie: Analysieren von Zeichenfolgen mithilfe von String.Split (C#-Programmierhandbuch)
Im folgenden Codebeispiel wird veranschaulicht, wie eine Zeichenfolge mithilfe der <xref:System.String.Split%2A?displayProperty=fullName> -Methode analysiert werden kann. Als Eingabe akzeptiert <xref:System.String.Split%2A> ein Array von Zeichen, die angeben, durch welche Zeichen relevante Unterzeichenfolgen der Zielzeichenfolge getrennt werden.  Die Funktion gibt ein Array von Unterzeichenfolgen zurück.  
  
 In diesem Beispiel werden Leerzeichen, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die alle in einem Array, das diese Trennzeichen enthält, an <xref:System.String.Split%2A>übergeben werden.  Jedes Wort im Satz der Zielzeichenfolge wird getrennt vom resultierenden Zeichenfolgenarray angezeigt.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Standardmäßig gibt String.Split leere Zeichenfolgen zurück, wenn zwei Trennzeichen in der Zielzeichenfolge nacheinander angezeigt werden.  Sie können einen optionalen StringSplitOptions.RemoveEmptyEntries-Parameter übergeben, um alle leeren Zeichenfolgen in der Ausgabe auszuschließen.  
  
 String.Split kann ein Array von Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        char[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Reguläre Ausdrücke von .NET Framework](https://msdn.microsoft.com/library/hs600312)

