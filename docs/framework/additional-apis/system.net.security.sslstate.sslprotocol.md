---
title: Sslstate. SslProtocol-Eigenschaft (System .net. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847247"
---
# <a name="sslstatesslprotocol-property"></a>Sslstate. SslProtocol (Eigenschaft)

Ruft die SSL-Protokoll Versionen ab.

## <a name="syntax"></a>Syntax

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>Eigenschafts Wert

<xref:System.Security.Authentication.SslProtocols>  
Eine bitweise Kombination der Enumerationswerte, die die SSL-Protokoll Versionen angeben.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `SslState.SslProtocol`-Eigenschaft ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net.Security>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
