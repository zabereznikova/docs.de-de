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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420655"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="46598-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="46598-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="46598-103">Gibt den Typ des systemeigenen Standorts einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="46598-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46598-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46598-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="46598-105">Member</span><span class="sxs-lookup"><span data-stu-id="46598-105">Members</span></span>  
  
|<span data-ttu-id="46598-106">Member</span><span class="sxs-lookup"><span data-stu-id="46598-106">Member</span></span>|<span data-ttu-id="46598-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46598-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="46598-108">Die Variable befindet sich in einem Register.</span><span class="sxs-lookup"><span data-stu-id="46598-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="46598-109">Die Variable befindet sich in einer Register-relativen Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="46598-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="46598-110">Die Variable wird nicht in einer Register-oder Register-relativen Speicheradresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46598-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46598-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46598-111">Remarks</span></span>  
 <span data-ttu-id="46598-112">Ein Member der- `VariableLocationType` Enumeration wird von der [icordebugvariablehome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="46598-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46598-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46598-113">Requirements</span></span>  
 <span data-ttu-id="46598-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46598-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46598-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46598-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46598-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46598-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46598-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46598-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46598-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46598-118">See also</span></span>

- [<span data-ttu-id="46598-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="46598-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
