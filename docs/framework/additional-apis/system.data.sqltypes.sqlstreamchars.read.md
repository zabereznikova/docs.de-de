---
title: SqlStreamChars.Read (Char [], Int32, Int32)-Methode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152533"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars.Read (Char [], Int32, Int32)-Methode

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