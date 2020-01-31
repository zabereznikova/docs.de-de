---
title: ICorDebugClass-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784168"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="20bf6-102">ICorDebugClass-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20bf6-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="20bf6-103">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="20bf6-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="20bf6-104">Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="20bf6-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20bf6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="20bf6-105">Methods</span></span>  
  
|<span data-ttu-id="20bf6-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="20bf6-106">Method</span></span>|<span data-ttu-id="20bf6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20bf6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20bf6-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="20bf6-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="20bf6-109">Ruft das Modul ab, das diese Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="20bf6-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="20bf6-110">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="20bf6-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="20bf6-111">Ruft den Wert des angegebenen statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="20bf6-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="20bf6-112">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="20bf6-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="20bf6-113">Ruft das `TypeDef` Metadatentoken für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="20bf6-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20bf6-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20bf6-114">Remarks</span></span>  
 <span data-ttu-id="20bf6-115">Die `ICorDebugClass`-Schnittstelle stellt einen nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="20bf6-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="20bf6-116">Die ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="20bf6-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="20bf6-117">Beispielsweise wird `Hashtable<K, V>` durch `ICorDebugClass`dargestellt, wohingegen `Hashtable<Int32, String>` durch `ICorDebugType`dargestellt würde.</span><span class="sxs-lookup"><span data-stu-id="20bf6-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="20bf6-118">Nicht generische Typen werden durch `ICorDebugClass` und `ICorDebugType`dargestellt.</span><span class="sxs-lookup"><span data-stu-id="20bf6-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="20bf6-119">Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="20bf6-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20bf6-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="20bf6-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20bf6-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20bf6-121">Requirements</span></span>  
 <span data-ttu-id="20bf6-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20bf6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20bf6-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20bf6-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20bf6-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20bf6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20bf6-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20bf6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20bf6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20bf6-126">See also</span></span>

- [<span data-ttu-id="20bf6-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="20bf6-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
