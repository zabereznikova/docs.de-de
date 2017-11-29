---
title: "How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic) (Gewusst wie: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 523b1e681c97e14f1d0e49b82a426b0e0e54fa1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a>How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic) (Gewusst wie: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))
Dieses Beispiel zeigt, wie Sie Sätze in einer Textdatei suchen, die Übereinstimmungen für jedes Wort einer bestimmten Gruppe von Wörtern enthält. Obwohl das Array von Suchbegriffen in diesem Beispiel hartcodiert ist, kann es auch zur Laufzeit dynamisch aufgefüllt werden. In diesem Beispiel gibt die Abfrage die Sätze zurück, die die Wörter „Historically“ (ursprünglich), „data“ (Daten) und „integrated“ (integriert) enthalten.  
  
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
  
 Die Abfrage funktioniert, indem der Text zuerst in Sätze aufgeteilt wird. Diese Sätze werden wiederum in ein Array von Zeichenfolgen aufgeteilt, das jedes Wort enthält. Für jedes dieser Arrays entfernt die <xref:System.Linq.Enumerable.Distinct%2A>-Methode alle Wortduplikate, und anschließend führt die Abfrage einen <xref:System.Linq.Enumerable.Intersect%2A>-Vorgang für das Wortarray und das `wordsToMatch`-Array durch. Wenn die Anzahl der Schnittmenge identisch mit der Anzahl des `wordsToMatch`-Arrays ist, werden alle gefundenen Wörter in den Wörtern und der ursprüngliche Satz zurückgegeben.  
  
 Im Aufruf von <xref:System.String.Split%2A> werden die Satzzeichen als Trennlinien verwendet, damit sie aus der Zeichenfolge entfernt werden können. Wenn Sie dies nicht getan haben, haben Sie z.B. eine „ursprüngliche“ Zeichenfolge, die „usprünglich“ nicht mit dem `wordsToMatch`-Array übereinstimmen würde. Sie müssen möglicherweise zusätzliche Trennzeichen verwenden, abhängig von den Satzzeichen, die im Quelltext vorkommen.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und einer `Imports`-Anweisung für den System.Linq-Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
