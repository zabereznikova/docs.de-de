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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3ce303e8bcf33d192dbc7e2447ea6737577dcc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554876"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc-Methode
Fordert an, dass der Host die angegebene Menge des Arbeitsspeichers aus dem Heap reserviert, und zudem nachverfolgen, in dem der Speicher belegt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cbSize`  
 [in] Die Größe des die aktuelle speicherbelegungsanforderung in Bytes.  
  
 `dwCriticalLevel`  
 [in] Eines der [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Werte, der Sie die Auswirkungen eines zuordnungsfehlers angibt.  
  
 `pszFileName`  
 [in] Die Codedatei der debuggten, ausführbaren Datei.  
  
 `iLineNo`  
 [in] Die Zeilennummer im `pszFileName` , in denen die Belegung angefordert wurde.  
  
 `ppMem`  
 [out] Ein Zeiger auf den zugeordneten Arbeitsspeicher oder Null, wenn die Anforderung konnte nicht abgeschlossen werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`DebugAlloc` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft einen Schnittstellenzeiger auf ein [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode. `DebugAlloc` ermöglicht der Runtime beim Abrufen von Informationen zur Verwendung während des Debuggens Code.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
