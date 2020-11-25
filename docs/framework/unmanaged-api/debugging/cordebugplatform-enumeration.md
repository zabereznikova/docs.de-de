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
ms.openlocfilehash: 5435f78b28975a5426fcb2fce94904efc1051c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696400"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="562ee-102">CorDebugPlatform-Enumeration</span><span class="sxs-lookup"><span data-stu-id="562ee-102">CorDebugPlatform Enumeration</span></span>

<span data-ttu-id="562ee-103">Stellt Ziel Platt Form Werte bereit, die von der [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="562ee-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="562ee-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="562ee-105">Member</span><span class="sxs-lookup"><span data-stu-id="562ee-105">Members</span></span>  
  
|<span data-ttu-id="562ee-106">Member</span><span class="sxs-lookup"><span data-stu-id="562ee-106">Member</span></span>|<span data-ttu-id="562ee-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="562ee-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="562ee-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="562ee-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="562ee-109">Die Zielplattform ist Windows auf Intel-x86-Hardware.</span><span class="sxs-lookup"><span data-stu-id="562ee-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="562ee-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="562ee-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="562ee-111">Die Zielplattform ist 64-Bit-Windows auf AMD64-Hardware oder Intel EM64T-Hardware.</span><span class="sxs-lookup"><span data-stu-id="562ee-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="562ee-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="562ee-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="562ee-113">Die Zielplattform ist 32-Bit-Windows auf Intel IA-64-Hardware.</span><span class="sxs-lookup"><span data-stu-id="562ee-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="562ee-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="562ee-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="562ee-115">Die Zielplattform ist das Macintosh-Betriebssystem, das auf PowerPC-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="562ee-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="562ee-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="562ee-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="562ee-117">Die Zielplattform ist das Macintosh-Betriebssystem, das auf Intel x86-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="562ee-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="562ee-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="562ee-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="562ee-119">Die Zielplattform ist das Macintosh-Betriebssystem, das auf Windows-Arm-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="562ee-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="562ee-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="562ee-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="562ee-121">Die Zielplattform ist das Macintosh-Betriebssystem, das auf AMD64-Hardware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="562ee-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="562ee-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="562ee-122">Requirements</span></span>  

 <span data-ttu-id="562ee-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="562ee-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="562ee-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="562ee-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="562ee-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="562ee-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="562ee-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="562ee-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="562ee-127">Die `CORDB_PLATFORM_WINDOWS_ARM`- und `CORDB_PLATFORM_MAC_AMD64`-Member sind in .NET Framework 4.5.2 und höheren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="562ee-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562ee-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="562ee-128">See also</span></span>

- [<span data-ttu-id="562ee-129">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="562ee-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
