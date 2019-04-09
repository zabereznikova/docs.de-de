---
title: ICorDebugProcess5::EnumerateGCReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0845165e3200d7a5e14715cbe116ea5255aa021
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178892"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences-Methode
Ruft einen Enumerator für alle Objekte, die in einem Prozess speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `enumerateWeakReferences`  
 [in] Ein boolescher Wert, der angibt, ob schwache Verweise ebenfalls aufgelistet werden sollen. Wenn `enumerateWeakReferences` ist `true`, `ppEnum` Enumerator umfasst starken Verweise und schwache Verweise. Wenn `enumerateWeakReferences` ist `false`, der Enumerator enthält, nur zuverlässige Verweise.  
  
 `ppEnum`  
 [out] Ein Zeiger auf die Adresse einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , einen Enumerator für die Objekte, das speicherbereinigt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode bietet eine Möglichkeit, um zu bestimmen, die vollständige rooting-Kette für ein verwaltetes Objekt in einem Prozess und kann verwendet werden, um zu bestimmen, warum ein Objekt noch aktiv ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
