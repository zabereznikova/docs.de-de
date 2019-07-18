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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301391"
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable-Feld

`ServicePointManager.s_ServicePointTable` ist eine <xref:System.Collections.Hashtable> , enthält die Liste der aktiven HTTP-Verbindungen (<xref:System.Net.ServicePoint>s) in der <xref:System.AppDomain>.

## <a name="syntax"></a>Syntax
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Die `ServicePointManager.s_ServicePointTable` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.
> 
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
