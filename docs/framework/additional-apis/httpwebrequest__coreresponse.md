---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest-Anforderung. \_CoreResponse-Feld

`HttpWebRequest._CoreResponse`ein Objekt ist (entweder eine [CoreResponseData](coreresponsedata.md) oder ein <xref:System.Exception>), enthält das Ergebnis der Analyse von HTTP-Antwort.

## <a name="syntax"></a>Syntax
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Diese API ist nicht vorgesehen, direkt im Code verwendet werden. Stattdessen sollten Sie verwenden eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen. Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System.dll")

**.NET Framework-Versionen:** verfügbar seit 2.0.
