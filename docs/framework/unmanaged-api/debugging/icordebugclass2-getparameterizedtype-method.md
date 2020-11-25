---
title: ICorDebugClass2::GetParameterizedType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 139181975d16c2cdacec10ed646cfc2b8fb31a20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717993"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="7b067-102">ICorDebugClass2::GetParameterizedType-Methode</span><span class="sxs-lookup"><span data-stu-id="7b067-102">ICorDebugClass2::GetParameterizedType Method</span></span>

<span data-ttu-id="7b067-103">Ruft die Typdeklaration für diese Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="7b067-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b067-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b067-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b067-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b067-105">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="7b067-106">in Ein Wert der CorElementType-Enumeration, der den Elementtyp für diese Klasse angibt: Legen Sie diesen Wert auf ELEMENT_TYPE_VALUETYPE fest, wenn dieses ICorDebugClass2 einen Werttyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b067-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="7b067-107">Legen Sie diesen Wert auf ELEMENT_TYPE_CLASS fest, wenn dieser `ICorDebugClass2` einen komplexen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b067-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="7b067-108">in Die Anzahl der Typparameter, wenn der Typ generisch ist.</span><span class="sxs-lookup"><span data-stu-id="7b067-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="7b067-109">Die Anzahl der Typparameter (sofern vorhanden) muss mit der von der Klasse benötigten Anzahl identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7b067-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="7b067-110">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das einen Typparameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b067-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="7b067-111">Wenn die Klasse nicht generisch ist, ist dieser Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="7b067-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="7b067-112">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die Typdeklaration darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b067-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="7b067-113">Dieses Objekt entspricht einem- <xref:System.Type> Objekt in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="7b067-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b067-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b067-114">Remarks</span></span>  

 <span data-ttu-id="7b067-115">Wenn die Klasse nicht generisch ist, d. h., wenn Sie keine Typparameter aufweist, ruft `GetParameterizedType` einfach das Lauf Zeit Typen Objekt ab, das der-Klasse entspricht.</span><span class="sxs-lookup"><span data-stu-id="7b067-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="7b067-116">Der- `elementType` Parameter sollte auf den richtigen Elementtyp für die-Klasse festgelegt werden: ELEMENT_TYPE_VALUETYPE, wenn die Klasse ein Werttyp ist, andernfalls ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="7b067-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="7b067-117">Wenn die Klasse Typparameter akzeptiert (z. b `ArrayList<T>` .), können Sie verwenden, `GetParameterizedType` um ein Typobjekt für einen instanziierten Typ wie zu erstellen `ArrayList<int>` .</span><span class="sxs-lookup"><span data-stu-id="7b067-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="7b067-118">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="7b067-118">Background Information</span></span>  

 <span data-ttu-id="7b067-119">In den .NET Framework Versionen 1,0 und 1,1 kann jeder Typ in den Metadaten direkt einem Typ im laufenden Prozess zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7b067-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="7b067-120">Folglich verfügten ein Metadatentyp und ein Lauf Zeittyp im laufenden Prozess über eine einzelne Darstellung.</span><span class="sxs-lookup"><span data-stu-id="7b067-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="7b067-121">Allerdings kann ein generischer Typ in Metadaten vielen unterschiedlichen Instanziierungen des Typs im laufenden Prozess zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7b067-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="7b067-122">Beispielsweise kann der Metadatentyp `SortedList<K,V>` `SortedList<String, EmployeeRecord>` , `SortedList<Int32, String>` , `SortedList<String,Array<Int32>>` usw. zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7b067-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="7b067-123">Daher benötigen Sie eine Möglichkeit, die Typinstanziierung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b067-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="7b067-124">In der .NET Framework Version 2,0 wird die- `ICorDebugType` Schnittstelle eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7b067-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="7b067-125">Bei einem generischen Typ `ICorDebugClass` stellt ein `ICorDebugClass2` -oder-Objekt den nicht instanziierten Typ ( `SortedList<K,V>` ) dar, und ein- `ICorDebugType` Objekt stellt die verschiedenen instanziierten Typen dar.</span><span class="sxs-lookup"><span data-stu-id="7b067-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="7b067-126">Wenn Sie ein- `ICorDebugClass` oder- `ICorDebugClass2` Objekt haben, können Sie ein- `ICorDebugType` Objekt für jede Instanziierung erstellen, indem Sie die- `ICorDebugClass2::GetParameterizedType` Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7b067-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="7b067-127">Sie können auch ein- `ICorDebugType` Objekt für einen einfachen Typ erstellen, z. b. Int32, oder für einen nicht generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="7b067-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="7b067-128">Die Einführung des- `ICorDebugType` Objekts zur Darstellung der Lauf Zeit Darstellung eines Typs wirkt sich in der gesamten API auf einen Ripple-Effekt aus.</span><span class="sxs-lookup"><span data-stu-id="7b067-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="7b067-129">Funktionen, die zuvor ein- `ICorDebugClass` oder- `ICorDebugClass2` Objekt oder sogar einen-Wert übernommen haben `CorElementType` , werden verallgemeinert, um ein- `ICorDebugType` Objekt</span><span class="sxs-lookup"><span data-stu-id="7b067-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b067-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7b067-130">Requirements</span></span>  

 <span data-ttu-id="7b067-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b067-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b067-132">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b067-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b067-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b067-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b067-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b067-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
