---
title: ICorPublishProcess::IsManaged-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421097"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged-Methode
Ruft einen Wert ab, der angibt, ob der Prozess, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md) verwiesen wird, über verwalteten Code verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbManaged`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess verwalteten Code aufweist. Der Wert ist `true` , wenn der Prozess verwalteten Code aufweist, andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  
 Da die aktuelle Version von `ICorPublishProcess` nur auf Prozesse mit verwaltetem Code zugreifen kann, `IsManaged` gibt immer zurück `true` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)
