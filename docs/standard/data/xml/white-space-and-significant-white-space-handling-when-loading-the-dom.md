---
title: "Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM
Beim Laden des Dokuments können Sie festlegen, dass die Option aus, um Leerraum beizubehalten, und erstellen Sie **XmlWhitespace** Knoten in der Dokumentstruktur. Zum Erstellen von Leerraumknoten legen die **PreserveWhitespace** Eigenschaft auf "true". Wenn die Eigenschaft, um festgelegt wird **"false"**, Hierbei handelt es sich um die Standardeinstellung, Leerraumknoten nicht erstellt werden. Knoten für signifikante Leerräume bleiben stets erhalten, und **XmlSignificantWhitespace** Knoten werden immer im Arbeitsspeicher, um diese Daten unabhängig von der Einstellung der darstellen, erstellt der **PreserveWhitespace** das Flag.  
  
 Wenn das Dokument von einem Reader geladen wird, klicken Sie dann der Festlegen der **PreserveWhitespace** flag der Eigenschaft für die **XmlDocument** Klasse wirkt sich auf die Erstellung von **XmlWhitespace** Knoten nur, wenn die **WhitespaceHandling** Eigenschaft auf die **XmlTextReader** nicht festgelegt ist, um **WhitespaceHandling.None**. Ist der Wert, der die **WhitespaceHandling** Eigenschaft für den Reader an, die Vorrang vor der Einstellung dieses Flags auf enthält die **XmlDocument**. Weitere Informationen zu **XmlSignificantWhitespace**, finden Sie unter <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
