---
title: ICorDebugType-Schnittstelle1
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
ms.openlocfilehash: d29ab3c67e0788b15850b7dfb8b55914c1d1e369
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694528"
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="62ad0-102">ICorDebugType-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="62ad0-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="62ad0-103">Stellt einen Typ dar, entweder grundlegend oder komplex (das heißt Benutzerdefiniert,).</span><span class="sxs-lookup"><span data-stu-id="62ad0-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="62ad0-104">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="62ad0-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62ad0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="62ad0-105">Methods</span></span>  
  
|<span data-ttu-id="62ad0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-106">Method</span></span>|<span data-ttu-id="62ad0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62ad0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62ad0-108">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="62ad0-109">Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die die generische verweist <xref:System.Type> Parameter, der auf die verwiesen wird von dieser Klasse `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62ad0-110">GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="62ad0-111">Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` , die auf die Basisklasse der Klasse auf die dieses `ICorDebugType`, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62ad0-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="62ad0-112">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="62ad0-113">Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die den typisierten Konstruktor dieser verweist `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62ad0-114">GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="62ad0-115">Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` , die auf dem ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse auf die dieses `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="62ad0-116">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="62ad0-117">Ruft die Anzahl der Dimensionen im Array-Typ ab.</span><span class="sxs-lookup"><span data-stu-id="62ad0-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="62ad0-118">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="62ad0-119">Ruft einen Schnittstellenzeiger auf einen mit dem Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld ICorDebugValue-Tokens in den angegebenen Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="62ad0-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="62ad0-120">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad0-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="62ad0-121">Ruft einen CorElementType-Wert, der den systemeigenen Typ des von der common Language Runtime beschreibt <xref:System.Type> verwiesen, die von diesem `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62ad0-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62ad0-122">Remarks</span></span>  
 <span data-ttu-id="62ad0-123">Wenn der Typ generisch ist, ist `ICorDebugClass` den nicht instanziierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="62ad0-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="62ad0-124">Die `ICorDebugType` Schnittstelle stellt einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="62ad0-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="62ad0-125">Z. B. Hashtable\<K, V > durch dargestellt werden würde `ICorDebugClass`hingegen Hashtable\<Int32, Zeichenfolge > durch dargestellt werden würde `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="62ad0-126">Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="62ad0-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="62ad0-127">Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="62ad0-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62ad0-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62ad0-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ad0-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62ad0-129">Requirements</span></span>  
 <span data-ttu-id="62ad0-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ad0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ad0-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62ad0-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62ad0-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62ad0-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62ad0-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ad0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ad0-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62ad0-134">See also</span></span>
- [<span data-ttu-id="62ad0-135">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62ad0-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
