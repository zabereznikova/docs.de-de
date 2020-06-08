---
title: ICorProfilerFunctionEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: d6f348eb781efdef89926ec1bc267281bf3a5004
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503106"
---
# <a name="icorprofilerfunctionenumclone-method"></a>ICorProfilerFunctionEnum::Clone-Methode
Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) -Schnittstelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
 vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) -Schnittstelle zeigt. Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator. Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerFunctionEnum-Schnittstelle](icorprofilerfunctionenum-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
