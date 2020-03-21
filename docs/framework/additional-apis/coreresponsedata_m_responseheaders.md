---
title: CoreResponseData.m_ResponseHeaders-Feld
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156102"
---
# <a name="coreresponsedatam_responseheaders-field"></a>CoreResponseData.m\_ResponseHeaders-Feld

`CoreResponseData.m_ResponseHeaders`ist <xref:System.Net.WebHeaderCollection> ein Header, der der Serverantwort zugeordnet ist.

## <a name="syntax"></a>Syntax
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Diese API ist nicht dazu gedacht, direkt in Ihrem Code verwendet zu werden. Stattdessen sollten Sie <xref:System.Diagnostics.DiagnosticSource> einen zum Hook-Netzwerkcode verwenden. Siehe [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:**<xref:System.Net>

**Montage:** System (in System.dll)

**.NET Framework-Versionen:** Verfügbar seit 2.0.
