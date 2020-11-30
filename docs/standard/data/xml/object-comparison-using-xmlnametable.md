---
title: Objektvergleich mit "XmlNameTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
ms.openlocfilehash: 5e0f5de6fd956bcaaf30b592e04c432a5f824c52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734100"
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="012ca-102">Objektvergleich mit "XmlNameTable"</span><span class="sxs-lookup"><span data-stu-id="012ca-102">Object Comparison Using XmlNameTable</span></span>

<span data-ttu-id="012ca-103">**XmlDocuments** weisen beim Erstellen eine für dieses spezifische Dokument erstellte Namenstabelle auf.</span><span class="sxs-lookup"><span data-stu-id="012ca-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="012ca-104">Beim Laden von XML in das Dokument oder beim Erstellen von Elementen oder Attributen werden Attribut- und Elementnamen in die **XmlNameTable** eingefügt.</span><span class="sxs-lookup"><span data-stu-id="012ca-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="012ca-105">Sie können auch ein **XmlDocument** unter Verwendung einer vorhandenen **NameTable** aus einem anderen Dokument erstellen.</span><span class="sxs-lookup"><span data-stu-id="012ca-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="012ca-106">Beim Erstellen von **XmlDocuments** unter Verwendung eines Konstruktors, der einen **XmlNameTable**-Parameter annimmt, verfügt das Dokument über Zugriff auf die bereits in der **XmlNameTable** gespeicherten Namen der Knoten, Namespaces und Präfixe.</span><span class="sxs-lookup"><span data-stu-id="012ca-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="012ca-107">Nachdem die Namen in der Tabelle gespeichert sind, können Sie rasch mithilfe eines Objektvergleichs anstelle eines Zeichenfolgenvergleichs verglichen werden; dies gilt unabhängig von der Verfahrensweise zum Laden der Namenstabelle mit Namen.</span><span class="sxs-lookup"><span data-stu-id="012ca-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="012ca-108">Mit <xref:System.Xml.NameTable.Add%2A> können der Namenstabelle auch Zeichenfolgen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="012ca-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="012ca-109">Im folgenden Codebeispiel wird veranschaulicht, wie eine Namenstabelle erstellt wird und wie dieser Tabelle die Zeichenfolge **MyString** hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="012ca-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="012ca-110">Anschließend wird unter Verwendung dieser Tabelle ein **XmlDocument** erstellt, und die Element- und Attributnamen in **Myfile.xml** werden der vorhandenen Namenstabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="012ca-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
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
  
 <span data-ttu-id="012ca-111">Im folgenden Codebeispiel wird gezeigt, wie ein Dokument erstellt wird, diesem zwei neue Elemente hinzugefügt werden, die dadurch auch der Namenstabelle des Dokuments hinzugefügt werden, und wie ein Objektvergleich der Namen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="012ca-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
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
  
 <span data-ttu-id="012ca-112">Das oben beschriebene Szenario einer Namenstabelle, die zwischen zwei Dokumenten übergeben wird, ist typisch für die wiederholte Verarbeitung gleicher Dokumenttypen. Ein Beispiel hierfür sind Bestellformulare auf E-Commerce-Seiten, die einem XSD-Schema (XML Schema Definition Language) oder einer DTD (Document Type Definition) entsprechen und die gleichen, sich wiederholenden Zeichenfolgen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="012ca-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="012ca-113">Das Verwenden der gleichen Namenstabelle führt zu einer Leistungssteigerung, da der gleiche Elementname in mehreren Dokumenten vorkommt.</span><span class="sxs-lookup"><span data-stu-id="012ca-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012ca-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="012ca-114">See also</span></span>

- [<span data-ttu-id="012ca-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="012ca-115">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
