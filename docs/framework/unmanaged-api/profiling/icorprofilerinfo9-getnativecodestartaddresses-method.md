---
title: 'ICorProfilerInfo9:: getnativecodestartadressen'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973810"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: getnativecodestartadressen-Methode
  
 Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.   
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 in Die ID der Funktion, deren Start Adressen für den ursprünglichen Code zurückgegeben werden sollen.  
  
 `reJitId`  
 [in] Die Identität der erneut JIT-kompilierten Funktion. 
  
 `cCodeStartAddresses` \
 [in] Die maximale Größe des `codeStartAddresses`-Arrays.

 `pcCodeStartAddresses` \
 vorgenommen Die Anzahl der verfügbaren Adressen.

 `codeStartAddresses` \
 vorgenommen Ein-Array `UINT_PTR`, von dem jeder die Startadresse für einen systemeigenen Text für die angegebene Funktion ist. 

## <a name="remarks"></a>Hinweise  
 Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen. 

## <a name="requirements"></a>Anforderungen  
 **Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Header:** Corprof. idl, Corprof. h  
  
 **Fern** CorGuids.lib  
  
 **.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo9-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

