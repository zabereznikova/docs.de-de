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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750850"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="ecae5-102">ICorDebugClass::GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ecae5-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="ecae5-103">Ruft den Wert des angegebenen statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="ecae5-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecae5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecae5-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecae5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecae5-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="ecae5-106">[in] Ein Feld `Def` -Token, verweist das Feld abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ecae5-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="ecae5-107">[in] Ein Zeiger auf ein ICorDebugFrame-Objekt, das den Rahmen verwendet werden, um Mehrdeutigkeiten zwischen Thread oder Kontext Anwendung Mehrdeutigkeit aufzulösen darstellt.</span><span class="sxs-lookup"><span data-stu-id="ecae5-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="ecae5-108">Wenn das statische Feld relativ zu einem Thread, einen Kontext oder eine Anwendungsdomäne ist, wird der Frame den richtigen Wert bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ecae5-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ecae5-109">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des statischen Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="ecae5-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecae5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecae5-110">Remarks</span></span>  
 <span data-ttu-id="ecae5-111">Für parametrisierte Typen bezieht die bestimmten Instanziierung der Wert eines statischen Felds.</span><span class="sxs-lookup"><span data-stu-id="ecae5-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="ecae5-112">Aus diesem Grund, wenn der Konstruktor der Klasse Parameter des Typs <xref:System.Type>, rufen Sie [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) anstelle von `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="ecae5-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecae5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecae5-113">Requirements</span></span>  
 <span data-ttu-id="ecae5-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecae5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecae5-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecae5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecae5-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecae5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecae5-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecae5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
