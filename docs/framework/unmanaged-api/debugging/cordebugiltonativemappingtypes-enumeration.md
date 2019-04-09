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
ms.openlocfilehash: 2f62707fb1e52a96cf3f131e9c11fee82ab03f4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097186"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="454be-102">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="454be-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="454be-103">Gibt an, ob es sich bei ein bestimmter Bereich systemeigener Anweisungen, dargestellt durch eine Instanz der COR_DEBUG_IL_TO_NATIVE_MAP-Struktur, die einem besonderen Codebereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="454be-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="454be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="454be-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="454be-105">Member</span><span class="sxs-lookup"><span data-stu-id="454be-105">Members</span></span>  
  
|<span data-ttu-id="454be-106">Member</span><span class="sxs-lookup"><span data-stu-id="454be-106">Member</span></span>|<span data-ttu-id="454be-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="454be-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="454be-108">Besonderen Codebereich entspricht nicht der Bereich systemeigener Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="454be-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="454be-109">Der Bereich systemeigener Anweisungen entspricht der Prolog.</span><span class="sxs-lookup"><span data-stu-id="454be-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="454be-110">Der Bereich systemeigener Anweisungen entspricht der Epilog.</span><span class="sxs-lookup"><span data-stu-id="454be-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="454be-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="454be-111">Requirements</span></span>  
 <span data-ttu-id="454be-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="454be-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="454be-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="454be-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="454be-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="454be-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="454be-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="454be-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="454be-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="454be-116">See also</span></span>

- [<span data-ttu-id="454be-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="454be-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="454be-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="454be-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
