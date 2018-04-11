---
title: '&#39; &lt;Attribut&gt;&#39; kann nicht angewendet werden, da das Format einer GUID &#39;&lt; Anzahl&gt;&#39; ist nicht richtig konfiguriert'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ead07d12064dbe18a1e23d4d1343b1efba1b533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39; &lt;Attribut&gt;&#39; kann nicht angewendet werden, da das Format einer GUID &#39;&lt; Anzahl&gt;&#39; ist nicht richtig konfiguriert
Ein `COMClassAttribute` -Attributblock gibt einen global eindeutigen Bezeichner (GUID), die nicht das richtige Format für eine GUID entspricht. `COMClassAttribute`verwendet GUIDs zur eindeutigen Identifizierung der Klasse, die Schnittstelle und das Erstellungsereignis an.  
  
 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Sie wird von Microsoft-Hilfsprogrammen wie z. B. uuidgen.exe generiert und ist garantiert im Platz und Zeit eindeutig sein.  
  
 **Fehler-ID:** BC32500  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie die richtige GUID oder den GUIDs zur Identifizierung des COM-Objekts erforderlich.  
  
2.  Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Guid>  
[Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

