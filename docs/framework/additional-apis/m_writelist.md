---
title: Connection.m_WriteList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743159"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="02025-102">Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="02025-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="02025-103">`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> der <xref:System.Net.HttpWebRequest> Objekte, die in der Warteschlange befinden, die über HTTP gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="02025-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="02025-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02025-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="02025-105">Die `Connection.m_WriteList` Feld sind reserviert und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02025-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="02025-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="02025-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="02025-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02025-107">Requirements</span></span>

<span data-ttu-id="02025-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="02025-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="02025-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="02025-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="02025-110">**.NET Framework-Versionen:** verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="02025-110">**.NET Framework versions:** Available since 2.0.</span></span>
