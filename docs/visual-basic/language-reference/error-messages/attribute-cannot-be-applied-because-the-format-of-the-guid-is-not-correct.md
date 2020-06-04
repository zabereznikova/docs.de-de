---
title: <attribute> kann nicht angewendet werden, da das Format von GUID "<number>" falsch ist.
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 554c38c8f44999feba4cfa04d58ce2f07e955eb1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409919"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>\<attribute> kann nicht angewendet werden, da das Format von GUID "\<number>" falsch ist.

Ein- `COMClassAttribute` Attribut Block gibt eine Globally Unique Identifier (GUID) an, die nicht dem richtigen Format für eine GUID entspricht. `COMClassAttribute`verwendet GUIDs, um die-Klasse, die-Schnittstelle und das Erstellungs Ereignis eindeutig zu identifizieren.  
  
 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Sie wird von Microsoft-Hilfsprogrammen wie "uuidgen. exe" generiert und ist im Raum und in der Zeit garantiert eindeutig.  
  
 **Fehler-ID:** BC32500  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Bestimmen Sie die richtige GUID oder GUIDs, die zum Identifizieren des COM-Objekts erforderlich sind.  
  
2. Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Guid>
- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
