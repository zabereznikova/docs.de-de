---
title: Message. bodydestring-Methode (System. Service Model. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 9f1f852c0bd82299fd40afe66a5f90cd7c0335cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215508"
---
# <a name="messagebodytostring-method"></a>Message. bodydestring-Methode

Konvertiert den Nachrichtentext in eine Zeichenfolge, indem die <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Parameter

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Der Writer, der verwendet wird, um den Nachrichtentext in eine Zeichenfolge zu konvertieren.

## <a name="remarks"></a>Bemerkungen

> [!WARNING]
> Die `Message.BodyToString`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.ServiceModel.Channels>

**Assembly:** System. Service Model. dll

**.NET Framework Versionen:** Verfügbar seit 3,0.
