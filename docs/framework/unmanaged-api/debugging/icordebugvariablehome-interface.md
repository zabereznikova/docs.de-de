---
title: ICorDebugVariableHome-Schnittstelle
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339a0f502b7e47f7bee82a0da92185481d909e64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202910"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="fc3ee-102">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc3ee-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="fc3ee-103">Stellt eine lokale Variable oder ein Argument einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc3ee-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fc3ee-104">Methods</span></span>  
  
|<span data-ttu-id="fc3ee-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-105">Method</span></span>|<span data-ttu-id="fc3ee-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc3ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc3ee-107">GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="fc3ee-108">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="fc3ee-109">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="fc3ee-110">Ruft die Instanz von "ICorDebugCode", der diesen `ICorDebugVariableHome` Objekt.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="fc3ee-111">GetLiveRange-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="fc3ee-112">Ruft ab, der systemeigenen Bereich, in dem diese Variable ist.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="fc3ee-113">GetLocationType-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="fc3ee-114">Ruft den Typ des systemeigenen Speicherorts für den Wert der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="fc3ee-115">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="fc3ee-116">Ruft den Offset aus dem Basis-Register für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="fc3ee-117">GetRegister-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="fc3ee-118">Ruft ab, das Register, die eine Variable mit einem Standort enthält `VLT_REGISTER`, und registrieren Sie die Basis für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="fc3ee-119">GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="fc3ee-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="fc3ee-120">Ruft den verwalteten slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc3ee-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc3ee-121">Example</span></span>  
 <span data-ttu-id="fc3ee-122">Das folgende Codefragment verwendet den [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) Objekt mit dem Namen `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="fc3ee-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="fc3ee-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc3ee-123">Requirements</span></span>  
 <span data-ttu-id="fc3ee-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3ee-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3ee-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc3ee-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc3ee-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc3ee-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fc3ee-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fc3ee-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc3ee-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc3ee-128">See also</span></span>

- [<span data-ttu-id="fc3ee-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc3ee-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fc3ee-130">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc3ee-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
