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
ms.openlocfilehash: 499522a11cac744c14ac32cf3bfe485a46b19d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675311"
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