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
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687872"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits-Methode

Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.  
  
> [!IMPORTANT]
> Beginnend mit dem .NET Framework 4,5 können Sie die Segmentgröße und die maximale Generation 0-Größe auf Werte festlegen, die größer als sind, `DWORD` indem Sie die [IGCHost2:: setgcstartuplimitsex](igchost2-setgcstartuplimitsex-method.md) -Methode verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `SegmentSize`  
 in Die Größe des Segments, das vom Garbage Collection System verwendet wird.  
  
 `MaxGen0Size`  
 in Die maximale Größe für die Generation 0.  
  
## <a name="remarks"></a>Hinweise  

 Die- `SetGCStartupLimits` Methode kann nur einmal aufgerufen werden. Diese Werte können später nicht mehr geändert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IGCHost-Schnittstelle](igchost-interface.md)
