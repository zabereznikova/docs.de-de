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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d138e0490e849ff26f540077ec7d23ae42737606
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300907"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="4b064-102">Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="4b064-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="4b064-103">`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekte, die in der Warteschlange befinden, die über HTTP gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b064-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b064-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b064-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="4b064-105">Die `Connection.m_WriteList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b064-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="4b064-106">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="4b064-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b064-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b064-107">Requirements</span></span>

<span data-ttu-id="4b064-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4b064-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4b064-109">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="4b064-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4b064-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="4b064-110">**.NET Framework versions:** Available since 2.0.</span></span>
