---
title: ICorProfilerObjectEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: df1d5881bccdb357b16c7f02cd090388e0f66273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722803"
---
# <a name="icorprofilerobjectenumclone-method"></a>ICorProfilerObjectEnum::Clone-Methode

Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) -Schnittstelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppEnum`  
 vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser `ICorProfilerObjectEnum` Schnittstelle zeigt. Der Kopiervorgang behält seinen eigenen Enumerationszustand getrennt von diesem bei. Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerObjectEnum-Schnittstelle](icorprofilerobjectenum-interface.md)
