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
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="d6ac9-104">ServicePointManager. s \_ servicepointtables-Feld</span><span class="sxs-lookup"><span data-stu-id="d6ac9-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="d6ac9-105">`ServicePointManager.s_ServicePointTable`ist eine <xref:System.Collections.Hashtable> , die die Liste der aktiven http-Verbindungen <xref:System.Net.ServicePoint> in der enthält <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d6ac9-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6ac9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6ac9-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="d6ac9-107">Das `ServicePointManager.s_ServicePointTable` Feld ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6ac9-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d6ac9-108">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d6ac9-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6ac9-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d6ac9-109">Requirements</span></span>

<span data-ttu-id="d6ac9-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d6ac9-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d6ac9-111">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="d6ac9-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d6ac9-112">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="d6ac9-112">**.NET Framework versions:** Available since 2.0.</span></span>
