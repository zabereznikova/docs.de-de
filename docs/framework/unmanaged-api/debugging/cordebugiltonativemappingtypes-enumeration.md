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
ms.openlocfilehash: ddb5af486ab6fb1c8c4fabf3ccf7b43d037e1eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789322"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="3d8bf-102">CorDebugIlToNativeMappingTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3d8bf-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="3d8bf-103">Gibt an, ob ein bestimmter Bereich von systemeigenen Anweisungen, der durch eine Instanz der COR_DEBUG_IL_TO_NATIVE_MAP-Struktur dargestellt wird, einem speziellen Code Bereich entspricht.</span><span class="sxs-lookup"><span data-stu-id="3d8bf-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d8bf-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="3d8bf-105">Member</span><span class="sxs-lookup"><span data-stu-id="3d8bf-105">Members</span></span>  
  
|<span data-ttu-id="3d8bf-106">Member</span><span class="sxs-lookup"><span data-stu-id="3d8bf-106">Member</span></span>|<span data-ttu-id="3d8bf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d8bf-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="3d8bf-108">Der Bereich der systemeigenen Anweisungen entspricht keinem speziellen Code Bereich.</span><span class="sxs-lookup"><span data-stu-id="3d8bf-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="3d8bf-109">Der Bereich der nativen Anweisungen entspricht dem Prolog.</span><span class="sxs-lookup"><span data-stu-id="3d8bf-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="3d8bf-110">Der Bereich der nativen Anweisungen entspricht dem Epilog.</span><span class="sxs-lookup"><span data-stu-id="3d8bf-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d8bf-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d8bf-111">Requirements</span></span>  
 <span data-ttu-id="3d8bf-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d8bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d8bf-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d8bf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d8bf-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d8bf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d8bf-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d8bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8bf-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d8bf-116">See also</span></span>

- [<span data-ttu-id="3d8bf-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="3d8bf-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="3d8bf-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3d8bf-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
