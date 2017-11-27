---
title: ICorDebugDataTarget::GetPlatform-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetPlatform Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf2f852d0da36211e379a4068cccff9dfc656100
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="6c869-102">ICorDebugDataTarget::GetPlatform-Methode</span><span class="sxs-lookup"><span data-stu-id="6c869-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="6c869-103">Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf denen der Zielprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6c869-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c869-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c869-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c869-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c869-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="6c869-106">[out] Ein Zeiger auf eine [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration, die die Zielplattform beschreibt.</span><span class="sxs-lookup"><span data-stu-id="6c869-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c869-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c869-107">Remarks</span></span>  
 <span data-ttu-id="6c869-108">Die `CorDebugPlatformEnum` return Enumerationswert wird verwendet, durch die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle, um die Details des Zielprozesses, z. B. die Zeigergröße, Adresse Speicherplatz Layout, Registersatz, Anweisungsformat, Kontextlayout zu bestimmen und Aufrufkonventionen.</span><span class="sxs-lookup"><span data-stu-id="6c869-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="6c869-109">Die `pTargetPlatform` Wert bezieht sich möglicherweise auf eine Plattform, die für das Ziel die tatsächliche Hardware verwendet angeben, statt emuliert wird.</span><span class="sxs-lookup"><span data-stu-id="6c869-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="6c869-110">Beispielsweise ein Prozess, der in dem Windows on Windows (WOW)-Umgebung auf eine 64-Bit-Edition von Windows-Betriebssystem ausgeführt wird die zu verwendende der `CORDB_PLATFORM_WINDOWS_X86` Wert, der die [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6c869-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="6c869-111">Diese Methode muss erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="6c869-111">This method must succeed.</span></span> <span data-ttu-id="6c869-112">Falls dies fehlschlägt, ist die Zielplattform unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="6c869-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="6c869-113">Die Methode kann den folgenden Gründen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="6c869-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="6c869-114">Die Plattform, die für das Ziel emulierte ist unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="6c869-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="6c869-115">Die tatsächliche Hardware für die Zielplattform ist unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="6c869-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c869-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c869-116">Requirements</span></span>  
 <span data-ttu-id="6c869-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c869-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c869-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c869-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c869-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c869-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c869-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c869-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c869-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c869-121">See Also</span></span>  
 [<span data-ttu-id="6c869-122">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c869-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="6c869-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6c869-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6c869-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6c869-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
