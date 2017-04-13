---
title: "&#220;berpr&#252;fen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten | Microsoft Docs"
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
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# &#220;berpr&#252;fen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
Das Dokumentobjektmodell \(DOM\) überprüft beim Erstellen neuer Element\- oder Attributknoten die Gültigkeit der Namen.  Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst.  Wenn Sie sicherstellen möchten, dass die Namen gültig und korrekt codiert sind, müssen Sie diese mithilfe der **XmlConvert**\-Klasse codieren und auf Anwendungsebene wieder decodieren.  Die in **XmlWriter** enthaltenen Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML\-Code generiert wird.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)