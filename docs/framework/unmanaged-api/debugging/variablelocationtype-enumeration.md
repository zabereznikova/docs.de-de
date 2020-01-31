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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790314"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="d08cb-102">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d08cb-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="d08cb-103">Gibt den Typ des systemeigenen Standorts einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="d08cb-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d08cb-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="d08cb-105">Member</span><span class="sxs-lookup"><span data-stu-id="d08cb-105">Members</span></span>  
  
|<span data-ttu-id="d08cb-106">Member</span><span class="sxs-lookup"><span data-stu-id="d08cb-106">Member</span></span>|<span data-ttu-id="d08cb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d08cb-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="d08cb-108">Die Variable befindet sich in einem Register.</span><span class="sxs-lookup"><span data-stu-id="d08cb-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="d08cb-109">Die Variable befindet sich in einer Register-relativen Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="d08cb-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="d08cb-110">Die Variable wird nicht in einer Register-oder Register-relativen Speicheradresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d08cb-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d08cb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d08cb-111">Remarks</span></span>  
 <span data-ttu-id="d08cb-112">Ein Member der `VariableLocationType` Enumeration wird von der [icordebugvariablehome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d08cb-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d08cb-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d08cb-113">Requirements</span></span>  
 <span data-ttu-id="d08cb-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d08cb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d08cb-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d08cb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d08cb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d08cb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d08cb-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d08cb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d08cb-118">See also</span></span>

- [<span data-ttu-id="d08cb-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d08cb-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
