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
ms.openlocfilehash: 6c60831ddf23ce8ac9afcf244383d24732c3ef8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155836"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="e965c-102">Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="e965c-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="e965c-103">`Connection.m_WriteList`ist <xref:System.Collections.ArrayList> ein <xref:System.Net.HttpWebRequest> Objekt, das in die Warteschlange eingereiht wird, um über HTTP gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="e965c-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="e965c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e965c-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="e965c-105">Das `Connection.m_WriteList` Feld ist privat und soll nicht direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e965c-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e965c-106">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="e965c-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e965c-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e965c-107">Requirements</span></span>

<span data-ttu-id="e965c-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e965c-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e965c-109">**Montage:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="e965c-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e965c-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="e965c-110">**.NET Framework versions:** Available since 2.0.</span></span>
