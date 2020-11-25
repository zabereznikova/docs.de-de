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
ms.openlocfilehash: 090b587ef509795609250914ce8883ad96d28c18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729680"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="c203c-102">ICorDebugEval2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c203c-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="c203c-103">Erweitert "ICorDebugEval", um Unterstützung für generische Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c203c-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c203c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c203c-104">Methods</span></span>  
  
|<span data-ttu-id="c203c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-105">Method</span></span>|<span data-ttu-id="c203c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c203c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c203c-107">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="c203c-108">Richtet einen aufzurufenden ' ICorDebugFunction ' ein, der in einem Typ geschachtelt werden kann, dessen Konstruktor Typparameter annimmt, oder selbst Typparameter annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="c203c-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="c203c-109">CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="c203c-110">Ruft einen Zeiger auf einen neuen "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von NULL oder 0 (null) ab.</span><span class="sxs-lookup"><span data-stu-id="c203c-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="c203c-111">NewParameterizedArray-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="c203c-112">Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.</span><span class="sxs-lookup"><span data-stu-id="c203c-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="c203c-113">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="c203c-114">Instanziiert ein neues parametrisiertes Typobjekt und ruft die Konstruktormethode des Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="c203c-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="c203c-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="c203c-116">Instanziiert ein neues parametrisiertes Typobjekt der angegebenen Klasse, ohne dass versucht wird, eine Konstruktormethode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c203c-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="c203c-117">NewStringWithLength-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="c203c-118">Erstellt eine neue Zeichenfolge mit der angegebenen Länge und dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c203c-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="c203c-119">RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="c203c-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="c203c-120">Bricht die `ICorDebugEval2` aktuell durchführte Berechnung ab.</span><span class="sxs-lookup"><span data-stu-id="c203c-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c203c-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c203c-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c203c-122">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c203c-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c203c-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c203c-123">Requirements</span></span>  

 <span data-ttu-id="c203c-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c203c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c203c-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c203c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c203c-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c203c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c203c-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c203c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c203c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c203c-128">See also</span></span>

- [<span data-ttu-id="c203c-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c203c-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
