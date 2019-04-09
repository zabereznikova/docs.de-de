---
title: ICorDebugRemoteTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae31506d4ba34bf262f49bc2321c6cfcd30f1b60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197320"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="647d1-102">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="647d1-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="647d1-103">Stellt Methoden bereit, die es Entwicklern ermöglichen, Silverlight-basierte Anwendungen in der Umgebung der Common Language Runtime (CLR) zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="647d1-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="647d1-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="647d1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="647d1-105">Methods</span></span>  
  
|<span data-ttu-id="647d1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="647d1-106">Method</span></span>|<span data-ttu-id="647d1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="647d1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="647d1-108">ICorDebugRemoteTarget::GetHostName-Methode</span><span class="sxs-lookup"><span data-stu-id="647d1-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="647d1-109">Gibt den Hostnamen oder die IP-Adresse eines Remotecomputers zurück.</span><span class="sxs-lookup"><span data-stu-id="647d1-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="647d1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="647d1-110">Remarks</span></span>  
 <span data-ttu-id="647d1-111">Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 und Windows Me sowie auf Nicht-x86-Plattformen (z. B. IA-64 und AMD64) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="647d1-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="647d1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="647d1-112">Requirements</span></span>  
 <span data-ttu-id="647d1-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="647d1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="647d1-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="647d1-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="647d1-115">**Bibliothek:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="647d1-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="647d1-116">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="647d1-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647d1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="647d1-117">See also</span></span>

- [<span data-ttu-id="647d1-118">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="647d1-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="647d1-119">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="647d1-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="647d1-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="647d1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
