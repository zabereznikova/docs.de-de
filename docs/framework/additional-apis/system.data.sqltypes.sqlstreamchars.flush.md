---
title: SqlStreamChars. Flush-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395624"
---
# <a name="sqlstreamcharsflush-method"></a>SqlStreamChars. Flush-Methode

Löscht beim Überschreiben in einer abgeleiteten Klasse alle Puffer für diesen Stream und veranlasst die Ausgabe aller gepufferten Daten an das zugrunde liegende Gerät. Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll. Sie ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.

## <a name="syntax"></a>Syntax

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Flush`-Methode ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in "System. Data. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
