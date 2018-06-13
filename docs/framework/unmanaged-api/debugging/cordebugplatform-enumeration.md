---
title: CorDebugPlatform-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d3b8f1e869e90fd3388cc0844e608b7ff40fc89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407091"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="40387-102">CorDebugPlatform-Enumeration</span><span class="sxs-lookup"><span data-stu-id="40387-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="40387-103">Stellt Zielplattformwerte, mit denen, die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="40387-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40387-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40387-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="40387-105">Member</span><span class="sxs-lookup"><span data-stu-id="40387-105">Members</span></span>  
  
|<span data-ttu-id="40387-106">Member</span><span class="sxs-lookup"><span data-stu-id="40387-106">Member</span></span>|<span data-ttu-id="40387-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40387-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="40387-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="40387-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="40387-109">Die Zielplattform ist Windows auf Intel-x86-Hardware.</span><span class="sxs-lookup"><span data-stu-id="40387-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="40387-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="40387-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="40387-111">Die Zielplattform ist 64-Bit-Windows auf AMD64-Hardware oder Intel EM64T-Hardware.</span><span class="sxs-lookup"><span data-stu-id="40387-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="40387-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="40387-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="40387-113">Die Zielplattform ist 32-Bit-Windows auf Intel IA-64-Hardware.</span><span class="sxs-lookup"><span data-stu-id="40387-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="40387-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="40387-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="40387-115">Die Zielplattform ist Macintosh-Betriebssystem auf PowerPC-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40387-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="40387-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="40387-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="40387-117">Die Zielplattform ist Macintosh-Betriebssystem auf Intel X86 Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40387-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="40387-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="40387-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="40387-119">Die Zielplattform ist Macintosh-Betriebssystem auf Windows-ARM-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40387-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="40387-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="40387-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="40387-121">Die Zielplattform ist Macintosh-Betriebssystem auf AMD64-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40387-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40387-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40387-122">Requirements</span></span>  
 <span data-ttu-id="40387-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40387-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40387-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40387-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40387-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40387-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40387-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40387-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="40387-127">Die `CORDB_PLATFORM_WINDOWS_ARM`- und `CORDB_PLATFORM_MAC_AMD64`-Member sind in .NET Framework 4.5.2 und höheren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40387-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40387-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40387-128">See Also</span></span>  
 [<span data-ttu-id="40387-129">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="40387-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
