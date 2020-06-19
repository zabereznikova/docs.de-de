---
title: ServicePointManager. s_ServicePointTable-Feld
description: Informieren Sie sich über das Feld ServicePointManager. s_ServicePointTable in .net. Dieses Hash Tabellenfeld enthält aktive http-Verbindungen (Service Points) in der AppDomain.
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
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989538"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager. s \_ servicepointtables-Feld

`ServicePointManager.s_ServicePointTable`ist eine <xref:System.Collections.Hashtable> , die die Liste der aktiven http-Verbindungen <xref:System.Net.ServicePoint> in der enthält <xref:System.AppDomain> .

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

**Assembly:** System (in System.dll)

**.NET Framework Versionen:** Verfügbar seit 2,0.
