---
title: 'Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 27f0df14fef7c261828040d905c9f624f02eddfe
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243828"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch)
Verwenden Sie einen anonymen Typ in einem Abfrageausdruck, wenn die folgenden Bedingungen beide erfüllt sind:  
  
-   Sie möchte nur manche der Eigenschaften jedes Quellelements zurückgeben.  
  
-   Sie müssen die Abfrageergebnisse nicht außerhalb des Geltungsbereichs der Methode speichern, in der die Abfrage ausgeführt wird.  
  
 Wenn Sie nur eine Eigenschaft oder ein Feld jeder Quelldatei zurückgeben möchten, können Sie dazu den Punktoperator in der `select`-Klausel verwenden. Wenn Sie z.B. die `ID` jedes `student` zurückgeben möchten, schreiben Sie die `select`-Klausel wie folgt:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erfahren Sie, wie Sie einen anonymen Typ verwenden können, um lediglich eine Teilmenge der Eigenschaften jedes Quellelements zurückzugeben, das die angegebenen Bedingungen erfüllt.  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Beachten Sie, dass der anonyme Typ den Namen des Quellelements für dessen Eigenschaften verwendet, wenn keine Namen angegeben sind. Um die Eigenschaften im anonymen Typen zu benennen, schreiben Sie die `select`-Anweisung wie folgt:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Wenn Sie dies mit vorherigem Beispiel durchführen möchten, müssen Sie die `Console.WriteLine`-Anweisung anpassen:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen. Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine `using`-Anweisung für „System.Linq“. Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.   
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
- [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)
