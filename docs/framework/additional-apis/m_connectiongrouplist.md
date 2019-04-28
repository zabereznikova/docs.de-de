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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: a764c74dc0927094675b0f5e0916a4ad29f04250
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705947"
---
# <a name="servicepointmconnectiongrouplist-field"></a><span data-ttu-id="72d72-102">ServicePoint.m\_ConnectionGroupList-Feld</span><span class="sxs-lookup"><span data-stu-id="72d72-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="72d72-103">`ServicePoint.m_ConnectionGroupList` ist eine <xref:System.Collections.Hashtable> von Verbindungsgruppen, enthalten jeweils eine Verbindung für die <xref:System.Net.ServicePoint>des URI.</span><span class="sxs-lookup"><span data-stu-id="72d72-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="72d72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72d72-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="72d72-105">Die `ServicePoint.m_ConnectionGroupList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72d72-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="72d72-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="72d72-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="72d72-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72d72-107">Requirements</span></span>

<span data-ttu-id="72d72-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="72d72-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="72d72-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="72d72-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="72d72-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="72d72-110">**.NET Framework versions:** Available since 2.0.</span></span>
