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
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616176"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="06614-102">ESymbolReadingPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="06614-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="06614-103">Enthält Werte, mit denen die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="06614-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06614-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06614-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="06614-105">Member</span><span class="sxs-lookup"><span data-stu-id="06614-105">Members</span></span>  
  
|<span data-ttu-id="06614-106">Member</span><span class="sxs-lookup"><span data-stu-id="06614-106">Member</span></span>|<span data-ttu-id="06614-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06614-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="06614-108">Gibt an, dass der Debugger immer PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="06614-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="06614-109">Gibt an, dass der Debugger nur PDB-Dateien lesen soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="06614-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="06614-110">Gibt an, dass der Debugger niemals PDB-Dateien lesen soll.</span><span class="sxs-lookup"><span data-stu-id="06614-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06614-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06614-111">Remarks</span></span>  
 <span data-ttu-id="06614-112">Die- `ESymbolReadingPolicy` Enumeration wird mit der [ICLRDebugManager:: setsymbolleserpolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="06614-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06614-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06614-113">Requirements</span></span>  
 <span data-ttu-id="06614-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06614-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06614-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="06614-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06614-116">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="06614-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06614-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06614-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06614-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06614-118">See also</span></span>

- [<span data-ttu-id="06614-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="06614-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
