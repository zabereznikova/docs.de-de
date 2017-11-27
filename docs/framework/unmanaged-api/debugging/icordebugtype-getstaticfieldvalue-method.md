---
title: ICorDebugType::GetStaticFieldValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="00e42-102">ICorDebugType::GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="00e42-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="00e42-103">Ruft einen Schnittstellenzeiger auf eine ICorDebugValue-Objekt, das den Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld enthält token in den angegebenen Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="00e42-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00e42-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00e42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00e42-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="00e42-106">[in] Ein `mdFieldDef` -Token, das statische Feld angibt.</span><span class="sxs-lookup"><span data-stu-id="00e42-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="00e42-107">[in] Ein Zeiger auf ein ICorDebugFrame, das den Stapelrahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="00e42-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="00e42-108">[out] Ein Zeiger auf die Adresse des ein `ICorDebugValue` , den Wert des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="00e42-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00e42-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00e42-109">Remarks</span></span>  
 <span data-ttu-id="00e42-110">Die `GetStaticFieldValue` Methode wird möglicherweise verwendet nur, wenn der Typ ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE, ist durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="00e42-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="00e42-111">Für nicht generische Typen, die Operation ausgeführt werden, indem `GetStaticFieldValue` entspricht dem Aufruf [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) auf das ICorDebugClass-Objekt, das von zurückgegebene [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="00e42-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="00e42-112">Bei generischen Typen wird der Wert eines statischen Felds relativ zu einer bestimmten Instanziierung sein.</span><span class="sxs-lookup"><span data-stu-id="00e42-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="00e42-113">Wenn das statische Feld möglicherweise relativ zu einem Thread, einem Kontext oder eine Anwendungsdomäne werden konnte, können der Stapelrahmen außerdem den Debugger den richtigen Wert zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="00e42-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00e42-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00e42-114">Remarks</span></span>  
 <span data-ttu-id="00e42-115">`GetStaticFieldValue`kann verwendet werden, nur bei einem Aufruf von `ICorDebugType::GetType` einen Wert des ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="00e42-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00e42-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00e42-116">Requirements</span></span>  
 <span data-ttu-id="00e42-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00e42-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00e42-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00e42-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00e42-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00e42-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00e42-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00e42-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
