---
title: ICorDebugType Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType
helpviewer_keywords: ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a25e72766e6647f820c9871e989d4b24db0bf26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="3ccc5-102">ICorDebugType Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="3ccc5-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="3ccc5-103">Stellt einen Typ dar, entweder grundlegend oder komplex (das heißt Benutzerdefiniert ist,).</span><span class="sxs-lookup"><span data-stu-id="3ccc5-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="3ccc5-104">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ccc5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ccc5-105">Methods</span></span>  
  
|<span data-ttu-id="3ccc5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-106">Method</span></span>|<span data-ttu-id="3ccc5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ccc5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ccc5-108">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="3ccc5-109">Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die die generische verweist <xref:System.Type> Parameter, der auf die verwiesen wird von dieser Klasse `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3ccc5-110">GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="3ccc5-111">Ruft einen Schnittstellenzeiger auf eine `ICorDebugType` , die auf die Basisklasse der verwiesen, die von dieser Klasse verweist `ICorDebugType`, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="3ccc5-112">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="3ccc5-113">Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die auf den typisierten Konstruktor dieses verweist `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3ccc5-114">GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="3ccc5-115">Ruft einen Schnittstellenzeiger auf eine `ICorDebugType` , verweist die erste generische <xref:System.Type> -Parameter für den Konstruktor der Klasse verweist, die von diesem auf `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3ccc5-116">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="3ccc5-117">Ruft die Anzahl der Dimensionen in einen Arraytyp an.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="3ccc5-118">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="3ccc5-119">Ruft einen Schnittstellenzeiger einen ICorDebugValue mit dem Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld token in den angegebenen Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="3ccc5-120">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="3ccc5-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="3ccc5-121">Ruft einen CorElementType-Wert, den systemeigenen Typ der common Language Runtime beschreibt <xref:System.Type> verwiesen, die von diesem `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ccc5-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ccc5-122">Remarks</span></span>  
 <span data-ttu-id="3ccc5-123">Wenn der Typ generisch ist, ist `ICorDebugClass` den nicht instanziierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="3ccc5-124">Die `ICorDebugType` Schnittstelle einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="3ccc5-125">Z. B. Hashtabellen\<K, V > dargestellt werden würde `ICorDebugClass`, wohingegen Hashtable\<Int32 "," String "> dargestellt werden würde `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="3ccc5-126">Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="3ccc5-127">Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ccc5-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3ccc5-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ccc5-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ccc5-129">Requirements</span></span>  
 <span data-ttu-id="3ccc5-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ccc5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ccc5-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ccc5-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ccc5-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ccc5-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ccc5-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ccc5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccc5-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ccc5-134">See Also</span></span>  
 [<span data-ttu-id="3ccc5-135">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ccc5-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
