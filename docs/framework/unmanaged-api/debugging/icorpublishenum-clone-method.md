---
title: ICorPublishEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 44ecba99999d04603477f411e68834548f6a7cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693553"
---
# <a name="icorpublishenumclone-method"></a>ICorPublishEnum::Clone-Methode

Erstellt eine Kopie dieses [ICorPublishEnum](icorpublishenum-interface.md) -Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorPublishEnum` Objekts, das eine Kopie dieses Objekts ist `ICorPublishEnum` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorPublishEnum-Schnittstelle](icorpublishenum-interface.md)
