---
title: SqlStreamChars. Read (Char [], Int32, Int32)-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395749"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars. Read (Char [], Int32, Int32)-Methode

Liest beim Überschreiben in einer abgeleiteten Klasse die nächsten Zeichensätze aus dem Eingabestream. Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll. Sie ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parameter

`buffer`\
Ein zu lesende Char-Array.

`offset`\
Ein Offset relativ zum Ursprung.

`count`\
Die Anzahl der Zeichen, die aus dem aktuellen Stream gelesen werden sollen.

## <a name="returns"></a>Rückgabe

<xref:System.Int32>\
Die Gesamtanzahl der in den Puffer gelesenen Zeichen.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Read`-Methode ist privat und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in "System. Data. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
