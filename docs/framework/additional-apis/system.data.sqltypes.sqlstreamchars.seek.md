---
title: SqlStreamChars.Seek ("Int64", "SeekOrigin")-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: aab3195ec0d300a7f001f98f2d646c85be939356
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152553"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>SqlStreamChars.Seek ("Int64", "SeekOrigin")-Methode

Legt beim Überschreiben in einer abgeleiteten Klasse die Position im aktuellen Stream fest. Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parameter

`offset`\
Ein Byteoffset relativ zum `origin`.

`origin`\
Einer der Enumerationswerte, der den Bezugspunkt, von dem aus die neue Position ermittelt angibt.

## <a name="returns"></a>Rückgabe

<xref:System.Int32>\
Die neue Position innerhalb des aktuellen Streams.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Seek` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.