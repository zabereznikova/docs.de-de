---
title: 'Vorgehensweise: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
ms.openlocfilehash: 3ff51b0b5f04a44f83db2590bd7005097b1c0161
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323351"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="a9f82-102">Vorgehensweise: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a9f82-102">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>
<span data-ttu-id="a9f82-103">In diesem Beispiel erfahren Sie, wie Sie Daten aus unterschiedlichen Quellen in einer Sequenz aus neuen Typen zusammenführen können.</span><span class="sxs-lookup"><span data-stu-id="a9f82-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9f82-104">Versuchen Sie nicht, Daten im Arbeitsspeicher oder Daten im Dateisystem mit Daten, die sich noch in der Datenbank befinden, zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="a9f82-104">Do not try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="a9f82-105">Derartige domänenübergreifende Verknüpfungen können aufgrund von möglichen unterschiedlichen Definitionen von Verknüpfungsvorgänge für Datenbankabfragen und anderen Quelltypen zu undefinierten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="a9f82-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="a9f82-106">Zusätzlich kann eine derartige Verknüpfung eine Ausnahme außerhalb des Speichers verursachen, wenn die Datenmenge in der Datenbank groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="a9f82-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="a9f82-107">Um Daten aus einer Datenbank mit Daten im Arbeitsspeicher zu verknüpfen, rufen Sie zuerst `ToList` oder `ToArray` in der Datenbankabfrage auf, und führen Sie dann die Verknüpfung in der zurückgegebenen Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="a9f82-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="a9f82-108">So erstellen Sie die Datendatei</span><span class="sxs-lookup"><span data-stu-id="a9f82-108">To create the data file</span></span>  
  
-   <span data-ttu-id="a9f82-109">Kopieren Sie die Dateien „names.csv“ und „scores.csv“ in Ihren Projektordner wie unter [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9f82-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f82-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9f82-110">Example</span></span>  
 <span data-ttu-id="a9f82-111">In folgendem Beispiel erfahren Sie, wie Sie einen benannten Typ `Student` zum Speichern zusammengeführter Daten aus zwei Zeichenfolgeauflistungen, die Arbeitsblätter im .csv-Format simulieren, im Arbeitsspeicher verwenden könne.</span><span class="sxs-lookup"><span data-stu-id="a9f82-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="a9f82-112">Die erste Zeichenfolgeauflistung stellt die Namen der Studenten und deren Matrikelnummer dar, und die zweite Zeichenfolgeauflistung stellt die Matrikelnummer (in der ersten Spalte) und vier Prüfungsergebnisse dar.</span><span class="sxs-lookup"><span data-stu-id="a9f82-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="a9f82-113">Die Matrikelnummer wird als Fremdschlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9f82-113">The ID is used as the foreign key.</span></span>  
  
```csharp  
class Student  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int ID { get; set; }  
    public List<int> ExamScores { get; set; }  
}  
  
class PopulateCollection  
{  
    static void Main()  
    {  
        // These data files are defined in How to: Join Content from   
        // Dissimilar Files (LINQ).  
  
        // Each line of names.csv consists of a last name, a first name, and an  
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
  
        // Each line of scores.csv consists of an ID number and four test   
        // scores, separated by commas. For example, 111, 97, 92, 81, 60  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Merge the data sources using a named type.  
        // var could be used instead of an explicit type. Note the dynamic  
        // creation of a list of ints for the ExamScores member. We skip   
        // the first item in the split string because it is the student ID,   
        // not an exam score.  
        IEnumerable<Student> queryNamesScores =  
            from nameLine in names  
            let splitName = nameLine.Split(',')  
            from scoreLine in scores  
            let splitScoreLine = scoreLine.Split(',')  
            where splitName[2] == splitScoreLine[0]  
            select new Student()  
            {  
                FirstName = splitName[0],  
                LastName = splitName[1],  
                ID = Convert.ToInt32(splitName[2]),  
                ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                              select Convert.ToInt32(scoreAsText)).  
                              ToList()  
            };  
  
        // Optional. Store the newly created student objects in memory  
        // for faster access in future queries. This could be useful with  
        // very large data files.  
        List<Student> students = queryNamesScores.ToList();  
  
        // Display each student's name and exam score average.  
        foreach (var student in students)  
        {  
            Console.WriteLine("The average score of {0} {1} is {2}.",  
                student.FirstName, student.LastName,  
                student.ExamScores.Average());  
        }  
  
        //Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    The average score of Omelchenko Svetlana is 82.5.  
    The average score of O'Donnell Claire is 72.25.  
    The average score of Mortensen Sven is 84.5.  
    The average score of Garcia Cesar is 88.25.  
    The average score of Garcia Debra is 67.  
    The average score of Fakhouri Fadi is 92.25.  
    The average score of Feng Hanying is 88.  
    The average score of Garcia Hugo is 85.75.  
    The average score of Tucker Lance is 81.75.  
    The average score of Adams Terry is 85.25.  
    The average score of Zabokritski Eugene is 83.  
    The average score of Tucker Michael is 92.  
 */  
```  
  
 <span data-ttu-id="a9f82-114">In der [select](../../../../csharp/language-reference/keywords/select-clause.md)-Klausel wird ein Objektinitialisierer zur Instanziierung jedes neuen `Student`-Objekts mithilfe der Daten aus den beiden Quellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9f82-114">In the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>  
  
 <span data-ttu-id="a9f82-115">Wenn Sie die Ergebnisse einer Abfrage nicht speichern müssen, können anonyme Typen praktischer als benannte Typen sein.</span><span class="sxs-lookup"><span data-stu-id="a9f82-115">If you do not have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="a9f82-116">Benannte Typen sind für die Übergabe von Abfrageergebnissen außerhalb der Methode, in der die Abfrage ausgeführt wird, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9f82-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="a9f82-117">In folgendem Beispiel wird die gleiche Aufgabe wie im vorherigen Beispiel ausgeführt; allerdings werden statt benannter anonyme Typen verwendet:</span><span class="sxs-lookup"><span data-stu-id="a9f82-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>  
  
```csharp  
// Merge the data sources by using an anonymous type.  
// Note the dynamic creation of a list of ints for the  
// ExamScores member. We skip 1 because the first string  
// in the array is the student ID, not an exam score.  
var queryNamesScores2 =  
    from nameLine in names  
    let splitName = nameLine.Split(',')  
    from scoreLine in scores  
    let splitScoreLine = scoreLine.Split(',')  
    where splitName[2] == splitScoreLine[0]  
    select new  
    {  
        First = splitName[0],  
        Last = splitName[1],  
        ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                      select Convert.ToInt32(scoreAsText))  
                      .ToList()  
    };  
  
// Display each student's name and exam score average.  
foreach (var student in queryNamesScores2)  
{  
    Console.WriteLine("The average score of {0} {1} is {2}.",  
        student.First, student.Last, student.ExamScores.Average());  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9f82-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a9f82-118">Compiling the Code</span></span>  
 <span data-ttu-id="a9f82-119">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a9f82-119">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f82-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9f82-120">See Also</span></span>  
 [<span data-ttu-id="a9f82-121">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="a9f82-121">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="a9f82-122">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="a9f82-122">Object and Collection Initializers</span></span>](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="a9f82-123">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="a9f82-123">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
