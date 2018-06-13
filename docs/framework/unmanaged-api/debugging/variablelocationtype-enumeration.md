---
title: VariableLocationType-Enumeration
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cc7a299e6be328095c0368acf0a4b767fb74d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423948"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="6c2d5-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6c2d5-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="6c2d5-103">Gibt den systemeigenen Typ einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="6c2d5-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c2d5-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="6c2d5-105">Member</span><span class="sxs-lookup"><span data-stu-id="6c2d5-105">Members</span></span>  
  
|<span data-ttu-id="6c2d5-106">Member</span><span class="sxs-lookup"><span data-stu-id="6c2d5-106">Member</span></span>|<span data-ttu-id="6c2d5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c2d5-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="6c2d5-108">Die Variable ist in einem Register.</span><span class="sxs-lookup"><span data-stu-id="6c2d5-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="6c2d5-109">Die Variable ist in eine Register-Relative Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="6c2d5-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="6c2d5-110">Die Variable wird nicht in ein Register oder Register relativen Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6c2d5-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c2d5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c2d5-111">Remarks</span></span>  
 <span data-ttu-id="6c2d5-112">Ein Mitglied der `VariableLocationType` Enumeration wird zurückgegeben, durch die [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6c2d5-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c2d5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c2d5-113">Requirements</span></span>  
 <span data-ttu-id="6c2d5-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c2d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c2d5-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c2d5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c2d5-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c2d5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c2d5-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c2d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2d5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c2d5-118">See Also</span></span>  
 [<span data-ttu-id="6c2d5-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6c2d5-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
