---
title: Abrufen von geordneten Knoten anhand des Indexes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 13d3077b1536d4e96cb9e4f1f09313dd793a906e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ordered-node-retrieval-by-index"></a><span data-ttu-id="6f702-102">Abrufen von geordneten Knoten anhand des Indexes</span><span class="sxs-lookup"><span data-stu-id="6f702-102">Ordered Node Retrieval by Index</span></span>
<span data-ttu-id="6f702-103">Der World Wide Web Consortium (W3C) XML-Dokument Objekt Model (DOM) beschreibt auch eine NodeList, diese kann eine geordnete Liste von Knoten, im Gegensatz zu den ungeordneten Knotensatz behandelt behandeln die **XmlNamedNodeMap**.</span><span class="sxs-lookup"><span data-stu-id="6f702-103">The World Wide Web Consortium (W3C) XML Document Object Model (DOM) also describes a NodeList, which has the ability to handle an ordered list of nodes, as opposed to the unordered set handled by the **XmlNamedNodeMap**.</span></span> <span data-ttu-id="6f702-104">Die NodeList in Microsoft .NET Framework heißt **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="6f702-104">The NodeList in the Microsoft .NET Framework is called **XmlNodeList**.</span></span> <span data-ttu-id="6f702-105">Methoden und Eigenschaften, die Zurückgeben einer **XmlNodeList** sind:</span><span class="sxs-lookup"><span data-stu-id="6f702-105">Methods and properties that return an **XmlNodeList** are:</span></span>  
  
-   <span data-ttu-id="6f702-106">XmlNode.ChildNodes</span><span class="sxs-lookup"><span data-stu-id="6f702-106">XmlNode.ChildNodes</span></span>  
  
-   <span data-ttu-id="6f702-107">XmlDocument.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="6f702-107">XmlDocument.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="6f702-108">XmlElement.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="6f702-108">XmlElement.GetElementsByTagName</span></span>  
  
-   <span data-ttu-id="6f702-109">XmlNode.SelectNodes</span><span class="sxs-lookup"><span data-stu-id="6f702-109">XmlNode.SelectNodes</span></span>  
  
 <span data-ttu-id="6f702-110">Die **XmlNodeList** verfügt über eine **Anzahl** -Eigenschaft, die verwendet werden kann, um das Durchlaufen der Knoten in Schleifen zu schreiben der **XmlNodeList**, wie im folgenden Codebeispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6f702-110">The **XmlNodeList** has a **Count** property that can be used to write loops to iterate over the nodes in the **XmlNodeList**, as shown in the following code sample:</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 <span data-ttu-id="6f702-111">Zusätzlich zu den **Anzahl** -Eigenschaft, besteht eine **GetEnumerator** -Methode bereit, a, `foreach` -Iteration für die Auflistung von Knoten in der **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="6f702-111">In addition to the **Count** property, there is a **GetEnumerator** method that provides a, `foreach` style iteration over the collection of nodes in the **XmlNodeList**.</span></span> <span data-ttu-id="6f702-112">Im folgenden Codebeispiel wird die Verwendung der `foreach`-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6f702-112">The following code example shows the use of the `foreach` statement.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 <span data-ttu-id="6f702-113">Weitere Informationen zu den verfügbaren Methoden und Eigenschaften für die **XmlNodeList**, finden Sie unter <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="6f702-113">For more information on the methods and properties available on the **XmlNodeList**, see <xref:System.Xml.XmlNodeList>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f702-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f702-114">See Also</span></span>  
 [<span data-ttu-id="6f702-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="6f702-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
