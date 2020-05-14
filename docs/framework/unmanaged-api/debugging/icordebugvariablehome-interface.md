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
ms.openlocfilehash: caf6a24207be98be9afb10be2bd027b51405fa3b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396539"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="49e79-102">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49e79-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="49e79-103">Stellt eine lokale Variable oder ein Argument einer Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="49e79-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49e79-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="49e79-104">Methods</span></span>  
  
|<span data-ttu-id="49e79-105">Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-105">Method</span></span>|<span data-ttu-id="49e79-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49e79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49e79-107">GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="49e79-108">Ruft den Index eines Funktionsarguments ab.</span><span class="sxs-lookup"><span data-stu-id="49e79-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="49e79-109">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="49e79-110">Ruft die ICorDebugCode-Instanz ab, die dieses- `ICorDebugVariableHome` Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="49e79-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="49e79-111">GetLiveRange-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="49e79-112">Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.</span><span class="sxs-lookup"><span data-stu-id="49e79-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="49e79-113">GetLocationType-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="49e79-114">Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="49e79-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="49e79-115">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="49e79-116">Ruft den Offset aus dem Basisregister für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="49e79-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="49e79-117">GetRegister-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="49e79-118">Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER` und dem Basisregister für eine Variable mit dem Speicherorttyp enthält `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="49e79-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="49e79-119">GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="49e79-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="49e79-120">Ruft den verwalteten Slot-Index einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="49e79-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49e79-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49e79-121">Example</span></span>  
 <span data-ttu-id="49e79-122">Im folgenden Code Fragment wird das [ICorDebugCode4](icordebugcode4-interface.md) -Objekt mit dem Namen verwendet `pCode4` .</span><span class="sxs-lookup"><span data-stu-id="49e79-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="49e79-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49e79-123">Requirements</span></span>  
 <span data-ttu-id="49e79-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e79-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49e79-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49e79-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49e79-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49e79-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49e79-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49e79-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e79-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49e79-128">See also</span></span>

- [<span data-ttu-id="49e79-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="49e79-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="49e79-130">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49e79-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
