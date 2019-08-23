---
title: ICorDebugType2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2f2c1e4c95c61eab4c9da6103d4ac479b4bbdb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936052"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="491aa-102">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="491aa-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="491aa-103">Erweitert die ICorDebugType-Schnittstelle zum Abrufen des Typbezeichners eines Basistyps oder eines komplexen (benutzerdefinierten) Typs.</span><span class="sxs-lookup"><span data-stu-id="491aa-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="491aa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="491aa-104">Methods</span></span>  
  
|<span data-ttu-id="491aa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="491aa-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="491aa-106">GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="491aa-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="491aa-107">Ruft eine [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für diesen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="491aa-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="491aa-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="491aa-108">Remarks</span></span>  
 <span data-ttu-id="491aa-109">Diese Schnittstelle ist eine logische Erweiterung der ICorDebugType-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="491aa-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="491aa-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="491aa-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="491aa-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="491aa-111">Example</span></span>  
 <span data-ttu-id="491aa-112">Das folgende Code Fragment veranschaulicht die Verwendung der [ICorDebugType2:: GetTypeId](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="491aa-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="491aa-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="491aa-113">Requirements</span></span>  
 <span data-ttu-id="491aa-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="491aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="491aa-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="491aa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="491aa-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="491aa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="491aa-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="491aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491aa-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="491aa-118">See also</span></span>

- [<span data-ttu-id="491aa-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="491aa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
