---
title: "Gewusst wie: Auffüllen einer XML-Struktur aus dem Dateisystem (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 34eec79e-7945-4ba8-9f74-d05bb8ec67f6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8119c134612aaf03e22644d34d758933a902339
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-visual-basic"></a><span data-ttu-id="28f3e-102">Gewusst wie: Auffüllen einer XML-Struktur aus dem Dateisystem (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28f3e-102">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>
<span data-ttu-id="28f3e-103">Eine häufige und sinnvolle Anwendung von XML-Strukturen besteht in deren Verwendung als hierarchischer Name/Wert-Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="28f3e-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="28f3e-104">Sie können eine XML-Struktur mit hierarchischen Daten auffüllen und die Struktur dann abfragen, transformieren und bei Bedarf serialisieren.</span><span class="sxs-lookup"><span data-stu-id="28f3e-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="28f3e-105">In diesem Verwendungsszenario ist ein großer Teil der XML-spezifischen Semantik, wie das Namespace- und Leerraumverhalten, ohne Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="28f3e-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="28f3e-106">Die XML-Struktur wird stattdessen als kleine hierarchische Datenbank für einen einzelnen Benutzer verwendet, die im Arbeitsspeicher gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="28f3e-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28f3e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28f3e-107">Example</span></span>  
 <span data-ttu-id="28f3e-108">Das folgende Beispiel füllt mit Rekursion eine XML-Struktur aus dem lokalen Dateisystem auf.</span><span class="sxs-lookup"><span data-stu-id="28f3e-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="28f3e-109">Anschließend fragt es die Struktur ab, indem es die Gesamtgröße aller Dateien in der Struktur berechnet.</span><span class="sxs-lookup"><span data-stu-id="28f3e-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```vb  
Module Module1  
    Function CreateFileSystemXmlTree(ByVal source As String) As XElement  
        Dim di As DirectoryInfo = New DirectoryInfo(source)  
        Return <Dir Name=<%= di.Name %>>  
                   <%= From d In Directory.GetDirectories(source) _  
                       Select CreateFileSystemXmlTree(d) %>  
                   <%= From fi In di.GetFiles() _  
                       Select <File>  
                                  <Name><%= fi.Name %></Name>  
                                  <Length><%= fi.Length %></Length>  
                              </File> %>  
               </Dir>  
    End Function  
  
    Sub Main()  
        Dim fileSystemTree As XElement = CreateFileSystemXmlTree("C:/Tmp")  
        Console.WriteLine(fileSystemTree)  
        Console.WriteLine("------")  
        Dim totalFileSize As Long = _  
            ( _  
                From f In fileSystemTree...<File> _  
                Select CLng(f.<Length>(0)) _  
            ).Sum()  
        Console.WriteLine("Total File Size:{0}", totalFileSize)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="28f3e-110">Dieses Beispiel führt zu einer Ausgabe, die der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="28f3e-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="28f3e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28f3e-111">See Also</span></span>  
 [<span data-ttu-id="28f3e-112">Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28f3e-112">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
