---
title: CoreClrDebugProcInfo-Struktur
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 5996393fd1a0504f9c3d3f9f07aa0e3d886a0787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719696"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="d212f-102">CoreClrDebugProcInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="d212f-102">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="d212f-103">Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d212f-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d212f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d212f-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d212f-105">Member</span><span class="sxs-lookup"><span data-stu-id="d212f-105">Members</span></span>  
  
|<span data-ttu-id="d212f-106">Member</span><span class="sxs-lookup"><span data-stu-id="d212f-106">Member</span></span>|<span data-ttu-id="d212f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d212f-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="d212f-108">Vom Betriebssystem zugewiesene Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="d212f-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="d212f-109">Die Prozess-ID, der durch den auf dem Zielcomputer ausgeführten Remotedebuggingproxy zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d212f-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="d212f-110">Diese ID wird seltener wiederverwendet als die Betriebssystem-ID.</span><span class="sxs-lookup"><span data-stu-id="d212f-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="d212f-111">Die Befehlszeile des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d212f-111">Command-line of the process.</span></span> <span data-ttu-id="d212f-112">Dieser Member wird möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="d212f-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d212f-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d212f-113">Requirements</span></span>  

 <span data-ttu-id="d212f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d212f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d212f-115">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="d212f-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d212f-116">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d212f-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d212f-117">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="d212f-117">**.NET Framework Versions:** 3.5 SP1</span></span>
