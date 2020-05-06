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
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860930"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="7fba3-102">CoreClrDebugRuntimeInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="7fba3-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="7fba3-103">Stellt eine CLR-Instanz (Common Language Runtime) dar, die in einem Prozess auf einem Remotecomputer geladen wird.</span><span class="sxs-lookup"><span data-stu-id="7fba3-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fba3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fba3-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="7fba3-105">Members</span><span class="sxs-lookup"><span data-stu-id="7fba3-105">Members</span></span>  
  
|<span data-ttu-id="7fba3-106">Member</span><span class="sxs-lookup"><span data-stu-id="7fba3-106">Member</span></span>|<span data-ttu-id="7fba3-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7fba3-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="7fba3-108">Der Prozessbezeichner, der durch den auf dem Zielcomputer ausgeführten Remotedebugproxy zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7fba3-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7fba3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fba3-109">Requirements</span></span>  
 <span data-ttu-id="7fba3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fba3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fba3-111">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="7fba3-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="7fba3-112">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="7fba3-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="7fba3-113">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="7fba3-113">**.NET Framework Versions:** 3.5 SP1</span></span>
