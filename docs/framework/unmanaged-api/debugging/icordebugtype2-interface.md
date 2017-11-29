---
title: ICorDebugType2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugType2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType2
helpviewer_keywords: ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 658dd1541a1de852c3c001cc7fbb7954f6c7590f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="cdbba-102">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdbba-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="cdbba-103">ICorDebugType-Schnittstelle, die Typ-ID von einem Basistyp oder komplexen (Benutzerdefiniert) Typ abgerufen wird erweitert.</span><span class="sxs-lookup"><span data-stu-id="cdbba-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdbba-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cdbba-104">Methods</span></span>  
  
|<span data-ttu-id="cdbba-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cdbba-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="cdbba-106">GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="cdbba-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="cdbba-107">Ruft eine [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="cdbba-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdbba-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdbba-108">Remarks</span></span>  
 <span data-ttu-id="cdbba-109">Diese Schnittstelle ist eine logische Erweiterung von ICorDebugType-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cdbba-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdbba-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cdbba-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdbba-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdbba-111">Example</span></span>  
 <span data-ttu-id="cdbba-112">Das folgende Codefragment veranschaulicht die Verwendung von der [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="cdbba-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="cdbba-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdbba-113">Requirements</span></span>  
 <span data-ttu-id="cdbba-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdbba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdbba-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdbba-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdbba-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdbba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdbba-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdbba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbba-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdbba-118">See Also</span></span>  
 [<span data-ttu-id="cdbba-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cdbba-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
