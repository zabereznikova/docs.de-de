---
title: IGCHost::SetGCStartupLimits-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9104550438a2a066cdf052b8d6592e86b831194
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749986"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits-Methode
Legt die Größe des Segments und die maximale Größe für Generation 0 fest.  
  
> [!IMPORTANT]
>  Ab .NET Framework 4.5, Sie können festlegen Segmentgröße und Größe von maximal Generation 0 zu Werten größer als `DWORD` mithilfe der [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `SegmentSize`  
 [in] Die Größe des Segments, die von der Garbage Collection-System verwendet werden soll.  
  
 `MaxGen0Size`  
 [in] Die maximale Größe für Generation 0.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetGCStartupLimits` Methode nur einmal aufgerufen werden kann. Diese Werte können nicht später geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
