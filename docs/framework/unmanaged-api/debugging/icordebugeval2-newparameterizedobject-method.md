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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c35baaee13782566c64dd8447c6a034f699b5cd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667001"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="e4bbe-102">ICorDebugEval2::NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e4bbe-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="e4bbe-103">Instanziiert ein neues Objekt für den parametrisierten Typ und die Konstruktormethode des Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4bbe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4bbe-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4bbe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4bbe-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="e4bbe-106">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das den Konstruktor des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="e4bbe-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="e4bbe-108">[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die ein Typargument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="e4bbe-109">[in] Die Anzahl von Argumenten, die an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="e4bbe-110">[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugValue-Objekt verweist, die einen Wert des Arguments darstellt, der an den Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4bbe-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4bbe-111">Remarks</span></span>  
 <span data-ttu-id="e4bbe-112">Der Konstruktor des Objekts dauert <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4bbe-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4bbe-113">Requirements</span></span>  
 <span data-ttu-id="e4bbe-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4bbe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4bbe-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4bbe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4bbe-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4bbe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4bbe-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4bbe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
