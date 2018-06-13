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
ms.openlocfilehash: 2b136f30b0c1ce9f83228f340ac5e147cc02002b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422028"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue-Methode
Ruft einen Schnittstellenzeiger auf eine ICorDebugValue-Objekt, das den Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld enthält token in den angegebenen Stapelrahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fieldDef`  
 [in] Ein `mdFieldDef` -Token, das statische Feld angibt.  
  
 `pFrame`  
 [in] Ein Zeiger auf ein ICorDebugFrame, das den Stapelrahmen darstellt.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse des ein `ICorDebugValue` , den Wert des statischen Felds enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetStaticFieldValue` Methode wird möglicherweise verwendet nur, wenn der Typ ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE, ist durch die [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) Methode.  
  
 Für nicht generische Typen, die Operation ausgeführt werden, indem `GetStaticFieldValue` entspricht dem Aufruf [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) auf das ICorDebugClass-Objekt, das von zurückgegebene [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Bei generischen Typen wird der Wert eines statischen Felds relativ zu einer bestimmten Instanziierung sein. Wenn das statische Feld möglicherweise relativ zu einem Thread, einem Kontext oder eine Anwendungsdomäne werden konnte, können der Stapelrahmen außerdem den Debugger den richtigen Wert zu bestimmen.  
  
## <a name="remarks"></a>Hinweise  
 `GetStaticFieldValue` kann verwendet werden, nur bei einem Aufruf von `ICorDebugType::GetType` einen Wert des ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE zurückgibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
