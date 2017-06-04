---
title: "Behandlung von Leerr&#228;umen und signifikanten Leerr&#228;umen beim Laden des DOM | Microsoft Docs"
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
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Behandlung von Leerr&#228;umen und signifikanten Leerr&#228;umen beim Laden des DOM
Beim Laden des Dokuments können Sie festlegen, dass Leerraum beibehalten wird und in der Dokumentstruktur **XmlWhitespace**\-Knoten erstellt werden.  Legen Sie die **PreserveWhitespace**\-Eigenschaft auf "true" fest, wenn Leerraumknoten erstellen werden sollen.  Wenn die Eigenschaft auf **false** festgelegt wird \(Standardeinstellung\), werden keine Leerraumknoten erstellt.  Knoten für signifikante Leerräume bleiben stets erhalten, und **XmlSignificantWhitespace**\-Knoten werden ungeachtet der Einstellung des **PreserveWhitespace**\-Flags stets im Speicher erstellt, um diese Daten darzustellen.  
  
 Wenn das Dokument aus einem Reader geladen wird, beeinflusst die Einstellung der **PreserveWhitespace**\-Eigenschaft für die **XmlDocument**\-Klasse nur dann das Erstellen von **XmlWhitespace**\-Knoten, wenn die **WhitespaceHandling**\-Eigenschaft des **XmlTextReader** nicht auf **WhitespaceHandling.None** festgelegt ist.  Der Wert der **WhitespaceHandling**\-Eigenschaft des Readers hat Vorrang vor der Einstellung dieses Flags für das **XmlDocument**.  Weitere Informationen zu **XmlSignificantWhitespace** finden Sie unter [XmlSignificantWhitespace\-Klasse](frlrfSystemXmlXmlSignificantWhitespaceClassTopic).  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)