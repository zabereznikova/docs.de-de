---
title: Feld "HttpWebRequest. _CoreResponse"
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
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740449"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest.\_Feld "coreresponse"

`HttpWebRequest._CoreResponse` ist ein Objekt (entweder [coreresponsedata](coreresponsedata.md) oder ein <xref:System.Exception>), das das Ergebnis der HTTP-Antwort Analyse enthält.

## <a name="syntax"></a>Syntax
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Diese API ist nicht für die direkte Verwendung im Code vorgesehen. Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden. Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>-Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
