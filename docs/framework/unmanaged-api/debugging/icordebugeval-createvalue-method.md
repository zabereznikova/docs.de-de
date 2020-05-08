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
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976251"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue-Methode
Erstellt einen Wert vom angegebenen Typ mit einem Anfangswert von 0 (null) oder NULL.  
  
 Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugEval2:: kreatevaluefortype](icordebugeval2-createvaluefortype-method.md) .  
  
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
 in Ein Wert der [CorElementType](../metadata/corelementtype-enumeration.md) -Enumeration, der den Typ des Werts angibt.  
  
 `pElementClass`  
 in Ein Zeiger auf ein [ICorDebugClass](icordebugclass-interface.md) -Objekt, das die Klasse des Werts angibt, wenn der Typ kein primitiver Typ ist.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `CreateValue`erstellt ein `ICorDebugValue` Objekt des angegebenen Typs für den alleinigen Zweck der Verwendung in einer Funktions Auswertung. Dieses Wertobjekt kann verwendet werden, um Benutzer Konstanten als Parameter zu übergeben.  
  
 Wenn der Typ des Werts ein primitiver Typ ist, ist der anfängliche Wert 0 (null) oder NULL. Verwenden Sie [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) , um den Wert eines primitiven Typs festzulegen.  
  
 Wenn der Wert von `elementType` ELEMENT_TYPE_CLASS ist, erhalten Sie einen "ICorDebugReferenceValue" (zurückgegeben `ppValue`in), der den NULL-Objekt Verweis darstellt. Sie können dieses Objekt verwenden, um NULL an eine Funktions Auswertung zu übergeben, die über Objekt Verweis Parameter verfügt. Sie können den `ICorDebugValue` nicht auf "nichts" festlegen. Sie bleibt immer NULL.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Weitere Informationen

- [CreateValueForType-Methode](icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval-Schnittstelle](icordebugeval-interface.md)
