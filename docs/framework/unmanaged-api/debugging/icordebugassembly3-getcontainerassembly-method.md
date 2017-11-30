---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9a32520c2a67c0bc51a3f88e9822db49e4a3974
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="696b4-102">ICorDebugAssembly3::GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="696b4-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="696b4-103">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="696b4-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="696b4-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="696b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="696b4-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="696b4-106">Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Container-Assembly darstellt oder **null** , wenn der Methodenaufruf fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="696b4-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="696b4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="696b4-107">Return Value</span></span>  
 <span data-ttu-id="696b4-108">`S_OK`Wenn der Methodenaufruf erfolgreich ist. andernfalls `S_FALSE`, und `ppAssembly` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="696b4-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="696b4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="696b4-109">Remarks</span></span>  
 <span data-ttu-id="696b4-110">Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="696b4-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="696b4-111">Weitere Informationen und Terminologie finden Sie in der [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="696b4-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="696b4-112">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="696b4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696b4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="696b4-113">Requirements</span></span>  
 <span data-ttu-id="696b4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696b4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696b4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="696b4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="696b4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="696b4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="696b4-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696b4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696b4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="696b4-118">See Also</span></span>  
 [<span data-ttu-id="696b4-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="696b4-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="696b4-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="696b4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
