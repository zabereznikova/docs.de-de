---
title: "Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten
Das Dokumentobjektmodell (DOM) überprüft beim Erstellen neuer Element- oder Attributknoten die Gültigkeit der Namen. Wenn die Namen ungültige Zeichen enthalten, wird eine Ausnahme ausgelöst. Um sicherzustellen, dass die Namen sind gültig und codierte ordnungsgemäß, müssen Sie die **XmlConvert** Klasse, um den Namen codieren und auf Anwendungsebene wieder decodieren. Die **"XmlWriter"** Methoden stellen durch weitere Aktionen sicher, dass wohlgeformter XML-Code generiert wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
