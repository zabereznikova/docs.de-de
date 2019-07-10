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
ms.openlocfilehash: 4e2e6a4624403dcab30bdb7b6d3af0226204cac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744646"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="1462e-102">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1462e-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="1462e-103">Stellt Methoden bereit, die es Entwicklern ermöglichen, Silverlight-basierte Anwendungen in der Umgebung der Common Language Runtime (CLR) zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="1462e-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1462e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1462e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="1462e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1462e-105">Methods</span></span>  
  
|<span data-ttu-id="1462e-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1462e-106">Method</span></span>|<span data-ttu-id="1462e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1462e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1462e-108">ICorDebugRemoteTarget::GetHostName-Methode</span><span class="sxs-lookup"><span data-stu-id="1462e-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="1462e-109">Gibt den Hostnamen oder die IP-Adresse eines Remotecomputers zurück.</span><span class="sxs-lookup"><span data-stu-id="1462e-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1462e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1462e-110">Remarks</span></span>  
 <span data-ttu-id="1462e-111">Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 und Windows Me sowie auf Nicht-x86-Plattformen (z. B. IA-64 und AMD64) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1462e-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1462e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1462e-112">Requirements</span></span>  
 <span data-ttu-id="1462e-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1462e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1462e-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="1462e-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1462e-115">**Bibliothek:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1462e-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="1462e-116">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1462e-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1462e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1462e-117">See also</span></span>

- [<span data-ttu-id="1462e-118">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1462e-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="1462e-119">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1462e-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="1462e-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1462e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
