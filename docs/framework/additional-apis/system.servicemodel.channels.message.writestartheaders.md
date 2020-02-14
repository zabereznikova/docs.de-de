---
title: Message. Write-starteaders-Methode (System. Service Model. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214864"
---
# <a name="messagewritestartheaders-method"></a>Message. Write-starteaders-Methode

Schreibt den Start Header in eine XML-Datei, indem die <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parameter

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Der Writer, der zum Schreiben des Start Headers in eine XML-Datei verwendet wird.

## <a name="remarks"></a>Bemerkungen

> [!WARNING]
> Die `Message.WriteStartHeaders`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.ServiceModel.Channels>

**Assembly:** System. Service Model. dll

**.NET Framework Versionen:** Verfügbar seit 3,0.
