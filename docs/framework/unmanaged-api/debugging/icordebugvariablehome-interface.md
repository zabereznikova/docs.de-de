---
title: ICorDebugVariableHome-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a561360e7ea43945a3e12a73daba5063b3ad02f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="ed347-102">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed347-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="ed347-103">Stellt eine lokale Variable oder ein Argument einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="ed347-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed347-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed347-104">Methods</span></span>  
  
|<span data-ttu-id="ed347-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-105">Method</span></span>|<span data-ttu-id="ed347-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed347-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed347-107">GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="ed347-108">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="ed347-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="ed347-109">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="ed347-110">Ruft die "ICorDebugCode"-Instanz, die dieses enthält `ICorDebugVariableHome` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ed347-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="ed347-111">GetLiveRange-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="ed347-112">Ruft den systemeigenen Bereich über den diese Variable aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="ed347-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="ed347-113">GetLocationType-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="ed347-114">Ruft den Typ des systemeigenen Speicherort der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="ed347-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="ed347-115">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="ed347-116">Ruft den Offset von der Basisregister für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="ed347-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="ed347-117">GetRegister-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="ed347-118">Ruft die Registrierung, die eine Variable mit einem Speicherort enthält `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="ed347-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="ed347-119">GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="ed347-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="ed347-120">Ruft den verwalteten slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="ed347-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ed347-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed347-121">Example</span></span>  
 <span data-ttu-id="ed347-122">Das folgende Codefragment verwendet den [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) Objekt mit dem Namen `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="ed347-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="ed347-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed347-123">Requirements</span></span>  
 <span data-ttu-id="ed347-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed347-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed347-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed347-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed347-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed347-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed347-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed347-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed347-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed347-128">See Also</span></span>  
 [<span data-ttu-id="ed347-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ed347-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ed347-130">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed347-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
