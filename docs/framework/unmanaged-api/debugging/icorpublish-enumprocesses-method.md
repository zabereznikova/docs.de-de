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
ms.openlocfilehash: 70255a89cee13abfe63b01351f8ffba51e54665a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396400"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses-Methode
Ruft einen Enumerator für die verwalteten Prozesse ab, die auf diesem Computer ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Type`  
 Ein Wert der [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) -Enumeration, die den Typ des abzurufenden Prozesses angibt. In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.  
  
 `ppIEnum`  
 Ein Zeiger auf die Adresse einer [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) -Instanz, bei der es sich um den Enumerator der Prozesse handelt.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Auflistung der Prozesse des Enumerators basiert auf einer Momentaufnahme der Prozesse, die ausgeführt werden, wenn die- `EnumProcesses` Methode aufgerufen wird. Der Enumerator enthält keine Prozesse, die vor oder nach dem Aufruf von beendet werden `EnumProcesses` .  
  
 Die `EnumProcesses` Methode kann mehrmals für diese [ICorPublish](icorpublish-interface.md) -Instanz aufgerufen werden, um eine neue aktuelle Sammlung von Prozessen zu erstellen. Bei nachfolgenden Aufrufen der-Methode werden vorhandene Auflistungen nicht beeinträchtigt `EnumProcesses` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublish-Schnittstelle](icorpublish-interface.md)
