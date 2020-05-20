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
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609442"
---
# <a name="user_thread-structure"></a><span data-ttu-id="af223-102">USER_THREAD-Struktur</span><span class="sxs-lookup"><span data-stu-id="af223-102">USER_THREAD Structure</span></span>
<span data-ttu-id="af223-103">Stellt einem Debugger Informationen zu einem Thread bereit.</span><span class="sxs-lookup"><span data-stu-id="af223-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="af223-104">Weitere Informationen finden Sie unter der [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="af223-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af223-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af223-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="af223-106">Member</span><span class="sxs-lookup"><span data-stu-id="af223-106">Members</span></span>  
  
|<span data-ttu-id="af223-107">Member</span><span class="sxs-lookup"><span data-stu-id="af223-107">Member</span></span>|<span data-ttu-id="af223-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af223-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="af223-109">Adresse des Thread Puffers.</span><span class="sxs-lookup"><span data-stu-id="af223-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="af223-110">Länge des Thread Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="af223-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="af223-111">Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="af223-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af223-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af223-112">Requirements</span></span>  
 <span data-ttu-id="af223-113">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="af223-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af223-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af223-114">See also</span></span>

- [<span data-ttu-id="af223-115">SetNotifyFilter-Methode</span><span class="sxs-lookup"><span data-stu-id="af223-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="af223-116">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="af223-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
