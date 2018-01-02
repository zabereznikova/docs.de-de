---
title: ServicePointManager.s_ServicePointTable-Feld
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.ServicePointManager.s_ServicePointTable
api_location: System.dll
api_type: Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dfdbab78d8efab13487575218820f8b0455248d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="a4e37-102">ServicePointManager.s\_ServicePointTable-Feld</span><span class="sxs-lookup"><span data-stu-id="a4e37-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="a4e37-103">`ServicePointManager.s_ServicePointTable`ist eine <xref:System.Collections.Hashtable> , enthält die Liste der aktiven HTTP-Verbindungen (<xref:System.Net.ServicePoint>s) in der <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="a4e37-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4e37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4e37-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="a4e37-105">Die `ServicePointManager.s_ServicePointTable` Feld sind reserviert und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4e37-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a4e37-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="a4e37-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4e37-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4e37-107">Requirements</span></span>

<span data-ttu-id="a4e37-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a4e37-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a4e37-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="a4e37-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a4e37-110">**.NET Framework-Versionen:** verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="a4e37-110">**.NET Framework versions:** Available since 2.0.</span></span>
