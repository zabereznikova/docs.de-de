---
title: Objektvergleich mit "XmlNameTable"
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
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd1a3bad69499b4804299adecabad3a43b5eab1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="1cd51-102">Objektvergleich mit "XmlNameTable"</span><span class="sxs-lookup"><span data-stu-id="1cd51-102">Object Comparison Using XmlNameTable</span></span>
<span data-ttu-id="1cd51-103">**XmlDocuments**beim Erstellen eine Namenstabelle, die speziell für das Dokument erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1cd51-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="1cd51-104">XML-Datei in das Dokument geladen ist, oder Erstellen von Elementen oder Attributen erstellt werden, gelten die Attribut- und Elementnamen in der **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="1cd51-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="1cd51-105">Sie können auch erstellen eine **XmlDocument** mithilfe eines vorhandenen **NameTable** aus einem anderen Dokument.</span><span class="sxs-lookup"><span data-stu-id="1cd51-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="1cd51-106">Wenn **XmlDocuments** werden erstellt, mit dem Konstruktor, verwendet eine **XmlNameTable** Parameter hat Zugriff auf den Knotennamen, Namespaces und Präfixen, die bereits in gespeichert, das Dokument der  **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="1cd51-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="1cd51-107">Nachdem die Namen in der Tabelle gespeichert sind, können Sie rasch mithilfe eines Objektvergleichs anstelle eines Zeichenfolgenvergleichs verglichen werden; dies gilt unabhängig von der Verfahrensweise zum Laden der Namenstabelle mit Namen.</span><span class="sxs-lookup"><span data-stu-id="1cd51-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="1cd51-108">Zeichenfolgen können auch hinzugefügt werden, um die Tabelle mit den <xref:System.Xml.NameTable.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cd51-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="1cd51-109">Im folgenden Codebeispiel wird gezeigt, eine Namenstabelle erstellt wird und die Zeichenfolge **MyString** zur Tabelle hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1cd51-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="1cd51-110">Danach ein **XmlDocument** wird mit dieser Tabelle und die Namen der Element- und Attributnamen in erstellt **Myfile.xml** der vorhandenen Namenstabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd51-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 <span data-ttu-id="1cd51-111">Im folgenden Codebeispiel wird gezeigt, wie ein Dokument erstellt wird, diesem zwei neue Elemente hinzugefügt werden, die dadurch auch der Namenstabelle des Dokuments hinzugefügt werden, und wie ein Objektvergleich der Namen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1cd51-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 <span data-ttu-id="1cd51-112">Das oben beschriebene Szenario einer Namenstabelle, die zwischen zwei Dokumenten übergeben wird, ist typisch für die wiederholte Verarbeitung gleicher Dokumenttypen. Ein Beispiel hierfür sind Bestellformulare auf E-Commerce-Seiten, die einem XSD-Schema (XML Schema Definition Language) oder einer DTD (Document Type Definition) entsprechen und die gleichen, sich wiederholenden Zeichenfolgen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1cd51-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="1cd51-113">Das Verwenden der gleichen Namenstabelle führt zu einer Leistungssteigerung, da der gleiche Elementname in mehreren Dokumenten vorkommt.</span><span class="sxs-lookup"><span data-stu-id="1cd51-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd51-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cd51-114">See Also</span></span>  
 [<span data-ttu-id="1cd51-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="1cd51-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
