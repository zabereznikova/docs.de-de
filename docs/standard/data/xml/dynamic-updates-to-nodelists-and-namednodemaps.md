---
title: "Dynamische Updates von &quot;NodeLists&quot; und &quot;NamedNodeMaps&quot; | Microsoft Docs"
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
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Dynamische Updates von &quot;NodeLists&quot; und &quot;NamedNodeMaps&quot;
Da die **XmlNodeList** und die **XmlNamedNodeMap** eine Knotengruppe enthalten, aber das XML\-Dokument in den Speicher geladen und verändert wird, müssen die vom W3C definierten Statusangaben, die diese Objekte mit den Knotengruppen haben können, dynamisch sein.  Anders ausgedrückt: Wenn das zugrunde liegende Dokument geändert wird, sollten sich auch die Daten in diesen beiden Objekten ändern.  Dies ist der Fall bei einer **XmlNodeList**, die alle untergeordneten Elemente eines bestimmten Elements enthält \(angenommen, dieses Element ist X\). In diesem Fall fügen Sie dem Dokument ein weiteres Element Q unterhalb des Elements X hinzu.  Das neue Element Q sollte ebenfalls zur Auflistung der **XmlNodeList** hinzugefügt worden sein.  Dies gilt auch umgekehrt.  Wenn der **XmlNodeList** ein Knoten hinzugefügt wird, wird auch das zugrunde liegende Dokument aktualisiert.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)