---
title: "Ändern von Namespacedeklarationen in einem XML-Dokument"
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
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Ändern von Namespacedeklarationen in einem XML-Dokument
Die **XmlDocument** macht Namespacedeklarationen und **Xmlns** Attribute als Teil des Dokumentobjektmodells. Diese werden gespeichert, der **XmlDocument**, sodass, wenn Sie das Dokument zu speichern, können sie den Speicherort dieser Attribute beibehalten. Änderung dieser Attribute hat keine Auswirkung auf die **Namen**, **NamespaceURI**, und **Präfix** Eigenschaften anderer Knoten bereits in der Struktur. Angenommen, wenn Sie das folgende Dokument laden und dann die `test` Element verfügt über **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Wenn Sie entfernen die `xmlns` -Attribut wie folgt die `test` Element immer noch die **NamespaceURI** von `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Ebenso, wenn Sie ein anderes hinzufügen `xmlns` -Attribut auf die `doc` -Element wie folgt, und dann die `test` Element immer noch **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Aus diesem Grund ändern `xmlns` Attribute haben keinen Einfluss, bis Sie speichern und laden die **XmlDocument** Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
