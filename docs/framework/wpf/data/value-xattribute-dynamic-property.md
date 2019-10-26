---
title: Value (dynamische XAttribute-Eigenschaft)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920975"
---
# <a name="value-xattribute-dynamic-property"></a>Value (dynamische XAttribute-Eigenschaft)

Ruft den Wert des XML-Attributs ab oder legt ihn fest.

## <a name="syntax"></a>Syntax

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Ein <xref:System.String>-Objekt, das den Wert dieses Attributs enthält.

## <a name="exceptions"></a>Ausnahmen

|Ausnahmetyp|Bedingung|
| - |---------------|
|<xref:System.ArgumentNullException>|Wenn dieser Ausnahmetyp festgelegt wird, ist `value` `null`.|

## <a name="remarks"></a>Hinweise

Diese Eigenschaft entspricht der <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft der <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>-Klasse, wobei diese dynamische Eigenschaft auch Änderungsbenachrichtigungen unterstützt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Dynamische Eigenschaften der XAttribute-Klasse](value-xattribute-dynamic-property.md)
- [Attribut](attribute-xelement-dynamic-property.md)
