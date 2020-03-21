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
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178363"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="bf6bb-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bf6bb-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="bf6bb-103">Gibt den systemeigenen Positionstyp einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="bf6bb-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf6bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf6bb-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="bf6bb-105">Members</span><span class="sxs-lookup"><span data-stu-id="bf6bb-105">Members</span></span>  
  
|<span data-ttu-id="bf6bb-106">Member</span><span class="sxs-lookup"><span data-stu-id="bf6bb-106">Member</span></span>|<span data-ttu-id="bf6bb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf6bb-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="bf6bb-108">Die Variable befindet sich in einem Register.</span><span class="sxs-lookup"><span data-stu-id="bf6bb-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="bf6bb-109">Die Variable befindet sich an einem registerrelativen Speicherspeicherort.</span><span class="sxs-lookup"><span data-stu-id="bf6bb-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="bf6bb-110">Die Variable wird nicht in einem Register oder einem registerrelativen Speicherspeicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bf6bb-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf6bb-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bf6bb-111">Remarks</span></span>  
 <span data-ttu-id="bf6bb-112">Ein Member `VariableLocationType` der Enumeration wird von der [ICorDebugVariableHome::GetLocationType-Methode](icordebugvariablehome-getlocationtype-method.md) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bf6bb-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf6bb-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bf6bb-113">Requirements</span></span>  
 <span data-ttu-id="bf6bb-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf6bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf6bb-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf6bb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf6bb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf6bb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf6bb-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf6bb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6bb-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf6bb-118">See also</span></span>

- [<span data-ttu-id="bf6bb-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="bf6bb-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
