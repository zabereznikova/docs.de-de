---
title: 'Gewusst wie: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie einen anonymen Typ in einem Abfrageausdruck in C# verwenden, um einige der Eigenschaften eines Quellelements zurückzugeben.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 882d94bc82527c14bd6c038f4bf574c2211b9089
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864370"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Gewusst wie: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch)
Verwenden Sie einen anonymen Typ in einem Abfrageausdruck, wenn die folgenden Bedingungen beide erfüllt sind:  
  
- Sie möchte nur manche der Eigenschaften jedes Quellelements zurückgeben.  
  
- Sie müssen die Abfrageergebnisse nicht außerhalb des Geltungsbereichs der Methode speichern, in der die Abfrage ausgeführt wird.  
  
 Wenn Sie nur eine Eigenschaft oder ein Feld jeder Quelldatei zurückgeben möchten, können Sie dazu den Punktoperator in der `select`-Klausel verwenden. Wenn Sie z.B. die `ID` jedes `student` zurückgeben möchten, schreiben Sie die `select`-Klausel wie folgt:  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erfahren Sie, wie Sie einen anonymen Typ verwenden können, um lediglich eine Teilmenge der Eigenschaften jedes Quellelements zurückzugeben, das die angegebenen Bedingungen erfüllt.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Beachten Sie, dass der anonyme Typ den Namen des Quellelements für dessen Eigenschaften verwendet, wenn keine Namen angegeben sind. Um die Eigenschaften im anonymen Typen zu benennen, schreiben Sie die `select`-Anweisung wie folgt:  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Wenn Sie dies mit vorherigem Beispiel durchführen möchten, müssen Sie die `Console.WriteLine`-Anweisung anpassen:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
Zum Ausführen dieses Codes müssen Sie die Klasse kopieren und in eine C#-Konsolenanwendung mit einer `using`-Anweisung für „System.Linq“ einfügen.
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Anonyme Typen](./anonymous-types.md)
- [LINQ in C#](../../linq/index.md)
