---
title: ICorDebugEval2::NewParameterizedObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 5d01ab0b6b5d489b2181056129e22661a50108a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084846"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="68e56-102">ICorDebugEval2::NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="68e56-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="68e56-103">Instanziiert ein neues parametrisiertes Typobjekt und ruft die Konstruktormethode des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="68e56-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68e56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68e56-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68e56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68e56-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="68e56-106">in Ein Zeiger auf ein ICorDebugFunction-Objekt, das den Konstruktor des Objekts darstellt, das instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="68e56-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="68e56-107">in Die Anzahl der bestandenen Typargumente.</span><span class="sxs-lookup"><span data-stu-id="68e56-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="68e56-108">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Typargument für das Objekt darstellt, das instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="68e56-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="68e56-109">in Die Anzahl von Argumenten, die an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="68e56-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="68e56-110">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugValue-Objekt verweist, das einen Argument Wert darstellt, der an den Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="68e56-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68e56-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68e56-111">Remarks</span></span>  
 <span data-ttu-id="68e56-112">Der Konstruktor des Objekts kann <xref:System.Type> Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="68e56-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68e56-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68e56-113">Requirements</span></span>  
 <span data-ttu-id="68e56-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68e56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68e56-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68e56-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68e56-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68e56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68e56-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68e56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
