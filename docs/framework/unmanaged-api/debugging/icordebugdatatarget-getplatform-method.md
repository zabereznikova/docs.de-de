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
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679792"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="e41bd-102">ICorDebugDataTarget::GetPlatform-Methode</span><span class="sxs-lookup"><span data-stu-id="e41bd-102">ICorDebugDataTarget::GetPlatform Method</span></span>

<span data-ttu-id="e41bd-103">Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e41bd-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e41bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e41bd-105">Parameters</span></span>  

 `pTargetPlatform`  
 <span data-ttu-id="e41bd-106">vorgenommen Ein Zeiger auf eine [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration, die die Zielplattform beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e41bd-106">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e41bd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e41bd-107">Remarks</span></span>  

 <span data-ttu-id="e41bd-108">Der `CorDebugPlatformEnum` Rückgabewert der-Enumeration wird von der [ICorDebug](icordebug-interface.md) -Schnittstelle verwendet, um Details des Ziel Prozesses zu bestimmen, z. b. die Zeiger Größe, das Adressraum Layout, den Register Satz, das Anweisungs Format, das Kontext Layout und die Aufruf Konventionen.</span><span class="sxs-lookup"><span data-stu-id="e41bd-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="e41bd-109">Der `pTargetPlatform` Wert verweist möglicherweise auf eine Plattform, die für das Ziel emuliert wird, anstatt die tatsächlich verwendete Hardware anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e41bd-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="e41bd-110">Beispielsweise sollte ein Prozess, der in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Edition des Windows-Betriebssystems ausgeführt wird, den `CORDB_PLATFORM_WINDOWS_X86` Wert der [cordebugplatformenum](cordebugplatform-enumeration.md) -Enumeration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e41bd-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="e41bd-111">Diese Methode muss erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="e41bd-111">This method must succeed.</span></span> <span data-ttu-id="e41bd-112">Wenn dies nicht möglich ist, ist die Zielplattform unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="e41bd-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="e41bd-113">Die-Methode kann aus den folgenden Gründen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="e41bd-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="e41bd-114">Die Plattform, die für das Ziel emuliert wird, ist unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="e41bd-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="e41bd-115">Die tatsächliche Hardware auf der Zielplattform ist unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="e41bd-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41bd-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e41bd-116">Requirements</span></span>  

 <span data-ttu-id="e41bd-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e41bd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e41bd-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e41bd-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e41bd-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e41bd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e41bd-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e41bd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41bd-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e41bd-121">See also</span></span>

- [<span data-ttu-id="e41bd-122">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e41bd-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="e41bd-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e41bd-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e41bd-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e41bd-124">Debugging</span></span>](index.md)
