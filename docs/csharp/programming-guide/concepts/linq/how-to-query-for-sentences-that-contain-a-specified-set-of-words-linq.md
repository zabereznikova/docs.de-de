---
title: 'Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)'
description: In diesem Artikel erfahren Sie, wie Sie mit LINQ in C# in einer Textdatei nach Sätzen suchen, die Übereinstimmungen für die einzelnen Wörter enthalten, die zur Laufzeit aufgefüllt werden können.
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: c334c7948f19fb857709ff04a83e1dae56fc69da
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104523"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a><span data-ttu-id="9c298-103">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="9c298-103">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>
<span data-ttu-id="9c298-104">Dieses Beispiel zeigt, wie Sie Sätze in einer Textdatei suchen, die Übereinstimmungen für jedes Wort einer bestimmten Gruppe von Wörtern enthält.</span><span class="sxs-lookup"><span data-stu-id="9c298-104">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="9c298-105">Obwohl das Array von Suchbegriffen in diesem Beispiel hartcodiert ist, kann es auch zur Laufzeit dynamisch aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="9c298-105">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="9c298-106">In diesem Beispiel gibt die Abfrage die Sätze zurück, die die Wörter „Historically“ (ursprünglich), „data“ (Daten) und „integrated“ (integriert) enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c298-106">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c298-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c298-107">Example</span></span>  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 <span data-ttu-id="9c298-108">Die Abfrage funktioniert, indem der Text zuerst in Sätze aufgeteilt wird. Diese Sätze werden wiederum in ein Array von Zeichenfolgen aufgeteilt, das jedes Wort enthält.</span><span class="sxs-lookup"><span data-stu-id="9c298-108">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="9c298-109">Für jedes dieser Arrays entfernt die <xref:System.Linq.Enumerable.Distinct%2A>-Methode alle Wortduplikate, und anschließend führt die Abfrage einen <xref:System.Linq.Enumerable.Intersect%2A>-Vorgang für das Wortarray und das `wordsToMatch`-Array durch.</span><span class="sxs-lookup"><span data-stu-id="9c298-109">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="9c298-110">Wenn die Anzahl der Schnittmenge identisch mit der Anzahl des `wordsToMatch`-Arrays ist, werden alle gefundenen Wörter in den Wörtern und der ursprüngliche Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9c298-110">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="9c298-111">Im Aufruf von <xref:System.String.Split%2A> werden die Satzzeichen als Trennlinien verwendet, damit sie aus der Zeichenfolge entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="9c298-111">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="9c298-112">Wenn Sie dies nicht getan haben, haben Sie z.B. eine „ursprüngliche“ Zeichenfolge, die „usprünglich“ nicht mit dem `wordsToMatch`-Array übereinstimmen würde.</span><span class="sxs-lookup"><span data-stu-id="9c298-112">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="9c298-113">Sie müssen möglicherweise zusätzliche Trennzeichen verwenden, abhängig von den Satzzeichen, die im Quelltext vorkommen.</span><span class="sxs-lookup"><span data-stu-id="9c298-113">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c298-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9c298-114">Compiling the Code</span></span>  
<span data-ttu-id="9c298-115">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="9c298-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c298-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c298-116">See also</span></span>

- [<span data-ttu-id="9c298-117">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="9c298-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
