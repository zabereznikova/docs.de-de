---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 51e68e73983425cdd7d648b6856809fcba590f70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688548"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="07239-102">ICorDebugAssembly3::GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="07239-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>

<span data-ttu-id="07239-103">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="07239-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07239-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07239-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07239-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07239-105">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="07239-106">Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die containerassembly darstellt, oder **null** , wenn der Methodenaufrufe fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="07239-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07239-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07239-107">Return Value</span></span>  

 <span data-ttu-id="07239-108">`S_OK` , wenn der Methoden Aufrufvorgang erfolgreich ist. andernfalls `S_FALSE` ist, und `ppAssembly` **null**.</span><span class="sxs-lookup"><span data-stu-id="07239-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07239-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07239-109">Remarks</span></span>  

 <span data-ttu-id="07239-110">Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="07239-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="07239-111">Weitere Informationen und die Terminologie finden Sie im Thema [ICorDebugProcess6:: enablevirtualmodulesplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="07239-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07239-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07239-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07239-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07239-113">Requirements</span></span>  

 <span data-ttu-id="07239-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07239-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07239-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07239-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07239-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07239-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07239-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07239-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07239-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07239-118">See also</span></span>

- [<span data-ttu-id="07239-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07239-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="07239-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="07239-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
