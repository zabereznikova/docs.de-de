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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9d4b27ca0bf454b42f15b849008e5a3019bb09a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402190"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="a5cd6-102">CoreClrDebugProcInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="a5cd6-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="a5cd6-103">Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5cd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5cd6-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="a5cd6-105">Member</span><span class="sxs-lookup"><span data-stu-id="a5cd6-105">Members</span></span>  
  
|<span data-ttu-id="a5cd6-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5cd6-106">Member</span></span>|<span data-ttu-id="a5cd6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5cd6-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="a5cd6-108">Vom Betriebssystem zugewiesene Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="a5cd6-109">Die Prozess-ID, der durch den auf dem Zielcomputer ausgeführten Remotedebuggingproxy zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="a5cd6-110">Diese ID wird seltener wiederverwendet als die Betriebssystem-ID.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="a5cd6-111">Die Befehlszeile des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-111">Command-line of the process.</span></span> <span data-ttu-id="a5cd6-112">Dieser Member wird möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="a5cd6-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5cd6-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5cd6-113">Requirements</span></span>  
 <span data-ttu-id="a5cd6-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5cd6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5cd6-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="a5cd6-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a5cd6-116">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="a5cd6-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a5cd6-117">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a5cd6-117">**.NET Framework Versions:** 3.5 SP1</span></span>
