---
title: ICorDebugEval2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4315c9f5296e8c3ffc9d8241b929c71c2448db6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965862"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="882d7-102">ICorDebugEval2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="882d7-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="882d7-103">Erweitert "ICorDebugEval", um Unterstützung für generische Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="882d7-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="882d7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="882d7-104">Methods</span></span>  
  
|<span data-ttu-id="882d7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-105">Method</span></span>|<span data-ttu-id="882d7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="882d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="882d7-107">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="882d7-108">Richtet einen Aufruf der angegebenen "ICorDebugFunction", die innerhalb eines Typs, dessen Konstruktor Parameter vom Typ annimmt, oder kann selbst Parameter vom Typ, geschachtelt werden können.</span><span class="sxs-lookup"><span data-stu-id="882d7-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="882d7-109">CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="882d7-110">Ruft einen Zeiger auf einen neuen "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von 0 oder NULL ab.</span><span class="sxs-lookup"><span data-stu-id="882d7-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="882d7-111">NewParameterizedArray-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="882d7-112">Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.</span><span class="sxs-lookup"><span data-stu-id="882d7-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="882d7-113">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="882d7-114">Instanziiert ein neues Objekt für den parametrisierten Typ und die Konstruktormethode des Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="882d7-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="882d7-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="882d7-116">Instanziiert ein neues parametrisierten Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen</span><span class="sxs-lookup"><span data-stu-id="882d7-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="882d7-117">NewStringWithLength-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="882d7-118">Erstellt eine neue Zeichenfolge mit der angegebenen Länge mit dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="882d7-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="882d7-119">RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="882d7-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="882d7-120">Bricht ab, der Berechnung, die dieses `ICorDebugEval2` wird derzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="882d7-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="882d7-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="882d7-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="882d7-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="882d7-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="882d7-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="882d7-123">Requirements</span></span>  
 <span data-ttu-id="882d7-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="882d7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="882d7-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="882d7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="882d7-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="882d7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="882d7-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="882d7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882d7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="882d7-128">See also</span></span>
- [<span data-ttu-id="882d7-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="882d7-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
