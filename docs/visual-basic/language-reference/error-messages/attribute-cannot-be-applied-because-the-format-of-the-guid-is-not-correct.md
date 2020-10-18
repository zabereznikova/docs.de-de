---
title: <attribute> kann nicht angewendet werden, da das Format von GUID "<number>" falsch ist.
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 8e9ac019470685d9fc45342273096d678a29428d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162647"
---
# <a name="bc32500-attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>BC32500: ' \<attribute> ' kann nicht angewendet werden, da das Format der GUID ' \<number> ' nicht korrekt ist.

Ein- `COMClassAttribute` Attribut Block gibt eine Globally Unique Identifier (GUID) an, die nicht dem richtigen Format für eine GUID entspricht. `COMClassAttribute` verwendet GUIDs, um die-Klasse, die-Schnittstelle und das Erstellungs Ereignis eindeutig zu identifizieren.

 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Sie wird von Microsoft-Hilfsprogrammen wie z. b. uuidgen.exe generiert und ist im Raum und in der Zeit garantiert eindeutig.

 **Fehler-ID:** BC32500

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Bestimmen Sie die richtige GUID oder GUIDs, die zum Identifizieren des COM-Objekts erforderlich sind.

2. Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Guid>
- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
