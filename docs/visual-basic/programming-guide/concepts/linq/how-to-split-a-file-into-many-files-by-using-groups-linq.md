---
title: 'Gewusst wie: Teilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ)'
ms.date: 07/20/2015
ms.assetid: 5e8b2a2b-0b1d-4933-8a2b-03e91dfaf77f
ms.openlocfilehash: bd210f5119540bd35c18a07a21fc836339222bd0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341358"
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-visual-basic"></a><span data-ttu-id="9d406-102">Vorgehensweise: Aufteilen einer Datei in viele Dateien mithilfe von Gruppen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d406-102">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="9d406-103">Dieses Beispiel zeigt eine Möglichkeit, den Inhalt von zwei Dateien zusammenführen und dann einen Satz von neuen Dateien zu erstellen, die die Daten auf neue Weise organisieren.</span><span class="sxs-lookup"><span data-stu-id="9d406-103">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>

### <a name="to-create-the-data-files"></a><span data-ttu-id="9d406-104">So erstellen Sie die Datendateien</span><span class="sxs-lookup"><span data-stu-id="9d406-104">To create the data files</span></span>

1. <span data-ttu-id="9d406-105">Kopieren Sie diese Namen in eine Textdatei namens „names1.txt“, und speichern Sie sie in Ihrem Projektordner:</span><span class="sxs-lookup"><span data-stu-id="9d406-105">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>

    ```text
    Bankov, Peter
    Holm, Michael
    Garcia, Hugo
    Potra, Cristina
    Noriega, Fabricio
    Aw, Kam Foo
    Beebe, Ann
    Toyoshima, Tim
    Guy, Wey Yuan
    Garcia, Debra
    ```

2. <span data-ttu-id="9d406-106">Kopieren Sie diese Namen in eine Textdatei namens „names2.txt“, und speichern Sie sie in Ihrem Projektordner: Beachten Sie, dass die beiden Dateien einige Namen gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="9d406-106">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>

    ```text
    Liu, Jinghao
    Bankov, Peter
    Holm, Michael
    Garcia, Hugo
    Beebe, Ann
    Gilchrist, Beth
    Myrcha, Jacek
    Giakoumakis, Leo
    McLin, Nkenge
    El Yassir, Mehdi
    ```

## <a name="example"></a><span data-ttu-id="9d406-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d406-107">Example</span></span>

```vb
Class SplitWithGroups

    Shared Sub Main()

        Dim fileA As String() = System.IO.File.ReadAllLines("../../../names1.txt")
        Dim fileB As String() = System.IO.File.ReadAllLines("../../../names2.txt")

        ' Concatenate and remove duplicate names based on
        Dim mergeQuery As IEnumerable(Of String) = fileA.Union(fileB)

        ' Group the names by the first letter in the last name
        Dim groupQuery = From name In mergeQuery
                     Let n = name.Split(New Char() {","})
                     Order By n(0)
                     Group By groupKey = n(0)(0)
                     Into groupName = Group

        ' Create a new file for each group that was created
        ' Note that nested foreach loops are required to access
        ' individual items with each group.
        For Each gGroup In groupQuery
            Dim fileName As String = "..'..'..'testFile_" & gGroup.groupKey & ".txt"
            Dim sw As New System.IO.StreamWriter(fileName)
            Console.WriteLine(gGroup.groupKey)
            For Each item In gGroup.groupName
                Console.WriteLine("   " & item.name)
                sw.WriteLine(item.name)
            Next
            sw.Close()
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Files have been written. Press any key to exit.")
        Console.ReadKey()

    End Sub
End Class
' Console Output:
' A
'    Aw, Kam Foo
' B
'    Bankov, Peter
'    Beebe, Ann
' E
'    El Yassir, Mehdi
' G
'    Garcia, Hugo
'    Garcia, Debra
'    Giakoumakis, Leo
'    Gilchrist, Beth
'    Guy, Wey Yuan
' H
'    Holm, Michael
' L
'    Liu, Jinghao
' M
'    McLin, Nkenge
'    Myrcha, Jacek
' N
'    Noriega, Fabricio
' P
'    Potra, Cristina
' T
'    Toyoshima, Tim
```

<span data-ttu-id="9d406-108">Das Programm schreibt eine separate Datei für jede Gruppe im gleichen Ordner wie die Datendateien.</span><span class="sxs-lookup"><span data-stu-id="9d406-108">The program writes a separate file for each group in the same folder as the data files.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9d406-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9d406-109">Compiling the Code</span></span>

<span data-ttu-id="9d406-110">Erstellen Sie ein Konsolen Anwendungsprojekt in VB.net mit einer `Imports`-Anweisung für den System. Linq-Namespace.</span><span class="sxs-lookup"><span data-stu-id="9d406-110">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d406-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d406-111">See also</span></span>

- [<span data-ttu-id="9d406-112">LINQ und Zeichen folgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d406-112">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="9d406-113">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9d406-113">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
