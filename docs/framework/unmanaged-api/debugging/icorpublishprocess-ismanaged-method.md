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
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790527"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged-Methode
Ruft einen Wert ab, der angibt, ob der Prozess, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md) verwiesen wird, über verwalteten Code verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pbManaged`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess verwalteten Code aufweist. Der Wert ist `true`, wenn der Prozess verwalteten Code hat. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Da die aktuelle Version von `ICorPublishProcess` nur Zugriff auf Prozesse zulässt, die über verwalteten Code verfügen, gibt `IsManaged` immer `true`zurück.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)
