---
title: 'Icordebugvariablehome:: getregiester-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790987"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="b684c-102">Icordebugvariablehome:: getregiester-Methode</span><span class="sxs-lookup"><span data-stu-id="b684c-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="b684c-103">Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER`enthält, und das Basisregister für eine Variable mit dem Speicherorttyp `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="b684c-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b684c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b684c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b684c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b684c-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="b684c-106">vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER`angibt, und das Basisregister für eine Variable mit dem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="b684c-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b684c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b684c-107">Return Value</span></span>  
 <span data-ttu-id="b684c-108">Die-Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="b684c-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="b684c-109">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="b684c-109">Value</span></span>|<span data-ttu-id="b684c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b684c-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="b684c-111">Die Variable befindet sich in dem durch das `pRegister`-Argument aufgeführten Register.</span><span class="sxs-lookup"><span data-stu-id="b684c-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="b684c-112">Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b684c-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b684c-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b684c-113">Requirements</span></span>  
 <span data-ttu-id="b684c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b684c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b684c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b684c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b684c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b684c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b684c-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b684c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b684c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b684c-118">See also</span></span>

- [<span data-ttu-id="b684c-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b684c-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="b684c-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b684c-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
