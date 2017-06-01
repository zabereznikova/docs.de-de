---
title: "&#196;ndern der Eigenschaften von Namespacepr&#228;fixen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# &#196;ndern der Eigenschaften von Namespacepr&#228;fixen
Mit der **XmlNode**\-Klasse können Sie das Namespacepräfix ändern, das mit einem bestimmten Knoten verknüpft ist.  Im folgenden Code wird beispielsweise die Änderung des Präfixes eines Elements dargestellt.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Ausgabe**  
  
```  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 Wenn Sie das Präfix eines Knotens ändern, ändert sich dessen Namespace dadurch nicht.  Der Namespace kann nur bei der Erstellung des Knotens festgelegt werden.  Wenn die Struktur erhalten bleiben soll, können neue Namespaceattribute nicht mit übernommen werden, damit die Anforderungen für das festgelegte Präfix erfüllt werden.  	Wenn der neue Namespace nicht erstellt werden kann, wird das Präfix geändert, sodass der Knoten seinen lokalen Namen und Namespace beibehält.  Im folgenden Beispiel wird dargestellt, wie ein Namespaceattribut hinzugefügt wird.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Ausgabe**  
  
```  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 Wenn die Struktur als Folge des Aufrufs von **doc.InnerXml** in Form einer Zeichenfolge erhalten blieb, wurde das `xmlns:a='123'`\-Attribut hinzugefügt, damit der Namespace des `test`\-Elements beibehalten wird.  Er war und bleibt `'123'`.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)