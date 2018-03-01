---
title: USER_THREAD-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 50533ce25812ad49d538c5a6a6c814d7a9704053
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="b99b8-102">USER_THREAD-Struktur</span><span class="sxs-lookup"><span data-stu-id="b99b8-102">USER_THREAD Structure</span></span>
<span data-ttu-id="b99b8-103">Enthält Informationen für einen Debugger über einen Thread.</span><span class="sxs-lookup"><span data-stu-id="b99b8-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="b99b8-104">Weitere Informationen finden Sie unter der [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b99b8-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b99b8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b99b8-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="b99b8-106">Member</span><span class="sxs-lookup"><span data-stu-id="b99b8-106">Members</span></span>  
  
|<span data-ttu-id="b99b8-107">Member</span><span class="sxs-lookup"><span data-stu-id="b99b8-107">Member</span></span>|<span data-ttu-id="b99b8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b99b8-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="b99b8-109">Die Adresse des Threadpuffers.</span><span class="sxs-lookup"><span data-stu-id="b99b8-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="b99b8-110">Die Länge des Threadpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b99b8-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="b99b8-111">Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="b99b8-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b99b8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b99b8-112">Requirements</span></span>  
 <span data-ttu-id="b99b8-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="b99b8-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99b8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b99b8-114">See Also</span></span>  
 [<span data-ttu-id="b99b8-115">SetNotifyFilter-Methode</span><span class="sxs-lookup"><span data-stu-id="b99b8-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="b99b8-116">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="b99b8-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
