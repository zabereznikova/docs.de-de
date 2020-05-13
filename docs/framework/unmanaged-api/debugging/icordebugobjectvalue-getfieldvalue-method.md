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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207591"
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
 Die-Klasse, die im-Parameter angegeben ist `pClass` , muss sich in der Hierarchie der-Klasse des Objekt Werts befinden, und das Feld muss ein Feld dieser Klasse sein.  
  
 Die `GetFieldValue` -Methode kann für generische Objekte und generische Klassen weiterhin erfolgreich ausgeführt werden. Wenn z. b. MyDictionary \< V> von der Wörterbuch \< Zeichenfolge erbt, v>, und der Objektwert vom Typ MyDictionary \< Int32> ist, wird bei der Übergabe des `ICorDebugClass` Objekts für das Wörterbuch \< K v> erfolgreich ein Feld der Wörterbuch \< Zeichenfolge Int32> erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
