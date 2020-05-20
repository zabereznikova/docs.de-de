---
title: ICLRProbingAssemblyEnum::Get-Methode
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: ea66c142afc097d1003df4e7f5f5b960a91e2ab0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703389"
---
# <a name="iclrprobingassemblyenumget-method"></a>ICLRProbingAssemblyEnum::Get-Methode
Ruft die Assemblyidentität am angegebenen Index ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwIndex`  
 in Der null basierte Index der zurück zugebende Assemblyidentität.  
  
 `pwzBuffer`  
 vorgenommen Ein Puffer mit den Assemblyidentitätsdaten.  
  
 `pcchBufferSize`  
 [in, out] Die Größe des `pwzBuffer` Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`Get`wurde erfolgreich zurückgegeben.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` ist zu klein.|  
|ERROR_NO_MORE_ITEMS|Die-Enumeration enthält keine weiteren Elemente.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe an beliebige Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die Identität bei Index 0 ist die Identität, die für die Prozessorarchitektur spezifisch ist. Die Identität bei Index 1 ist die Architektur neutrale Assembly für Microsoft Intermediate Language (MSIL). Die Identität am Index 2 enthält keine Architektur Informationen.  
  
 `Get`wird in der Regel zweimal aufgerufen. Der erste-Befehl stellt einen NULL-Wert für bereit `pwzBuffer` und legt `pcchBufferSize` auf die für geeignete Größe fest `pwzBuffer` . Der zweite-Rückruf stellt eine angemessene Größenanpassung dar `pwzBuffer` und enthält die kanonischen Assemblyidentitätsdaten bei Abschluss.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRProbingAssemblyEnum-Schnittstelle](iclrprobingassemblyenum-interface.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
