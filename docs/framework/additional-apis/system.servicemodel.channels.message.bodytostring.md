---
title: Message. bodydestring-Methode (System. Service Model. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 7b0b56bfda1c0c37f43f95e9684d3b4042c1b97c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451311"
---
# <a name="messagebodytostring-method"></a>Message. bodydestring-Methode

Konvertiert den Nachrichtentext in eine Zeichenfolge, indem die <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Parameter

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Der Writer, der verwendet wird, um den Nachrichtentext in eine Zeichenfolge zu konvertieren.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `Message.BodyToString`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Voraussetzungen

**Namespace:** <xref:System.ServiceModel.Channels>

**Assembly:** System. Service Model. dll

**.NET Framework Versionen:** Verfügbar seit 3,0.
