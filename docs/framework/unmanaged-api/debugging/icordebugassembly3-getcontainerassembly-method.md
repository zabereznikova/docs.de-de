---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c01898bcbd76f7e6de9445d5d1f511203c100ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585184"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="c3b18-102">ICorDebugAssembly3::GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c3b18-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="c3b18-103">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="c3b18-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3b18-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3b18-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3b18-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="c3b18-106">Ein Zeiger auf die Adresse des ein ICorDebugAssembly-Objekt, das die Container Assembly darstellt, oder **null** , wenn der Methodenaufruf fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c3b18-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b18-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c3b18-107">Return Value</span></span>  
 <span data-ttu-id="c3b18-108">`S_OK` Wenn der Methodenaufruf erfolgreich ist. andernfalls `S_FALSE`, und `ppAssembly` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="c3b18-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b18-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3b18-109">Remarks</span></span>  
 <span data-ttu-id="c3b18-110">Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="c3b18-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="c3b18-111">Weitere Informationen und Terminologie finden Sie unter den [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="c3b18-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3b18-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c3b18-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b18-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3b18-113">Requirements</span></span>  
 <span data-ttu-id="c3b18-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3b18-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b18-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3b18-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3b18-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3b18-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3b18-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b18-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b18-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3b18-118">See also</span></span>
- [<span data-ttu-id="c3b18-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3b18-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="c3b18-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c3b18-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
