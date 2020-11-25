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
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711753"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="3762d-102">Icordebugvariablehome:: getregiester-Methode</span><span class="sxs-lookup"><span data-stu-id="3762d-102">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="3762d-103">Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER` und dem Basisregister für eine Variable mit dem Speicherorttyp enthält `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="3762d-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3762d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3762d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3762d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3762d-105">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="3762d-106">vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER` und das Basisregister für eine Variable mit dem Speicherorttyp angibt `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="3762d-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3762d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3762d-107">Return Value</span></span>  

 <span data-ttu-id="3762d-108">Die-Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="3762d-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="3762d-109">Wert</span><span class="sxs-lookup"><span data-stu-id="3762d-109">Value</span></span>|<span data-ttu-id="3762d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3762d-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="3762d-111">Die-Variable befindet sich in dem durch das-Argument aufgeführten Register `pRegister` .</span><span class="sxs-lookup"><span data-stu-id="3762d-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="3762d-112">Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="3762d-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3762d-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3762d-113">Requirements</span></span>  

 <span data-ttu-id="3762d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3762d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3762d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3762d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3762d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3762d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3762d-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3762d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3762d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3762d-118">See also</span></span>

- [<span data-ttu-id="3762d-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3762d-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="3762d-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3762d-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
