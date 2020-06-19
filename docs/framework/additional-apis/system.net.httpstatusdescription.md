---
title: HttpStatus Description-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990476"
---
# <a name="httpstatusdescription-class"></a>HttpStatus Description-Klasse

Stellt standardmäßige HTTP-Status Beschreibungen bereit. Diese Klasse kann nicht vererbt werden.

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="get-method"></a>Get-Methode

Gibt die Beschreibung zurück, die dem angegebenen HTTP-Statuscode zugeordnet ist.

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a>Parameter

`code` <xref:System.Int32>

Der HTTP-Statuscode, z `404` . b..

### <a name="return-value"></a>Rückgabewert

<xref:System.String?displayProperty=nameWithType>

Die http-Statusbeschreibung.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
