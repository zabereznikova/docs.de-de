---
title: ICorDebugAppDomain2::GetArrayOrPointerType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetArrayOrPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c08a56ff7f6bd109c5568a7f992850708a22a4b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="ecace-102">ICorDebugAppDomain2::GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="ecace-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="ecace-103">Ruft ein Array des angegebenen Typs oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="ecace-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecace-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecace-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecace-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecace-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="ecace-106">[in] Der Wert der CorElementType-Enumeration, die angibt, die zugrunde liegenden systemeigenen Typ (ein Array, Zeiger oder Verweis) erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecace-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="ecace-107">[in] Der Rang (d. h. die Anzahl der Dimensionen) des Arrays.</span><span class="sxs-lookup"><span data-stu-id="ecace-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="ecace-108">Dieser Wert muss 0 sein, wenn `elementType` gibt einen Zeiger oder Verweis Typ an.</span><span class="sxs-lookup"><span data-stu-id="ecace-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="ecace-109">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des Arrays darstellt, Zeiger oder Verweis erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecace-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="ecace-110">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` geben Objekt, das die konstruierte Array, Zeigertyp oder Verweis darstellt.</span><span class="sxs-lookup"><span data-stu-id="ecace-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecace-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecace-111">Remarks</span></span>  
 <span data-ttu-id="ecace-112">Der Wert der *ElementType* muss eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="ecace-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="ecace-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="ecace-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="ecace-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="ecace-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="ecace-115">Einem oder ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="ecace-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="ecace-116">Wenn der Wert der *ElementType* ELEMENT_TYPE_PTR oder ELEMENT_TYPE_BYREF, *nRank* muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="ecace-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecace-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecace-117">Requirements</span></span>  
 <span data-ttu-id="ecace-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecace-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecace-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecace-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecace-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecace-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecace-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecace-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
