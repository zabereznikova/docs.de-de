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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099949"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="f8477-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f8477-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="f8477-103">Gibt den nativen Speicherort-Typ einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="f8477-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8477-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8477-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="f8477-105">Member</span><span class="sxs-lookup"><span data-stu-id="f8477-105">Members</span></span>  
  
|<span data-ttu-id="f8477-106">Member</span><span class="sxs-lookup"><span data-stu-id="f8477-106">Member</span></span>|<span data-ttu-id="f8477-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8477-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="f8477-108">Die Variable ist in einem Register.</span><span class="sxs-lookup"><span data-stu-id="f8477-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="f8477-109">Die Variable ist in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="f8477-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="f8477-110">Die Variable wird nicht in ein Register oder einen Register bezogene-Speicherbereich gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f8477-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8477-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8477-111">Remarks</span></span>  
 <span data-ttu-id="f8477-112">Ein Mitglied der `VariableLocationType` Enumeration wird zurückgegeben, durch die [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f8477-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8477-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8477-113">Requirements</span></span>  
 <span data-ttu-id="f8477-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8477-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8477-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8477-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8477-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8477-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f8477-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f8477-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8477-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8477-118">See also</span></span>

- [<span data-ttu-id="f8477-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="f8477-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
