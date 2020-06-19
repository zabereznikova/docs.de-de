---
title: Coreresponabdata. m_ResponseHeaders-Feld
description: Verstehen Sie das coreresponabdata. m_ResponseHeaders-Feld in .net. Dieses Feld ist ein WebHeaderCollection-Typ, dem Header mit der Serverantwort zugeordnet sind.
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
ms.openlocfilehash: 7c7b896193cb81e9fc9e3ec28110359003a36728
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989795"
---
# <a name="coreresponsedatam_responseheaders-field"></a>Feld "coreresponabdata. m \_ Response Headers"

`CoreResponseData.m_ResponseHeaders`ist eine <xref:System.Net.WebHeaderCollection> von Headern, die der Serverantwort zugeordnet sind.

## <a name="syntax"></a>Syntax
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Diese API ist nicht für die direkte Verwendung im Code vorgesehen. Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden. Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)

**.NET Framework Versionen:** Verfügbar seit 2,0.
