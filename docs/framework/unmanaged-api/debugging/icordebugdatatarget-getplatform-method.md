---
title: ICorDebugDataTarget::GetPlatform-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 309c31dacd801f1c46a2d37932124638bc157cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214026"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="41218-102">ICorDebugDataTarget::GetPlatform-Methode</span><span class="sxs-lookup"><span data-stu-id="41218-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="41218-103">Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf dem der Zielprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="41218-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41218-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41218-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41218-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41218-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="41218-106">[out] Ein Zeiger auf eine [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration, die die Zielplattform beschreibt.</span><span class="sxs-lookup"><span data-stu-id="41218-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41218-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41218-107">Remarks</span></span>  
 <span data-ttu-id="41218-108">Die `CorDebugPlatformEnum` Rückgabewert der Enumeration wird verwendet, durch die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle, um zu bestimmen, die Details des Zielprozesses z. B. die Größe des Zeigers, Adresse Speicherplatz Layout, Registersatz, Anweisungsformat, Layout mit Ausrichtung von Kontext und Aufrufkonventionen.</span><span class="sxs-lookup"><span data-stu-id="41218-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="41218-109">Die `pTargetPlatform` Wert bezieht sich möglicherweise auf eine Plattform, die für das Ziel anstelle der tatsächlichen Hardware verwendet emuliert wird.</span><span class="sxs-lookup"><span data-stu-id="41218-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="41218-110">Beispielsweise ein Prozess, der in der Windows für die Umgebung für Windows (WOW), auf einer 64-Bit-Edition des Betriebssystems Windows ausgeführt wird verwenden sollte die `CORDB_PLATFORM_WINDOWS_X86` Wert, der die [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="41218-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="41218-111">Diese Methode muss erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="41218-111">This method must succeed.</span></span> <span data-ttu-id="41218-112">Wenn ein Fehler auftritt, ist die Zielplattform unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="41218-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="41218-113">Die Methode kann den folgenden Gründen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="41218-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="41218-114">Die Plattform, die emuliert wird, für das Ziel kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41218-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="41218-115">Die tatsächliche Hardware auf der Zielplattform ist unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="41218-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41218-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41218-116">Requirements</span></span>  
 <span data-ttu-id="41218-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41218-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41218-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41218-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41218-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41218-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41218-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="41218-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41218-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41218-121">See also</span></span>

- [<span data-ttu-id="41218-122">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41218-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="41218-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41218-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="41218-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="41218-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
