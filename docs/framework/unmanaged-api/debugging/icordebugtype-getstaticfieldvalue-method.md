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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663842"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue-Methode
Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld enthält Tokens in den angegebenen Stapelrahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fieldDef`  
 [in] Ein `mdFieldDef` -Token, das statische Feld angibt.  
  
 `pFrame`  
 [in] Ein Zeiger auf einen ICorDebugFrame, das den Stapelrahmen darstellt.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugValue` , den Wert des statischen Felds enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetStaticFieldValue` Methode kann verwendet werden nur dann, wenn der Typ ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE, ist wie durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.  
  
 Für nicht generische Typen, die Operation ausgeführt werden, indem `GetStaticFieldValue` entspricht dem Aufrufen von [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) auf das ICorDebugClass-Objekt, das von zurückgegebene [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Bei generischen Typen wird der Wert eines statischen Felds relativ zu einer bestimmten Instanziierung sein. Auch wenn das statische Feld möglicherweise relativ zu einem Thread, einen Kontext oder eine Anwendungsdomäne werden konnte, helfen klicken Sie dann der Stapelrahmen den Debugger den richtigen Wert zu ermitteln.  
  
## <a name="remarks"></a>Hinweise  
 `GetStaticFieldValue` kann verwendet werden, nur wenn ein Aufruf von `ICorDebugType::GetType` gibt einen Wert von ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
