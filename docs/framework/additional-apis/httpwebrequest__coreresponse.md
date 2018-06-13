---
title: HttpWebRequest._CoreResponse-Feld
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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356198"
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest-Anforderung. \_CoreResponse-Feld

`HttpWebRequest._CoreResponse` ein Objekt ist (entweder eine [CoreResponseData](coreresponsedata.md) oder ein <xref:System.Exception>), enthält das Ergebnis der Analyse von HTTP-Antwort.

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
