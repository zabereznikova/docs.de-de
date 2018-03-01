---
title: ICorDebugObjectValue::GetFieldValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fcf53610cf96ef1ab62b4768521e8a2fb7ee6c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue-Methode
Ruft den Wert des angegebenen Felds der angegebenen Klasse für den Wert dieses Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pClass`  
 [in] Ein Zeiger auf ein "ICorDebugClass"-Objekt, das die Klasse für das Abrufen des Wert des Felds darstellt.  
  
 `fieldDef`  
 [in] Ein `mdFieldDef` -Token, die Metadaten zum Beschreiben des Felds verweist.  
  
 `ppValue`  
 [out] Ein Zeiger auf ein "ICorDebugValue"-Objekt, das den Wert des angegebenen Felds darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse, angegeben der `pClass` -Parameter muss in der Hierarchie den Objektwert-Klasse, und das Feld muss ein Feld dieser Klasse.  
  
 Die `GetFieldValue` Methode ist für generische Objekte und generische Klassen dennoch erfolgreich. Z. B. wenn MyDictionary\<V > erbt von Wörterbuch\<"string", "V >, und der Wert des Objekts vom Typ MyDictionary\<int32 >, und übergeben Sie die `ICorDebugClass` Objekt für das Wörterbuch\<K, V > wird ein Feld des Wörterbuchs abgerufen\<String, int32 >.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
 
