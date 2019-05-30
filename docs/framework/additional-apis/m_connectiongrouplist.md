---
title: ServicePoint.m_ConnectionGroupList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 85359492fbf06942a57c51142620cab015999b31
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300864"
---
# <a name="servicepointmconnectiongrouplist-field"></a><span data-ttu-id="cf4de-102">ServicePoint.m\_ConnectionGroupList-Feld</span><span class="sxs-lookup"><span data-stu-id="cf4de-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="cf4de-103">`ServicePoint.m_ConnectionGroupList` ist eine <xref:System.Collections.Hashtable> von Verbindungsgruppen, enthalten jeweils eine Verbindung für die <xref:System.Net.ServicePoint>des URI.</span><span class="sxs-lookup"><span data-stu-id="cf4de-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf4de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf4de-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="cf4de-105">Die `ServicePoint.m_ConnectionGroupList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf4de-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="cf4de-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="cf4de-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf4de-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf4de-107">Requirements</span></span>

<span data-ttu-id="cf4de-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="cf4de-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="cf4de-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="cf4de-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="cf4de-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="cf4de-110">**.NET Framework versions:** Available since 2.0.</span></span>
