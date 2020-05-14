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
ms.openlocfilehash: 5e88652ff75223e30e6abc454f1e1af91494c7b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396702"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="1c270-102">ICorDebugType-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c270-102">ICorDebugType Interface</span></span>
<span data-ttu-id="1c270-103">Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert).</span><span class="sxs-lookup"><span data-stu-id="1c270-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1c270-104">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1c270-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c270-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1c270-105">Methods</span></span>  
  
|<span data-ttu-id="1c270-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-106">Method</span></span>|<span data-ttu-id="1c270-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c270-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c270-108">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="1c270-109">Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf die generischen <xref:System.Type> Parameter der Klasse verweist, auf die von verwiesen wird `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="1c270-110">GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="1c270-111">Ruft einen Schnittstellen Zeiger auf einen-Wert ab, der auf `ICorDebugType` die Basisklasse der Klasse verweist, auf die diese verweist `ICorDebugType` , sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1c270-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="1c270-112">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="1c270-113">Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor von verweist `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="1c270-114">GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="1c270-115">Ruft einen Schnittstellen Zeiger auf einen ab, der auf `ICorDebugType` den ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse verweist, auf die von verwiesen wird `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="1c270-116">GetRank-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="1c270-117">Ruft die Anzahl der Dimensionen in einem Arraytyp ab.</span><span class="sxs-lookup"><span data-stu-id="1c270-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="1c270-118">GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="1c270-119">Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1c270-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="1c270-120">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="1c270-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="1c270-121">Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des Common Language Runtime beschreibt, <xref:System.Type> auf den von diesem verwiesen wird `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c270-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1c270-122">Remarks</span></span>  
 <span data-ttu-id="1c270-123">Wenn der Typ generisch ist, `ICorDebugClass` stellt den nicht instanziierten Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1c270-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="1c270-124">Die- `ICorDebugType` Schnittstelle stellt einen instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1c270-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="1c270-125">Beispielsweise würde Hashtable \< K, V> durch dargestellt `ICorDebugClass` , wohingegen Hash Table \< Int32, Zeichen folgen> durch dargestellt werden `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="1c270-126">Nicht generische Typen werden sowohl von `ICorDebugClass` als auch von dargestellt `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="1c270-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="1c270-127">Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="1c270-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c270-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1c270-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c270-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c270-129">Requirements</span></span>  
 <span data-ttu-id="1c270-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c270-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c270-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c270-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c270-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c270-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c270-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c270-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c270-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c270-134">See also</span></span>

- [<span data-ttu-id="1c270-135">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c270-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
