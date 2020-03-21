---
title: ServicePointManager.s_ServicePointTable-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155812"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager.s\_ServicePointTable-Feld

`ServicePointManager.s_ServicePointTable`ist <xref:System.Collections.Hashtable> eine, die die Liste<xref:System.Net.ServicePoint>der aktiven <xref:System.AppDomain>HTTP-Verbindungen (s) im enthält.

## <a name="syntax"></a>Syntax
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Das `ServicePointManager.s_ServicePointTable` Feld ist privat und soll nicht direkt in Ihrem Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:**<xref:System.Net>

**Montage:** System (in System.dll)

**.NET Framework-Versionen:** Verfügbar seit 2.0.
