---
title: SqlStreamChars.CanSeek-Eigenschaft (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 0145fe87e2c8aa3dd40e73f0089fe40b6b6cca30
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152733"
---
# <a name="sqlstreamcharscanseek-property"></a>SqlStreamChars.CanSeek-Eigenschaft

Ruft beim Überschreiben in einer abgeleiteten Klasse ruft einen Wert, der angibt, ob der aktuelle Stream Suchvorgänge unterstützt. Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Eigenschaftswert

<xref:System.Boolean>\
`true` Wenn der aktuelle Stream Suchvorgänge unterstützt; andernfalls `false`.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.CanSeek` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.