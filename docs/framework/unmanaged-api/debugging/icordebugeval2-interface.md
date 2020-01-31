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
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788712"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="34f01-102">ICorDebugEval2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34f01-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="34f01-103">Erweitert "ICorDebugEval", um Unterstützung für generische Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34f01-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34f01-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="34f01-104">Methods</span></span>  
  
|<span data-ttu-id="34f01-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-105">Method</span></span>|<span data-ttu-id="34f01-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34f01-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34f01-107">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="34f01-108">Richtet einen aufzurufenden ' ICorDebugFunction ' ein, der in einem Typ geschachtelt werden kann, dessen Konstruktor Typparameter annimmt, oder selbst Typparameter annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="34f01-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="34f01-109">CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="34f01-110">Ruft einen Zeiger auf einen neuen "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von NULL oder 0 (null) ab.</span><span class="sxs-lookup"><span data-stu-id="34f01-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="34f01-111">NewParameterizedArray-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="34f01-112">Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.</span><span class="sxs-lookup"><span data-stu-id="34f01-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="34f01-113">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="34f01-114">Instanziiert ein neues parametrisiertes Typobjekt und ruft die Konstruktormethode des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="34f01-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="34f01-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="34f01-116">Instanziiert ein neues parametrisiertes Typobjekt der angegebenen Klasse, ohne dass versucht wird, eine Konstruktormethode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="34f01-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="34f01-117">NewStringWithLength-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="34f01-118">Erstellt eine neue Zeichenfolge mit der angegebenen Länge und dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="34f01-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="34f01-119">RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="34f01-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="34f01-120">Bricht die Berechnung ab, die von diesem `ICorDebugEval2` gerade durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34f01-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34f01-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34f01-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34f01-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="34f01-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f01-123">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34f01-123">Requirements</span></span>  
 <span data-ttu-id="34f01-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f01-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f01-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34f01-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f01-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34f01-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f01-127">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f01-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f01-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34f01-128">See also</span></span>

- [<span data-ttu-id="34f01-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="34f01-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
