---
title: '[ICorDebugClass Schnittstelle1'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3998cf76430612759f69df07fb4f5afebd7a25ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="fe954-102">[ICorDebugClass Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="fe954-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="fe954-103">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="fe954-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="fe954-104">Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="fe954-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe954-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fe954-105">Methods</span></span>  
  
|<span data-ttu-id="fe954-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fe954-106">Method</span></span>|<span data-ttu-id="fe954-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe954-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe954-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="fe954-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="fe954-109">Ruft das Modul, das diese Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="fe954-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="fe954-110">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="fe954-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="fe954-111">Ruft den Wert des angegebenen statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="fe954-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="fe954-112">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fe954-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="fe954-113">Ruft die `TypeDef` Metadatentoken für diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="fe954-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe954-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe954-114">Remarks</span></span>  
 <span data-ttu-id="fe954-115">Die `ICorDebugClass` Schnittstelle stellt einen nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="fe954-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="fe954-116">[ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="fe954-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="fe954-117">Beispielsweise `Hashtable<K, V>` dargestellt werden würde `ICorDebugClass`, wohingegen `Hashtable<Int32, String>` dargestellt werden würde `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fe954-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="fe954-118">Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="fe954-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="fe954-119">Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe954-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe954-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fe954-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe954-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe954-121">Requirements</span></span>  
 <span data-ttu-id="fe954-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe954-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe954-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe954-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe954-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe954-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe954-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe954-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe954-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe954-126">See Also</span></span>  
 [<span data-ttu-id="fe954-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fe954-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
