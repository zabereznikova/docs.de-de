---
title: ICorDebugType::GetStaticFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791274"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="f6240-102">ICorDebugType::GetStaticFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f6240-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="f6240-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f6240-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6240-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6240-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6240-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f6240-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="f6240-106">in Ein `mdFieldDef` Token, das das statische Feld angibt.</span><span class="sxs-lookup"><span data-stu-id="f6240-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="f6240-107">in Ein Zeiger auf ein ICorDebug Frame-Element, das den Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="f6240-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f6240-108">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugValue`, die den Wert des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="f6240-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6240-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6240-109">Remarks</span></span>  
 <span data-ttu-id="f6240-110">Die `GetStaticFieldValue`-Methode kann nur verwendet werden, wenn der Typ ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, wie durch die [ICorDebugType:: GetType](icordebugtype-gettype-method.md) -Methode angegeben.</span><span class="sxs-lookup"><span data-stu-id="f6240-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="f6240-111">Bei nicht generischen Typen ist der von `GetStaticFieldValue` ausgeführte Vorgang identisch mit dem Aufruf von [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) für das ICorDebugClass-Objekt, das von [ICorDebugType:: GetClass](icordebugtype-getclass-method.md)zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f6240-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="f6240-112">Bei generischen Typen ist ein statischer Feldwert relativ zu einer bestimmten Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="f6240-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="f6240-113">Wenn das statische Feld möglicherweise relativ zu einem Thread, einem Kontext oder einer Anwendungsdomäne sein kann, unterstützt der Stapel Rahmen den richtigen Wert für den Debugger.</span><span class="sxs-lookup"><span data-stu-id="f6240-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6240-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6240-114">Remarks</span></span>  
 <span data-ttu-id="f6240-115">`GetStaticFieldValue` können nur verwendet werden, wenn ein-Aufruf`ICorDebugType::GetType` den Wert ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f6240-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6240-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6240-116">Requirements</span></span>  
 <span data-ttu-id="f6240-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6240-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6240-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6240-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6240-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6240-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6240-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6240-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
