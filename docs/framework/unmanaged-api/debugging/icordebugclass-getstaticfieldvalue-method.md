---
title: ICorDebugClass::GetStaticFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: 873dd5a1eb2c9356049d2d0c0cb495b963c2ae46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784190"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="9e911-102">ICorDebugClass::GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="9e911-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="9e911-103">Ruft den Wert des angegebenen statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="9e911-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e911-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e911-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e911-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9e911-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="9e911-106">in Ein Feld `Def` Token, das auf das Feld verweist, das abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e911-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="9e911-107">in Ein Zeiger auf ein ICorDebugFrame-Objekt, das den Frame darstellt, der zum unterscheiden zwischen Thread-, Kontext-oder Anwendungs Domänen Statics verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e911-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="9e911-108">Wenn das statische Feld relativ zu einem Thread, einem Kontext oder einer Anwendungsdomäne ist, bestimmt der Frame den richtigen Wert.</span><span class="sxs-lookup"><span data-stu-id="9e911-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9e911-109">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des statischen Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="9e911-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e911-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e911-110">Remarks</span></span>  
 <span data-ttu-id="9e911-111">Bei parametrisierten Typen ist der Wert eines statischen Felds relativ zur jeweiligen Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="9e911-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="9e911-112">Wenn der Klassenkonstruktor Parameter vom Typ <xref:System.Type>annimmt, müssen Sie daher [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) anstelle von `ICorDebugClass::GetStaticFieldValue`aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9e911-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e911-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e911-113">Requirements</span></span>  
 <span data-ttu-id="9e911-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e911-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e911-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e911-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e911-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e911-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e911-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e911-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
