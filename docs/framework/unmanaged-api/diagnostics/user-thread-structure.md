---
title: USER_THREAD-Struktur
ms.date: 03/30/2017
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
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722894"
---
# <a name="user_thread-structure"></a><span data-ttu-id="52540-102">USER_THREAD-Struktur</span><span class="sxs-lookup"><span data-stu-id="52540-102">USER_THREAD Structure</span></span>

<span data-ttu-id="52540-103">Stellt einem Debugger Informationen zu einem Thread bereit.</span><span class="sxs-lookup"><span data-stu-id="52540-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="52540-104">Weitere Informationen finden Sie unter der [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="52540-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52540-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="52540-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="52540-106">Member</span><span class="sxs-lookup"><span data-stu-id="52540-106">Members</span></span>  
  
|<span data-ttu-id="52540-107">Member</span><span class="sxs-lookup"><span data-stu-id="52540-107">Member</span></span>|<span data-ttu-id="52540-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="52540-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="52540-109">Adresse des Thread Puffers.</span><span class="sxs-lookup"><span data-stu-id="52540-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="52540-110">Länge des Thread Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="52540-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="52540-111">Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="52540-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52540-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="52540-112">Requirements</span></span>  

 <span data-ttu-id="52540-113">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="52540-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52540-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52540-114">See also</span></span>

- [<span data-ttu-id="52540-115">SetNotifyFilter-Methode</span><span class="sxs-lookup"><span data-stu-id="52540-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="52540-116">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="52540-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
