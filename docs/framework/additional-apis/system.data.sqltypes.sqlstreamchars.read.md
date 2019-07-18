---
title: SqlStreamChars.Read (Char [], Int32, Int32)-Methode (System.Data.SqlTypes)
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
ms.openlocfilehash: df715f622f874b3c9297c421eab9f4c7504e696b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634320"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars.Read(Char[], Int32, Int32) Method

Ruft beim Überschreiben in einer abgeleiteten Klasse liest Sie die nächste Gruppe von Zeichen aus dem Eingabestream. Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll. Es ist für die Verwendung durch SQL Server vorgesehen. Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parameter

`buffer`\
Ein Char-Array gelesen werden soll.

`offset`\
Ein Offset relativ zum Ursprung.

`count`\
Die Anzahl der Zeichen aus dem aktuellen Stream gelesen werden.

## <a name="returns"></a>Rückgabe

<xref:System.Int32>\
Die Gesamtanzahl der in den Puffer gelesenen Zeichen.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SqlStreamChars.Read` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Data.SqlTypes>

**Assembly:** System.Data (in "System.Data.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
