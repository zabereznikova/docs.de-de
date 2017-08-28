---
title: "Gewusst wie: Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
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
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Gewusst wie: Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken (C#-Programmierhandbuch)
Die <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>-Klasse kann zum durchsuchen von Zeichenfolgen verwendet werden. Diese Suchvorgänge können sehr simpel sein oder voll von regulären Ausdrücken profitieren. Im Folgenden finden Sie zwei Beispiele für das Durchsuchen von Zeichenfolgen mit der <xref:System.Text.RegularExpressions.Regex>-Klasse. Weitere Informationen hierzu finden Sie unter [Reguläre Ausdrücke von .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist eine Konsolenanwendung, die eine einfache Suche von Zeichenfolgen in einem Array durchführt, die nicht auf die Groß- und Kleinschreibung achtet. Die statische Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> führt die Suche mit der zu durchsuchenden Zeichenfolge und einer Zeichenfolge, die das Suchmuster enthält, durch. In diesem Fall wird ein drittes Argument verwendet, um anzugeben, dass die Groß- und Kleinschreibung nicht beachtet werden soll. Weitere Informationen finden Sie unter <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ist eine Konsolenanwendung, die reguläre Ausdrücke verwendet, um das Format jeder Zeichenfolge in einem Array zu überprüfen. Für die Überprüfung ist erforderlich, dass jede Zeichenfolge die Form einer Telefonnummer hat, in der drei Gruppen von Zahlen durch Gedankenstriche getrennt sind, wobei die erste Gruppe drei Zeichen enthält und die dritte vier. Dies erreichen Sie mit dem regulären Ausdruck `^\\d{3}-\\d{3}-\\d{4}$`. Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Reguläre Ausdrücke von .NET Framework](https://msdn.microsoft.com/library/hs600312)   
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

