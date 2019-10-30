---
title: IGCHost2::SetGCStartupLimitsEx-Methode
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: d78f81093e61c40eaec334f957d8583eeb593f5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134819"
---
# <a name="igchost2setgcstartuplimitsex-method"></a>IGCHost2::SetGCStartupLimitsEx-Methode
Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `SegmentSize`  
 in Die Größe des Segments, das vom Garbage Collection System verwendet wird.  
  
 `MaxGen0Size`  
 in Die maximale Größe für die Generation 0.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte, die `SetGCStartupLimitsEx` festgelegt haben, können nur angegeben werden, bevor der Host gestartet wird. Diese Werte können später nicht mehr geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IGCHost2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
