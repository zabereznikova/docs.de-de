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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214924"
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

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
