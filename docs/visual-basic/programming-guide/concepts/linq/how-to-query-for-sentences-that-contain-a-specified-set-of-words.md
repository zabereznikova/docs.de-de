---
title: "Gewusst wie: Abfragen von Sätzen, die eine angegebene Gruppe von Wörtern (LINQ) (Visual Basic) enthalten | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31561d586c9c05f502002efdfc455acb55159fed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a>How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic) (Gewusst wie: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))
Dieses Beispiel zeigt, wie Sie Sätze in einer Textdatei, die Übereinstimmungen für jedes einen bestimmten Satz von Wörtern enthalten. Obwohl das Array von Suchbegriffen in diesem Beispiel wird hartcodiert ist, können sie auch zur Laufzeit dynamisch aufgefüllt werden. In diesem Beispiel gibt die Abfrage die Sätze, die die Wörter "In der Vergangenheit" enthalten "Daten" und "integriert".  
  
## <a name="example"></a>Beispiel  
  
```vb  
Class FindSentences  
  
    Shared Sub Main()  
        Dim text As String = "Historically, the world of data and the world of objects " &   
        "have not been well integrated. Programmers work in C# or Visual Basic " &   
        "and also in SQL or XQuery. On the one side are concepts such as classes, " &   
        "objects, fields, inheritance, and .NET Framework APIs. On the other side " &   
        "are tables, columns, rows, nodes, and separate languages for dealing with " &   
        "them. Data types often require translation between the two worlds; there are " &   
        "different standard functions. Because the object world has no notion of query, a " &   
        "query can only be represented as a string without compile-time type checking or " &   
        "IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " &   
        "objects in memory is often tedious and error-prone."  
  
        ' Split the text block into an array of sentences.  
        Dim sentences As String() = text.Split(New Char() {".", "?", "!"})  
  
        ' Define the search terms. This list could also be dynamically populated at runtime  
        Dim wordsToMatch As String() = {"Historically", "data", "integrated"}  
  
        ' Find sentences that contain all the terms in the wordsToMatch array  
        ' Note that the number of terms to match is not specified at compile time  
        Dim sentenceQuery = From sentence In sentences   
                            Let w = sentence.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                   StringSplitOptions.RemoveEmptyEntries)   
                            Where w.Distinct().Intersect(wordsToMatch).Count = wordsToMatch.Count()   
                            Select sentence  
  
        ' Execute the query  
        For Each str As String In sentenceQuery  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Class  
' Output:  
' Historically, the world of data and the world of objects have not been well integrated  
```  
  
 Die Abfrage funktioniert, indem zuerst den Text in Sätze aufgeteilt, und Teilen dann Sätze in ein Array von Zeichenfolgen, die die einzelnen Wörter enthalten. Für jedes dieser Arrays die <xref:System.Linq.Enumerable.Distinct%2A>-Methode entfernt alle doppelten Wörter, und dann führt die Abfrage eine <xref:System.Linq.Enumerable.Intersect%2A>Vorgang auf dem Word-Array und die `wordsToMatch` Array.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Distinct%2A> Wenn die Anzahl der Schnittmenge identisch mit der Anzahl ist der `wordsToMatch` Array alle gefundenen Wörter und der ursprüngliche Satz zurückgegeben.  
  
 Im Aufruf von <xref:System.String.Split%2A>, die Satzzeichen als Trennzeichen verwendet, um sie aus der Zeichenfolge zu entfernen.</xref:System.String.Split%2A> Wenn Sie nicht, z. B. eine Zeichenfolge "Historisch" verfügen, die nicht übereinstimmt, "Historisch" in der `wordsToMatch` Array. Sie müssen möglicherweise zusätzliche Trennzeichen, abhängig von den Satzzeichen im Quelltext verwenden.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
