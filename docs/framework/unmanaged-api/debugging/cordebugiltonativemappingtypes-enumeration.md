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
ms.openlocfilehash: ecb88195e3ecc7c540679a683005798247afe57f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712403"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="35bf5-102">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="35bf5-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>

<span data-ttu-id="35bf5-103">Gibt an, ob ein bestimmter Bereich von systemeigenen Anweisungen, der durch eine Instanz der COR_DEBUG_IL_TO_NATIVE_MAP-Struktur dargestellt wird, einem speziellen Code Bereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="35bf5-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35bf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35bf5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="35bf5-105">Member</span><span class="sxs-lookup"><span data-stu-id="35bf5-105">Members</span></span>  
  
|<span data-ttu-id="35bf5-106">Member</span><span class="sxs-lookup"><span data-stu-id="35bf5-106">Member</span></span>|<span data-ttu-id="35bf5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="35bf5-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="35bf5-108">Der Bereich der systemeigenen Anweisungen entspricht keinem speziellen Code Bereich.</span><span class="sxs-lookup"><span data-stu-id="35bf5-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="35bf5-109">Der Bereich der nativen Anweisungen entspricht dem Prolog.</span><span class="sxs-lookup"><span data-stu-id="35bf5-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="35bf5-110">Der Bereich der nativen Anweisungen entspricht dem Epilog.</span><span class="sxs-lookup"><span data-stu-id="35bf5-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35bf5-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35bf5-111">Requirements</span></span>  

 <span data-ttu-id="35bf5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35bf5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35bf5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35bf5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35bf5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35bf5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35bf5-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35bf5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35bf5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35bf5-116">See also</span></span>

- [<span data-ttu-id="35bf5-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="35bf5-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="35bf5-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="35bf5-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
