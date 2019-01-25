---
title: '&#39;&lt;Attribut&gt; &#39; kann nicht angewendet werden, da das Format der GUID &#39; &lt;Anzahl&gt; &#39; ist nicht richtig'
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 85b8c9dcccbb307d8a744e33a5f1d4b1775fda04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623663"
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39;&lt;Attribut&gt; &#39; kann nicht angewendet werden, da das Format der GUID &#39; &lt;Anzahl&gt; &#39; ist nicht richtig
Ein `COMClassAttribute` -Attributblock gibt einen global eindeutigen Bezeichner (GUID), die nicht das richtige Format für eine GUID entspricht. `COMClassAttribute` verwendet GUIDs zur eindeutigen Identifizierung der Klasse, die Schnittstelle und das Erstellungsereignis an.  
  
 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Er ist wird vom Microsoft-Hilfsprogrammen wie uuidgen.exe generiert und zeitlich und größenmäßig eindeutig sein.  
  
 **Fehler-ID:** BC32500  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie die richtige GUID oder den GUIDs zur Identifizierung des COM-Objekts erforderlich.  
  
2.  Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Guid>
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

