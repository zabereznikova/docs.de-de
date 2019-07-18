---
title: SmiOrderProperty.Item-Eigenschaft (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2d8788f610d80c30baf51bff0131f0834d59fcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634577"
---
# <a name="smiorderpropertyitem-property"></a>SmiOrderProperty.Item-Eigenschaft

Ruft die Reihenfolge der Spalten für die Entität ab. Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

## <a name="syntax"></a>Syntax

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a>Eigenschaftswert

Die Spaltenreihenfolge.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SmiOrderProperty.Item` -Eigenschaft ist intern und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieser Eigenschaft in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:Microsoft.SqlServer.Server>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
