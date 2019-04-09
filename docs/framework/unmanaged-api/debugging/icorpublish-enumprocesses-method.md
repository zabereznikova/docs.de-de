---
title: ICorPublish::EnumProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116294"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses-Methode
Ruft einen Enumerator für die verwaltete Prozesse auf diesem Computer ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Type`  
 Der Wert der [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) Enumeration, der angibt, den Typ des Prozesses abgerufen werden sollen. In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.  
  
 `ppIEnum`  
 Ein Zeiger auf die Adresse einer [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) -Instanz, die der Enumerator, der Prozesse ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Enumerator die Auflistung der Prozesse wird auf Grundlage einer Momentaufnahme der Prozesse, die beim Ausführen der `EnumProcesses` Methode wird aufgerufen. Der Enumerator enthält keine Prozesse, die vor dem Beenden oder starten Sie nach `EnumProcesses` aufgerufen wird.  
  
 Die `EnumProcesses` Methode kann mehrmals aufgerufen werden, dazu [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) Instanz eine neue aktuelle Auflistung von Prozessen erstellen. Vorhandene Sammlungen nicht betroffen von nachfolgenden Aufrufen der `EnumProcesses` Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublish-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
