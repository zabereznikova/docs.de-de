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
# <a name="object-comparison-using-xmlnametable"></a>Objektvergleich mit "XmlNameTable"
**XmlDocuments**beim Erstellen eine Namenstabelle, die speziell für das Dokument erstellt haben. XML-Datei in das Dokument geladen ist, oder Erstellen von Elementen oder Attributen erstellt werden, gelten die Attribut- und Elementnamen in der **XmlNameTable**. Sie können auch erstellen eine **XmlDocument** mithilfe eines vorhandenen **NameTable** aus einem anderen Dokument. Wenn **XmlDocuments** werden erstellt, mit dem Konstruktor, verwendet eine **XmlNameTable** Parameter hat Zugriff auf den Knotennamen, Namespaces und Präfixen, die bereits in gespeichert, das Dokument der  **XmlNameTable**. Nachdem die Namen in der Tabelle gespeichert sind, können Sie rasch mithilfe eines Objektvergleichs anstelle eines Zeichenfolgenvergleichs verglichen werden; dies gilt unabhängig von der Verfahrensweise zum Laden der Namenstabelle mit Namen. Zeichenfolgen können auch hinzugefügt werden, um die Tabelle mit den <xref:System.Xml.NameTable.Add%2A>. Im folgenden Codebeispiel wird gezeigt, eine Namenstabelle erstellt wird und die Zeichenfolge **MyString** zur Tabelle hinzugefügt wird. Danach ein **XmlDocument** wird mit dieser Tabelle und die Namen der Element- und Attributnamen in erstellt **Myfile.xml** der vorhandenen Namenstabelle hinzugefügt werden.  
  
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
  
 Im folgenden Codebeispiel wird gezeigt, wie ein Dokument erstellt wird, diesem zwei neue Elemente hinzugefügt werden, die dadurch auch der Namenstabelle des Dokuments hinzugefügt werden, und wie ein Objektvergleich der Namen ausgeführt wird.  
  
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
  
 Das oben beschriebene Szenario einer Namenstabelle, die zwischen zwei Dokumenten übergeben wird, ist typisch für die wiederholte Verarbeitung gleicher Dokumenttypen. Ein Beispiel hierfür sind Bestellformulare auf E-Commerce-Seiten, die einem XSD-Schema (XML Schema Definition Language) oder einer DTD (Document Type Definition) entsprechen und die gleichen, sich wiederholenden Zeichenfolgen aufweisen. Das Verwenden der gleichen Namenstabelle führt zu einer Leistungssteigerung, da der gleiche Elementname in mehreren Dokumenten vorkommt.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
