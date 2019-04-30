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
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986517"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="453f1-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="453f1-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="453f1-103">Gibt den nativen Speicherort-Typ einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="453f1-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="453f1-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="453f1-105">Member</span><span class="sxs-lookup"><span data-stu-id="453f1-105">Members</span></span>  
  
|<span data-ttu-id="453f1-106">Member</span><span class="sxs-lookup"><span data-stu-id="453f1-106">Member</span></span>|<span data-ttu-id="453f1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="453f1-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="453f1-108">Die Variable ist in einem Register.</span><span class="sxs-lookup"><span data-stu-id="453f1-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="453f1-109">Die Variable ist in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="453f1-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="453f1-110">Die Variable wird nicht in ein Register oder einen Register bezogene-Speicherbereich gespeichert.</span><span class="sxs-lookup"><span data-stu-id="453f1-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="453f1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="453f1-111">Remarks</span></span>  
 <span data-ttu-id="453f1-112">Ein Mitglied der `VariableLocationType` Enumeration wird zurückgegeben, durch die [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="453f1-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453f1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="453f1-113">Requirements</span></span>  
 <span data-ttu-id="453f1-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453f1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453f1-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="453f1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="453f1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="453f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="453f1-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453f1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453f1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="453f1-118">See also</span></span>

- [<span data-ttu-id="453f1-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="453f1-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
