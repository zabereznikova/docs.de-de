---
title: Objektvergleich mit "XmlNameTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
ms.openlocfilehash: 1e47bee50f7fa51df82bb37ed3049765f8f360d2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830076"
---
# <a name="object-comparison-using-xmlnametable"></a>Objektvergleich mit "XmlNameTable"
**XmlDocuments** weisen beim Erstellen eine für dieses spezifische Dokument erstellte Namenstabelle auf. Beim Laden von XML in das Dokument oder beim Erstellen von Elementen oder Attributen werden Attribut- und Elementnamen in die **XmlNameTable** eingefügt. Sie können auch ein **XmlDocument** unter Verwendung einer vorhandenen **NameTable** aus einem anderen Dokument erstellen. Beim Erstellen von **XmlDocuments** unter Verwendung eines Konstruktors, der einen **XmlNameTable**-Parameter annimmt, verfügt das Dokument über Zugriff auf die bereits in der **XmlNameTable** gespeicherten Namen der Knoten, Namespaces und Präfixe. Nachdem die Namen in der Tabelle gespeichert sind, können Sie rasch mithilfe eines Objektvergleichs anstelle eines Zeichenfolgenvergleichs verglichen werden; dies gilt unabhängig von der Verfahrensweise zum Laden der Namenstabelle mit Namen. Mit <xref:System.Xml.NameTable.Add%2A> können der Namenstabelle auch Zeichenfolgen hinzugefügt werden. Im folgenden Codebeispiel wird veranschaulicht, wie eine Namenstabelle erstellt wird und wie dieser Tabelle die Zeichenfolge **MyString** hinzugefügt wird. Anschließend wird unter Verwendung dieser Tabelle ein **XmlDocument** erstellt, und die Element- und Attributnamen in **Myfile.xml** werden der vorhandenen Namenstabelle hinzugefügt.  
  
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

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
