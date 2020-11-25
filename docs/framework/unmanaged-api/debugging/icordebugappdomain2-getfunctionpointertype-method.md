---
title: ICorDebugAppDomain2::GetFunctionPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: be797b1b3f288fd367d7f624e9cf33015dd114ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698272"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="7131c-102">ICorDebugAppDomain2::GetFunctionPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="7131c-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>

<span data-ttu-id="7131c-103">Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="7131c-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7131c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7131c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7131c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7131c-105">Parameters</span></span>  

 `nTypeArgs`  
 <span data-ttu-id="7131c-106">in Die Anzahl der Typargumente für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="7131c-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="7131c-107">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Typargument der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="7131c-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="7131c-108">Das erste Element ist der Rückgabetyp. Jedes der anderen Elemente ist ein Parametertyp.</span><span class="sxs-lookup"><span data-stu-id="7131c-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="7131c-109">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den Zeiger auf die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="7131c-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7131c-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7131c-110">Requirements</span></span>  

 <span data-ttu-id="7131c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7131c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7131c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7131c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7131c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7131c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7131c-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7131c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
