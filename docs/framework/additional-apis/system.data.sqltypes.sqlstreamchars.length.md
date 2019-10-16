---
title: SqlStreamChars. length-Eigenschaft (System. Data. SqlTypes)
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
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395604"
---
# <a name="sqlstreamcharslength-property"></a>SqlStreamChars. length (Eigenschaft)

Ruft beim Überschreiben in einer abgeleiteten Klasse die Länge des aktuellen Streams ab. Die Assembly, die diese Eigenschaft enthält, hat eine Friend-Beziehung mit SQLAccess. dll. Sie ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.

## <a name="syntax"></a>Syntax

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>Eigenschafts Wert

<xref:System.Int64>\
Die Länge des Streams.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Length`-Eigenschaft ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in "System. Data. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
