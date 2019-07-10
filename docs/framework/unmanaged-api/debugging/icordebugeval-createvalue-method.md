---
title: ICorDebugEval::CreateValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ada3a06a2beb8f21c3e24665c0f1f8e7c48515f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752955"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue-Methode
Erstellt einen Wert des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null.  
  
 Diese Methode ist in .NET Framework, Version 2.0, veraltet. Verwendung [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Der Wert der [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) -Enumeration, der den Typ des Werts angibt.  
  
 `pElementClass`  
 [in] Zeiger auf ein [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) Objekt, das die Klasse des-Werts angibt, wenn der Typ nicht um einen primitiven Typ ist.  
  
 `ppValue`  
 [out] Zeiger auf die Adresse ein "ICorDebugValue"-Objekt, das den Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `CreateValue` erstellt eine `ICorDebugValue` Objekt des angegebenen Typs für den Zweck der Verwendung in eine funktionsauswertung. Dieser Wertobjekt kann verwendet werden, Benutzerkonstanten als Parameter übergeben wird.  
  
 Wenn der Typ des Werts ein primitiver Typ ist, wird ihren anfänglichen Wert 0 (null) oder null. Verwendung [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) zum Festlegen des Werts eines primitiven Typs.  
  
 Wenn der Wert des `elementType` ELEMENT_TYPE_CLASS lautet, erhalten Sie eine "ICorDebugReferenceValue" (im zurückgegebenen `ppValue`), der null-Objektverweis darstellt. Sie können dieses Objekt verwenden, null, eine funktionsauswertung übergeben, die Objektverweisparameter verfügt. Sie können nicht festgelegt werden die `ICorDebugValue` auf nichts, es bleibt immer null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch

- [CreateValueForType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval-Schnittstelle](icordebugeval-interface.md)
