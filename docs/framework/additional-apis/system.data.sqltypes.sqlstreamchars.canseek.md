---
title: SqlStreamChars. CanSeek-Eigenschaft (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395780"
---
# <a name="sqlstreamcharscanseek-property"></a>SqlStreamChars. CanSeek (Eigenschaft)

Ruft beim Überschreiben in einer abgeleiteten Klasse einen Wert ab, der angibt, ob der aktuelle Stream den Suchvorgang unterstützt. Die Assembly, die diese Eigenschaft enthält, hat eine Friend-Beziehung mit SQLAccess. dll. Sie ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Eigenschafts Wert

<xref:System.Boolean>\
`true`, wenn der aktuelle Stream den Suchvorgang unterstützt. Andernfalls `false`.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.CanSeek`-Eigenschaft ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in "System. Data. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
