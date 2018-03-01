---
title: CoreClrDebugProcInfo-Struktur
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d341b875f9f64b9aa1fcdcf21668dafea0beac12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="18adb-102">CoreClrDebugProcInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="18adb-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="18adb-103">Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18adb-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18adb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18adb-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="18adb-105">Member</span><span class="sxs-lookup"><span data-stu-id="18adb-105">Members</span></span>  
  
|<span data-ttu-id="18adb-106">Member</span><span class="sxs-lookup"><span data-stu-id="18adb-106">Member</span></span>|<span data-ttu-id="18adb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18adb-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="18adb-108">Vom Betriebssystem zugewiesene Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="18adb-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="18adb-109">Die Prozess-ID, der durch den auf dem Zielcomputer ausgeführten Remotedebuggingproxy zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="18adb-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="18adb-110">Diese ID wird seltener wiederverwendet als die Betriebssystem-ID.</span><span class="sxs-lookup"><span data-stu-id="18adb-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="18adb-111">Die Befehlszeile des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="18adb-111">Command-line of the process.</span></span> <span data-ttu-id="18adb-112">Dieser Member wird möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="18adb-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18adb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18adb-113">Requirements</span></span>  
 <span data-ttu-id="18adb-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18adb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18adb-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="18adb-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="18adb-116">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="18adb-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="18adb-117">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="18adb-117">**.NET Framework Versions:** 3.5 SP1</span></span>
