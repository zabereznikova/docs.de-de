---
title: SqlStreamChars. Write (Char [], Int32, Int32)-Methode (System. Data. SqlTypes)
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
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395576"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>SqlStreamChars. Write (Char [], Int32, Int32)-Methode

Schreibt beim Überschreiben in einer abgeleiteten Klasse eine Sequenz von Zeichen in den aktuellen Stream und erhöht die aktuelle Position in diesem Stream um die Anzahl der geschriebenen Zeichen. Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll. Sie ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parameter

`buffer`  
Ein Char-Array, das geschrieben werden soll.

`offset`  
Ein Offset relativ zum Ursprung.

`count`  
Die Anzahl der Zeichen, die in den aktuellen Stream geschrieben werden sollen.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Write`-Methode ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in "System. Data. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
