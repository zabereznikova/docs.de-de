---
title: IHostMAlloc::DebugAlloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178035"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc-Methode
Fordert an, dass der Host die angegebene Speichermenge aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Speicher zugewiesen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbSize`  
 [in] Die Größe der aktuellen Speicherzuweisungsanforderung in Bytes.  
  
 `dwCriticalLevel`  
 [in] Einer der [EMemoryCriticalLevel-Werte,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) der die Auswirkungen eines Zuordnungsfehlers angibt.  
  
 `pszFileName`  
 [in] Die Codedatei der ausführbaren Datei, die gedebuggt wird.  
  
 `iLineNo`  
 [in] Die Positionsnummer, in `pszFileName` der die Zuordnung angefordert wurde.  
  
 `ppMem`  
 [out] Ein Zeiger auf den zugewiesenen Speicher oder NULL, wenn die Anforderung nicht abgeschlossen werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Zuweisungsanforderung abzuschließen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR ruft einen Schnittstellenzeiger auf eine [IHostMalloc-Instanz](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) ab, indem sie die [IHostMemoryManager::CreateMalloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) aufruft. `DebugAlloc`ermöglicht es der Laufzeit, Codedateiinformationen für die Verwendung während des Debuggens abzubekommen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
