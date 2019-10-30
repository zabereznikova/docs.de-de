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
ms.openlocfilehash: 867db3325f9b18b31f66429d01ea02be3603c0f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125758"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue-Methode
Ruft den Wert des angegebenen statischen Felds ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fieldDef`  
 in Ein Feld `Def` Token, das auf das Feld verweist, das abgerufen werden soll.  
  
 `pFrame`  
 in Ein Zeiger auf ein ICorDebugFrame-Objekt, das den Frame darstellt, der zum unterscheiden zwischen Thread-, Kontext-oder Anwendungs Domänen Statics verwendet werden soll.  
  
 Wenn das statische Feld relativ zu einem Thread, einem Kontext oder einer Anwendungsdomäne ist, bestimmt der Frame den richtigen Wert.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des statischen Felds darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Bei parametrisierten Typen ist der Wert eines statischen Felds relativ zur jeweiligen Instanziierung. Wenn der Klassenkonstruktor Parameter vom Typ <xref:System.Type>annimmt, müssen Sie daher [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) anstelle von `ICorDebugClass::GetStaticFieldValue`aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
