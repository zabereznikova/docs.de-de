---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f61d23fc3ee3c6c8adb46c0deecdd72d155ae65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="30e89-102">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="30e89-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="30e89-103">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="30e89-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30e89-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="30e89-105">Member</span><span class="sxs-lookup"><span data-stu-id="30e89-105">Members</span></span>  
  
|<span data-ttu-id="30e89-106">Member</span><span class="sxs-lookup"><span data-stu-id="30e89-106">Members</span></span>|<span data-ttu-id="30e89-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e89-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="30e89-108">Die Startadresse des Blocks.</span><span class="sxs-lookup"><span data-stu-id="30e89-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="30e89-109">Die Länge der zusammenhängende Block.</span><span class="sxs-lookup"><span data-stu-id="30e89-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30e89-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30e89-110">Requirements</span></span>  
 <span data-ttu-id="30e89-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e89-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="30e89-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="30e89-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30e89-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e89-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30e89-115">See Also</span></span>  
 [<span data-ttu-id="30e89-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="30e89-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
