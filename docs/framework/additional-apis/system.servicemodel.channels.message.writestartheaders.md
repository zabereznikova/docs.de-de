---
title: Message. Write-starteaders-Methode (System. Service Model. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451287"
---
# <a name="messagewritestartheaders-method"></a>Message. Write-starteaders-Methode

Schreibt den Start Header in eine XML-Datei, indem die <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>-Methode aufgerufen wird.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parameter

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Der Writer, der zum Schreiben des Start Headers in eine XML-Datei verwendet wird.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `Message.WriteStartHeaders`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Voraussetzungen

**Namespace:** <xref:System.ServiceModel.Channels>

**Assembly:** System. Service Model. dll

**.NET Framework Versionen:** Verfügbar seit 3,0.
