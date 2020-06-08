---
title: 'Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 144d004d697b84a011cedafc7d07b679ef8852c3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288146"
---
# <a name="how-to-return-a-value-from-a-task"></a>Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe
In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ einen Wert aus der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zurückgeben. Für das Beispiel ist es erforderlich, dass das Verzeichnis "C:\Users\Public\Pictures\Sample Pictures\" vorhanden ist und Dateien enthält.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft sperrt den aufrufenden Thread, bis die Aufgabe abgeschlossen ist.  
  
 Um zu erfahren, wie das Ergebnis eines <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> an eine Fortsetzungsaufgabe übergeben wird, lesen Sie [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Aufgabenbasierte asynchrone Programmierung](task-based-asynchronous-programming.md)
- [Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md)
