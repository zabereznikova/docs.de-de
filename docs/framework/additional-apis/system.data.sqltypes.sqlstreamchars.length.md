---
title: SqlStreamChars.Length-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8f318f593237dc555d546858152bb03546c8306b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634453"
---
# <a name="sqlstreamcharslength-property"></a>SqlStreamChars.Length-Eigenschaft

Ruft beim Überschreiben in einer abgeleiteten Klasse ruft die Länge des aktuellen Streams ab. Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

## <a name="syntax"></a>Syntax

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>Eigenschaftswert

<xref:System.Int64>\
Die Länge des Streams.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Length` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
