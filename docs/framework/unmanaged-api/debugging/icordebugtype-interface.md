---
title: ICorDebugType-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964763"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="62b45-102">ICorDebugType-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62b45-102">ICorDebugType Interface</span></span>
<span data-ttu-id="62b45-103">Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert).</span><span class="sxs-lookup"><span data-stu-id="62b45-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="62b45-104">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="62b45-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62b45-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="62b45-105">Methods</span></span>  
  
|<span data-ttu-id="62b45-106">Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-106">Method</span></span>|<span data-ttu-id="62b45-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62b45-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62b45-108">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="62b45-109">Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf <xref:System.Type> die generischen Parameter der Klasse verweist `ICorDebugType`, auf die von verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="62b45-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62b45-110">GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="62b45-111">Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` -Wert ab, der auf die Basisklasse der Klasse `ICorDebugType`verweist, auf die diese verweist, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62b45-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="62b45-112">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="62b45-113">Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor von `ICorDebugType`verweist.</span><span class="sxs-lookup"><span data-stu-id="62b45-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62b45-114">GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="62b45-115">Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf den <xref:System.Type> ersten generischen Parameter für den Konstruktor der Klasse verweist `ICorDebugType`, auf die von verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="62b45-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62b45-116">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="62b45-117">Ruft die Anzahl der Dimensionen in einem Arraytyp ab.</span><span class="sxs-lookup"><span data-stu-id="62b45-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="62b45-118">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="62b45-119">Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="62b45-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="62b45-120">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="62b45-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="62b45-121">Ruft einen korelementtype-Wert ab, der den systemeigenen Typ <xref:System.Type> des Common Language Runtime beschreibt `ICorDebugType`, auf den von diesem verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="62b45-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62b45-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62b45-122">Remarks</span></span>  
 <span data-ttu-id="62b45-123">Wenn der Typ generisch ist `ICorDebugClass` , stellt den nicht instanziierten Typ dar.</span><span class="sxs-lookup"><span data-stu-id="62b45-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="62b45-124">Die `ICorDebugType` -Schnittstelle stellt einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="62b45-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="62b45-125">Beispielsweise würde Hashtable\<K, V > durch `ICorDebugClass`dargestellt, wohingegen Hash Table\<Int32, Zeichen folgen > durch `ICorDebugType`dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="62b45-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="62b45-126">Nicht generische Typen werden sowohl `ICorDebugClass` von als auch `ICorDebugType`von dargestellt.</span><span class="sxs-lookup"><span data-stu-id="62b45-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="62b45-127">Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="62b45-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62b45-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62b45-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62b45-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62b45-129">Requirements</span></span>  
 <span data-ttu-id="62b45-130">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62b45-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62b45-131">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="62b45-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62b45-132">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62b45-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62b45-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62b45-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b45-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62b45-134">See also</span></span>

- [<span data-ttu-id="62b45-135">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62b45-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
