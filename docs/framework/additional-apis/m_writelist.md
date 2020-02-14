---
title: "\"Connection. m_WriteList\"-Feld"
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
ms.openlocfilehash: 22f939d13cceac4d1c0b39e9e8fe20cdc0ab9387
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214900"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="2c1e2-102">Connection. m\_beschreitelist-Feld</span><span class="sxs-lookup"><span data-stu-id="2c1e2-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="2c1e2-103">`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekten, die in die Warteschlange eingereiht werden, um über HTTP gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="2c1e2-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c1e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c1e2-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="2c1e2-105">Das `Connection.m_WriteList` Feld ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c1e2-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="2c1e2-106">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="2c1e2-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c1e2-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c1e2-107">Requirements</span></span>

<span data-ttu-id="2c1e2-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2c1e2-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2c1e2-109">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="2c1e2-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2c1e2-110">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="2c1e2-110">**.NET Framework versions:** Available since 2.0.</span></span>
