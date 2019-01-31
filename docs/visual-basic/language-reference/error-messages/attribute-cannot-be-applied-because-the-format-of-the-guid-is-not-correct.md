---
title: <attribute> kann nicht angewendet werden, da das Format von GUID "<number>" falsch ist.
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 1e92c77e6138bbd546d9b837e095e41d5dfaf30c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279863"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>"\<Attribut >' kann nicht angewendet werden, da das Format der GUID '\<Anzahl >' ist nicht richtig
Ein `COMClassAttribute` -Attributblock gibt einen global eindeutigen Bezeichner (GUID), die nicht das richtige Format für eine GUID entspricht. `COMClassAttribute` verwendet GUIDs zur eindeutigen Identifizierung der Klasse, die Schnittstelle und das Erstellungsereignis an.  
  
 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Er ist wird vom Microsoft-Hilfsprogrammen wie uuidgen.exe generiert und zeitlich und größenmäßig eindeutig sein.  
  
 **Fehler-ID:** BC32500  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie die richtige GUID oder den GUIDs zur Identifizierung des COM-Objekts erforderlich.  
  
2.  Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Guid>
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

