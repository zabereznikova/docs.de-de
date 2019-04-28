---
title: Connection.m_WriteList Field
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
ms.openlocfilehash: a7446b9cbbfd4d3a4d38368a8e24c99527cf9108
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705934"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="a4e2d-102">Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="a4e2d-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="a4e2d-103">`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekte, die in der Warteschlange befinden, die über HTTP gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4e2d-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4e2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4e2d-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="a4e2d-105">Die `Connection.m_WriteList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4e2d-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a4e2d-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="a4e2d-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4e2d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4e2d-107">Requirements</span></span>

<span data-ttu-id="a4e2d-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a4e2d-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a4e2d-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="a4e2d-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a4e2d-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="a4e2d-110">**.NET Framework versions:** Available since 2.0.</span></span>
