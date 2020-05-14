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
ms.openlocfilehash: 6cf66774209bd07426872c29c15b2225421c2b4d
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396834"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="0a5e4-102">Icordebugvariablehome:: getregiester-Methode</span><span class="sxs-lookup"><span data-stu-id="0a5e4-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="0a5e4-103">Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER` und dem Basisregister für eine Variable mit dem Speicherorttyp enthält `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="0a5e4-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a5e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a5e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a5e4-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="0a5e4-106">vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER` und das Basisregister für eine Variable mit dem Speicherorttyp angibt `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="0a5e4-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a5e4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0a5e4-107">Return Value</span></span>  
 <span data-ttu-id="0a5e4-108">Die-Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="0a5e4-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="0a5e4-109">Wert</span><span class="sxs-lookup"><span data-stu-id="0a5e4-109">Value</span></span>|<span data-ttu-id="0a5e4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a5e4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="0a5e4-111">Die-Variable befindet sich in dem durch das-Argument aufgeführten Register `pRegister` .</span><span class="sxs-lookup"><span data-stu-id="0a5e4-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="0a5e4-112">Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="0a5e4-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a5e4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a5e4-113">Requirements</span></span>  
 <span data-ttu-id="0a5e4-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a5e4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a5e4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a5e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a5e4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a5e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a5e4-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a5e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5e4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a5e4-118">See also</span></span>

- [<span data-ttu-id="0a5e4-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0a5e4-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="0a5e4-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a5e4-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
