---
title: CorDebugIlToNativeMappingTypes-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fec0f4f31f45847dc092808b2d47c662213e9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402519"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="5783f-102">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5783f-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="5783f-103">Gibt an, ob es sich bei einem besonderen Codebereich entspricht ein bestimmter Bereich systemeigener Anweisungen, die von einer Instanz von COR_DEBUG_IL_TO_NATIVE_MAP-Struktur dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5783f-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5783f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5783f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="5783f-105">Member</span><span class="sxs-lookup"><span data-stu-id="5783f-105">Members</span></span>  
  
|<span data-ttu-id="5783f-106">Member</span><span class="sxs-lookup"><span data-stu-id="5783f-106">Member</span></span>|<span data-ttu-id="5783f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5783f-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="5783f-108">Besonderen Codebereich entspricht nicht der Bereich systemeigener Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5783f-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="5783f-109">Der Bereich systemeigener Anweisungen entspricht der Prolog.</span><span class="sxs-lookup"><span data-stu-id="5783f-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="5783f-110">Der Bereich systemeigener Anweisungen entspricht der Epilog.</span><span class="sxs-lookup"><span data-stu-id="5783f-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5783f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5783f-111">Requirements</span></span>  
 <span data-ttu-id="5783f-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5783f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5783f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5783f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5783f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5783f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5783f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5783f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5783f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5783f-116">See Also</span></span>  
 [<span data-ttu-id="5783f-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="5783f-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="5783f-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5783f-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
