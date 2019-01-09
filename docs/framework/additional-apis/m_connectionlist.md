---
title: ConnectionGroup.m_ConnectionList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
author: guardrex
ms.author: mairaw
ms.openlocfilehash: c9162e123c1167e3aa1be26ddd37279c088acc89
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149162"
---
# <a name="connectiongroupmconnectionlist-field"></a><span data-ttu-id="d0661-102">ConnectionGroup.m\_ConnectionList-Feld</span><span class="sxs-lookup"><span data-stu-id="d0661-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="d0661-103">`ConnectionGroup.m_ConnectionList` ist ein <xref:System.Collections.ArrayList> von Verbindungsobjekten, die den gleichen URI und die Freigabe dient, die gleichen Werte für einige andere Eigenschaften wie Ablauf und Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d0661-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0661-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0661-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="d0661-105">Die `ConnectionGroup.m_ConnectionList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0661-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="d0661-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d0661-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0661-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0661-107">Requirements</span></span>

<span data-ttu-id="d0661-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d0661-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d0661-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="d0661-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d0661-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="d0661-110">**.NET Framework versions:** Available since 2.0.</span></span>
