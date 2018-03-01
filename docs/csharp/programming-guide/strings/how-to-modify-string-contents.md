---
title: "Gewusst wie: Ändern von Zeichenfolgeninhalten (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>Gewusst wie: Ändern von Zeichenfolgeninhalten (C#-Programmierhandbuch)
Da Zeichenfolgen *unveränderlich* sind, ist es nicht möglich (ohne unsicheren Code zu verwenden), den Wert eines Zeichenfolgenobjekts zu verändern, nachdem es erstellt wurde. Es gibt jedoch viele Möglichkeiten, den Wert einer Zeichenfolge zu ändern und das Ergebnis in einem neuen Zeichenfolgenobjekt zu speichern. Die <xref:System.String?displayProperty=nameWithType>-Klasse enthält Methoden, die eine Eingabezeichenfolge verarbeiten und ein neues Zeichenfolgenobjekt zurückgeben. In vielen Fällen können Sie das neue Objekt der Variablen zuweisen, die die ursprüngliche Zeichenfolge enthalten hat. Die <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Klasse stellt zusätzliche Methoden bereit, die auf ähnliche Weise funktionieren. Die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse stellt einen Puffer aus Zeichen bereit, die Sie „direkt“ ändern können. Sie rufen die <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>-Methode auf, um ein neues Zeichenfolgenobjekt zu erstellen, das die aktuellen Inhalte des Puffers enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Möglichkeiten, eine Teilzeichenfolgen in einer angegebenen Zeichenfolge zu ersetzen oder zu entfernen.  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Um auf die einzelnen Zeichen in einer Zeichenfolge mithilfe der Arraynotation zuzugreifen, können Sie das <xref:System.Text.StringBuilder>-Objekt verwenden, das den `[]`-Operator für den Zugriff auf den internen Zeichenpuffer überlädt. Sie können auch die Zeichenfolge mithilfe der <xref:System.String.ToCharArray%2A>-Methode in ein Array von Zeichen konvertieren. Im folgenden Beispiel wird `ToCharArray` zum Erstellen des Arrays verwendet. Einige Elemente dieses Arrays werden dann geändert. Ein Zeichenfolgenkonstruktor, der ein char-Array als Eingabeparameter verwendet, wird dann zum Erstellen einer neuen Zeichenfolge aufgerufen.  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel wird für diese seltenen Fälle bereitgestellt, in denen Sie eine Zeichenfolge direkt verändern sollen, indem Sie einen unsicheren Code auf ähnliche Weise wie char-Array in C verwenden. Das Beispiel zeigt, wie Sie auf die einzelnen Zeichen „direkt“ mithilfe des festgelegten Schlüsselworts zugreifen. Darüber hinaus wird ein möglicher Nebeneffekt unsicherer Vorgänge auf Zeichenfolgen gezeigt, die daraus entstehen, dass der C#-Compiler Zeichenfolgen intern speichert (hält). Im Allgemeinen sollten Sie dieses Verfahren nicht verwenden, es sei denn, es ist unbedingt notwendig.  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)
