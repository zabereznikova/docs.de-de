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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d06968c844dc9187b973af156a29ded9ba7cde66
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301395"
---
# <a name="connectiongroupmconnectionlist-field"></a><span data-ttu-id="1fceb-102">ConnectionGroup.m\_ConnectionList-Feld</span><span class="sxs-lookup"><span data-stu-id="1fceb-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="1fceb-103">`ConnectionGroup.m_ConnectionList` ist ein <xref:System.Collections.ArrayList> von Verbindungsobjekten, die den gleichen URI und die Freigabe dient, die gleichen Werte für einige andere Eigenschaften wie Ablauf und Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1fceb-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fceb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fceb-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="1fceb-105">Die `ConnectionGroup.m_ConnectionList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fceb-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="1fceb-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="1fceb-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fceb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fceb-107">Requirements</span></span>

<span data-ttu-id="1fceb-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1fceb-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1fceb-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="1fceb-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="1fceb-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="1fceb-110">**.NET Framework versions:** Available since 2.0.</span></span>
