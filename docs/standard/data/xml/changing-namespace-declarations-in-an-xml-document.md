---
title: "&#196;ndern von Namespacedeklarationen in einem XML-Dokument | Microsoft Docs"
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
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# &#196;ndern von Namespacedeklarationen in einem XML-Dokument
Das **XmlDocument** macht Namespacedeklarationen und **xmlns**\-Attribute als Teil des Dokumentobjektmodells verfügbar.  Diese werden im **XmlDocument** gespeichert, sodass der Speicherort dieser Attribute beim Speichern des Dokuments beibehalten werden kann.  Eine Änderung dieser Attribute hat keine Auswirkungen auf die Eigenschaften **Name**, **NamespaceURI** und **Prefix** anderer Knoten, die bereits in der Struktur vorhanden sind.  Wenn Sie z. B. das folgende Dokument laden, weist das `test`\-Element den **NamespaceURI** `123.` auf.  
  
```  
<test xmlns="123"/>  
```  
  
 Wenn Sie das `xmlns`\-Attribut wie folgt entfernen, weist das `test`\-Element weiterhin den **NamespaceURI** `123` auf.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Gleichermaßen weist das `test`\-Element weiterhin den **NamespaceURI** `123` auf, wenn Sie dem `doc`\-Element wie folgt ein anderes `xmlns`\-Attribut hinzufügen.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Änderungen an `xmlns`\-Attributen haben daher keine Auswirkungen, solange Sie das **XmlDocument**\-Objekt nicht speichern und neu laden.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)