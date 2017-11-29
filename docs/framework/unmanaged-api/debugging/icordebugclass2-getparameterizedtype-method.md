---
title: ICorDebugClass2::GetParameterizedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0df76f43ad037a4681f985e99401cb8c7f5a2ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="84d36-102">ICorDebugClass2::GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="84d36-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="84d36-103">Ruft die Typdeklaration für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="84d36-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84d36-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84d36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84d36-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="84d36-106">[in] Ein Wert, der CorElementType-Enumeration, der den Elementtyp für diese Klasse angibt: Legen Sie diesen Wert auf ELEMENT_TYPE_VALUETYPE fest, wenn ICorDebugClass2 einen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="84d36-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="84d36-107">Legen Sie diesen Wert auf ELEMENT_TYPE_CLASS fest, wenn diese `ICorDebugClass2` stellt einen komplexen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="84d36-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="84d36-108">[in] Die Anzahl von Typparametern, wenn der Typ generisch ist.</span><span class="sxs-lookup"><span data-stu-id="84d36-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="84d36-109">Die Anzahl der Typparameter (sofern vorhanden) muss von der Klasse erforderliche Anzahl übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="84d36-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="84d36-110">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die einen Typparameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="84d36-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="84d36-111">Wenn die Klasse nicht generisch ist, ist dieser Wert null.</span><span class="sxs-lookup"><span data-stu-id="84d36-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="84d36-112">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das die Typdeklaration darstellt.</span><span class="sxs-lookup"><span data-stu-id="84d36-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="84d36-113">Dieses Objekt entspricht einem <xref:System.Type> Objekt in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="84d36-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d36-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84d36-114">Remarks</span></span>  
 <span data-ttu-id="84d36-115">Wenn die Klasse nicht-generische, d. h. wenn es sich um keine Typparameter aufweist `GetParameterizedType` einfach ruft der Klasse entsprechende Common Language Runtime-Typ-Objekt.</span><span class="sxs-lookup"><span data-stu-id="84d36-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="84d36-116">Die `elementType` Parameter sollte in den richtigen Elementtyp für die Klasse festgelegt werden: ELEMENT_TYPE_VALUETYPE, wenn die Klasse ein Werttyp ist, andernfalls ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="84d36-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="84d36-117">Wenn die Klasse Typparameter akzeptiert (z. B. `ArrayList<T>`), können Sie `GetParameterizedType` So erstellen Sie ein Objekt vom Typ für einen instanziierten Typ wie z. B. `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="84d36-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="84d36-118">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="84d36-118">Background Information</span></span>  
 <span data-ttu-id="84d36-119">In der .NET Framework-Versionen 1.0 und 1.1 konnte jeder Typ in den Metadaten direkt zu einem Typ in den laufenden Prozess zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="84d36-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="84d36-120">Daher musste ein Metadatentyp und einen Laufzeittyp eine einzelne Darstellung in der ausgeführte Prozess.</span><span class="sxs-lookup"><span data-stu-id="84d36-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="84d36-121">Allerdings kann einen generischer Typ in den Metadaten auf vielen verschiedenen Instanziierungen des Typs in der laufenden Prozess zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="84d36-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="84d36-122">Z. B. der Metadatentyp `SortedList<K,V>` können zuordnen `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="84d36-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="84d36-123">Daher benötigen Sie eine Möglichkeit zum Verarbeiten von Typinstanziierung.</span><span class="sxs-lookup"><span data-stu-id="84d36-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="84d36-124">.NET Framework, Version 2.0 führt die `ICorDebugType` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="84d36-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="84d36-125">Für einen generischen Typ ein `ICorDebugClass` oder `ICorDebugClass2` Objekt darstellt, den nicht instanziierten Typ (`SortedList<K,V>`), und ein `ICorDebugType` -Objekt stellt die verschiedenen instanziierten Typen dar.</span><span class="sxs-lookup"><span data-stu-id="84d36-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="84d36-126">Erhält ein `ICorDebugClass` oder `ICorDebugClass2` -Objekt können Sie erstellen eine `ICorDebugType` Objekt für jede Instanziierung durch Aufrufen der `ICorDebugClass2::GetParameterizedType` Methode.</span><span class="sxs-lookup"><span data-stu-id="84d36-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="84d36-127">Sie können auch erstellen, ein `ICorDebugType` Objekt für einen einfachen Typ, z. B. Int32, oder für einen nichtgenerischen Typ.</span><span class="sxs-lookup"><span data-stu-id="84d36-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="84d36-128">Die Einführung der `ICorDebugType` Objekt zur Darstellung des Begriff zur Laufzeit einen Typ hat einen Welleneffekt während der API.</span><span class="sxs-lookup"><span data-stu-id="84d36-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="84d36-129">Funktionen, die zuvor dauerte ein `ICorDebugClass` oder `ICorDebugClass2` -Objekt oder sogar eine `CorElementType` Wert werden generalisiert, um nehmen eine `ICorDebugType` Objekt.</span><span class="sxs-lookup"><span data-stu-id="84d36-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d36-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84d36-130">Requirements</span></span>  
 <span data-ttu-id="84d36-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d36-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d36-132">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84d36-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d36-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d36-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d36-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d36-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
