---
title: Ändern von Namespacedeklarationen in einem XML-Dokument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: 95f9c6301f656ad4da5edcfb66521589b9195114
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725364"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Ändern von Namespacedeklarationen in einem XML-Dokument

Das **XmlDocument** macht Namespacedeklarationen und **xmlns**-Attribute als Teil des Dokumentobjektmodells verfügbar. Diese werden im **XmlDocument** gespeichert, sodass der Speicherort dieser Attribute beim Speichern des Dokuments beibehalten werden kann. Eine Änderung dieser Attribute hat keine Auswirkungen auf die Eigenschaften **Name**, **NamespaceURI** und **Prefix** anderer Knoten, die bereits in der Struktur vorhanden sind. Wenn Sie z. B. das folgende Dokument laden, weist das `test`-Element den **NamespaceURI** `123.` auf.  
  
```xml  
<test xmlns="123"/>  
```  
  
 Wenn Sie das `xmlns`-Attribut wie folgt entfernen, weist das `test`-Element weiterhin den **NamespaceURI**`123` auf.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Gleichermaßen weist das `test`-Element weiterhin den **NamespaceURI** `123` auf, wenn Sie dem `doc`-Element wie folgt ein anderes `xmlns`-Attribut hinzufügen.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Änderungen an `xmlns`-Attributen haben daher keine Auswirkungen, solange Sie das **XmlDocument**-Objekt nicht speichern und erneut laden.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
