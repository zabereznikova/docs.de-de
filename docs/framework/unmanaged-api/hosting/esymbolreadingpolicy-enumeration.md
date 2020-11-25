---
title: ESymbolReadingPolicy-Enumeration
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 42ce1f02294db98c5c593a5f16de5226703d5f9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733710"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="72505-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="72505-102">ESymbolReadingPolicy Enumeration</span></span>

<span data-ttu-id="72505-103">Enthält Werte, mit denen die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="72505-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72505-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72505-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="72505-105">Member</span><span class="sxs-lookup"><span data-stu-id="72505-105">Members</span></span>  
  
|<span data-ttu-id="72505-106">Member</span><span class="sxs-lookup"><span data-stu-id="72505-106">Member</span></span>|<span data-ttu-id="72505-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="72505-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="72505-108">Gibt an, dass der Debugger immer PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="72505-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="72505-109">Gibt an, dass der Debugger nur PDB-Dateien lesen soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="72505-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="72505-110">Gibt an, dass der Debugger niemals PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="72505-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72505-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72505-111">Remarks</span></span>  

 <span data-ttu-id="72505-112">Die- `ESymbolReadingPolicy` Enumeration wird mit der [ICLRDebugManager:: setsymbolleserpolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="72505-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72505-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="72505-113">Requirements</span></span>  

 <span data-ttu-id="72505-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72505-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72505-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="72505-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72505-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72505-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72505-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72505-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72505-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72505-118">See also</span></span>

- [<span data-ttu-id="72505-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="72505-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
