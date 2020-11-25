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
ms.openlocfilehash: 745be25183f6b94e7a807c4230961d72e2836fe5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695334"
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
  
 Die `GetFieldValue` -Methode kann für generische Objekte und generische Klassen weiterhin erfolgreich ausgeführt werden. Wenn z. b. MyDictionary \<V> vom-Wörterbuch erbt \<string,V> und der Objektwert den Typ MyDictionary \<int32> hat, erhält das Übergeben des- `ICorDebugClass` Objekts für das Wörterbuch \<K,V> erfolgreich ein Wörterbuch \<string,int32> .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
