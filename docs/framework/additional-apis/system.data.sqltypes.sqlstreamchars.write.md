---
title: SqlStreamChars.Write (Char [], Int32, Int32)-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4084c7161eaa91d78eab32f1c14624e0032cdfcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705908"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>SqlStreamChars.Write (Char [], Int32, Int32)-Methode

Ruft beim Überschreiben in einer abgeleiteten Klasse schreibt eine Folge von Zeichen in den aktuellen Stream und erhöht die aktuelle Position im Stream um die Anzahl der geschriebenen Zeichen. Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parameter

`buffer`  
Ein Char-Array geschrieben werden soll.

`offset`  
Ein Offset relativ zum Ursprung.

`count`  
Die Anzahl der Zeichen in den aktuellen Stream geschrieben werden.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Write` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
