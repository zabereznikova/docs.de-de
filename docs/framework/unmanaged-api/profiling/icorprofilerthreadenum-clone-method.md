---
title: ICorProfilerThreadEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: 890bb9bdd3b639d38f4f290eed86ad72b6a53f0f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494448"
---
# <a name="icorprofilerthreadenumclone-method"></a>ICorProfilerThreadEnum::Clone-Methode
Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [icorprofilerthreadenum](icorprofilerthreadenum-interface.md) -Schnittstelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
 vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [icorprofilerthreadenum](icorprofilerthreadenum-interface.md) -Schnittstelle zeigt. Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator. Die ursprüngliche Cursorposition der Kopie ist jedoch mit der aktuellen Cursorposition des Enumerators identisch.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
