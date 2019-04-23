---
title: ICorDebugVariableHome::GetRegister-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 290647f0e0dcaeae53362762ed7f8e0c2f05a82c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189949"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="11bf0-102">ICorDebugVariableHome::GetRegister-Methode</span><span class="sxs-lookup"><span data-stu-id="11bf0-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="11bf0-103">Ruft ab, das Register, die eine Variable mit einem Standort enthält `VLT_REGISTER`, und registrieren Sie die Basis für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="11bf0-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bf0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11bf0-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11bf0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11bf0-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="11bf0-106">[out] Ein CorDebugRegister-Enumeration-Wert, der das Register für eine Variable mit einem Standort gibt `VLT_REGISTER`, und registrieren Sie die Basis für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="11bf0-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11bf0-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11bf0-107">Return Value</span></span>  
 <span data-ttu-id="11bf0-108">Die Methode gibt die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="11bf0-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="11bf0-109">Wert</span><span class="sxs-lookup"><span data-stu-id="11bf0-109">Value</span></span>|<span data-ttu-id="11bf0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11bf0-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="11bf0-111">Die Variable ist in der Registrierung, angegeben durch die `pRegister` Argument.</span><span class="sxs-lookup"><span data-stu-id="11bf0-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="11bf0-112">Die Variable ist nicht in ein Register oder ein Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="11bf0-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11bf0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11bf0-113">Requirements</span></span>  
 <span data-ttu-id="11bf0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11bf0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11bf0-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11bf0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11bf0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11bf0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11bf0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bf0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bf0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11bf0-118">See also</span></span>

- [<span data-ttu-id="11bf0-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="11bf0-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="11bf0-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11bf0-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
