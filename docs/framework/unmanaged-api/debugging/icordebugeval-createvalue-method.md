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
ms.openlocfilehash: 41db6ac00d8646651d0e8433d076c37af6020071
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696153"
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

 `CreateValue` erstellt ein `ICorDebugValue` Objekt des angegebenen Typs für den alleinigen Zweck der Verwendung in einer Funktions Auswertung. Dieses Wertobjekt kann verwendet werden, um Benutzer Konstanten als Parameter zu übergeben.  
  
 Wenn der Typ des Werts ein primitiver Typ ist, ist der anfängliche Wert 0 (null) oder NULL. Verwenden Sie [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) , um den Wert eines primitiven Typs festzulegen.  
  
 Wenn der Wert von `elementType` ELEMENT_TYPE_CLASS ist, erhalten Sie einen "ICorDebugReferenceValue" (zurückgegeben in `ppValue` ), der den NULL-Objekt Verweis darstellt. Sie können dieses Objekt verwenden, um NULL an eine Funktions Auswertung zu übergeben, die über Objekt Verweis Parameter verfügt. Sie können `ICorDebugValue` auf nichts festlegen. es bleibt immer NULL.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Weitere Informationen

- [CreateValueForType-Methode](icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval-Schnittstelle](icordebugeval-interface.md)
