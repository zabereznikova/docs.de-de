---
title: ServicePointManager. s_ServicePointTable-Feld
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120000"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager. s\_servicepointtables-Feld

`ServicePointManager.s_ServicePointTable` ist eine <xref:System.Collections.Hashtable>, die die Liste der aktiven http-Verbindungen (<xref:System.Net.ServicePoint>s) in der <xref:System.AppDomain>enthält.

## <a name="syntax"></a>Syntax
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Das `ServicePointManager.s_ServicePointTable` Feld ist privat und sollte nicht direkt im Code verwendet werden.
> 
> Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
