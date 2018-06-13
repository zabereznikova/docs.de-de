---
title: CoreClrDebugRuntimeInfo-Struktur
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88fcc5959054f1cdf7c9543674584a4bde26d896
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402069"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="373a0-102">CoreClrDebugRuntimeInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="373a0-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="373a0-103">Stellt eine CLR-Instanz (Common Language Runtime) dar, die in einem Prozess auf einem Remotecomputer geladen wird.</span><span class="sxs-lookup"><span data-stu-id="373a0-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="373a0-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="373a0-105">Member</span><span class="sxs-lookup"><span data-stu-id="373a0-105">Members</span></span>  
  
|<span data-ttu-id="373a0-106">Member</span><span class="sxs-lookup"><span data-stu-id="373a0-106">Member</span></span>|<span data-ttu-id="373a0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="373a0-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="373a0-108">Der Prozessbezeichner, der durch den auf dem Zielcomputer ausgeführten Remotedebugproxy zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="373a0-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="373a0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="373a0-109">Requirements</span></span>  
 <span data-ttu-id="373a0-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="373a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373a0-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="373a0-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="373a0-112">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="373a0-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="373a0-113">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="373a0-113">**.NET Framework Versions:** 3.5 SP1</span></span>
