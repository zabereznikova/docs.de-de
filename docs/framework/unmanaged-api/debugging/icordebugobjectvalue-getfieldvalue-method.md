---
title: ICorDebugObjectValue::GetFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095881"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue-Methode
Ruft den Wert des angegebenen Felds der angegebenen Klasse für diesen Objektwert ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pClass`  
 in Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse darstellt, für die der Feldwert zu erhalten ist.  
  
 `fieldDef`  
 in Ein `mdFieldDef` Token, das auf die Metadaten verweist, die das Feld beschreiben.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf ein ICorDebugValue-Objekt, das den Wert des angegebenen Felds darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die im `pClass`-Parameter angegebene-Klasse muss sich in der Hierarchie der-Klasse des Objekt Werts befinden, und das Feld muss ein Feld dieser Klasse sein.  
  
 Die `GetFieldValue`-Methode ist für generische Objekte und generische Klassen weiterhin erfolgreich. Wenn z. b. MyDictionary\<V > von der Wörterbuch\<String, v > erbt und der Objektwert vom Typ MyDictionary\<Int32 > ist, wird ein Feld Wörterbuch\<Zeichenfolge, Int32 >.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
