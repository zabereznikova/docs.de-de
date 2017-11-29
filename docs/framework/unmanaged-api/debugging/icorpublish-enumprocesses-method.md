---
title: ICorPublish::EnumProcesses-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c556cffa95b4d6471b8a07954ec7b93ddbdb21c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses-Methode
Ruft einen Enumerator für die verwaltete Prozesse auf diesem Computer ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Type`  
 Der Wert der [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) -Enumeration, der den Typ des Prozesses abgerufen werden sollen. In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.  
  
 `ppIEnum`  
 Ein Zeiger auf die Adresse des ein [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) -Instanz, die der Enumerator der Prozesse ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Enumerator die Auflistung der Prozesse basiert auf einem Snapshot der Prozesse, die beim Ausführen der `EnumProcesses` -Methode aufgerufen wird. Der Enumerator enthält keine Prozesse, die vor dem Beenden oder starten, nachdem `EnumProcesses` aufgerufen wird.  
  
 Die `EnumProcesses` -Methode möglicherweise mehr als einmal aufgerufen werden, für dieses [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) Instanz eine neue Auflistung Prozesse auf dem neuesten Stand zu erstellen. Vorhandene Sammlungen nicht beeinträchtigt durch nachfolgende Aufrufe von der `EnumProcesses` Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorPublish-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
