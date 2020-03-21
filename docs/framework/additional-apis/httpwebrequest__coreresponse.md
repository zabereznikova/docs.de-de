---
title: HttpWebRequest._CoreResponse Feld
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155920"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_CoreResponse-Feld

`HttpWebRequest._CoreResponse`ist ein Objekt (entweder eine <xref:System.Exception> [CoreResponseData](coreresponsedata.md) oder ein ), die das Ergebnis der HTTP-Antwortanalyse enthält.

## <a name="syntax"></a>Syntax
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Diese API ist nicht dazu gedacht, direkt in Ihrem Code verwendet zu werden. Stattdessen sollten Sie <xref:System.Diagnostics.DiagnosticSource> einen zum Hook-Netzwerkcode verwenden. Siehe [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:**<xref:System.Net>

**Montage:** System (in System.dll)

**.NET Framework-Versionen:** Verfügbar seit 2.0.
