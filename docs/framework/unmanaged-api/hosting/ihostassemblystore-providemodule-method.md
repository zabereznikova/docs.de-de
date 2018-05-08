---
title: IHostAssemblyStore::ProvideModule-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b604e1d7fc3d3c8adf7d95bd95843bc0110dbc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule-Methode
Löst eine Modul innerhalb einer Assembly oder einer verknüpften (jedoch nicht eingebetteten) Ressourcendatei.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBindInfo`  
 [in] Ein Zeiger auf eine [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) Instanz, die des angeforderten Moduls beschreibt <xref:System.AppDomain>, Assembly und der Name des Moduls.  
  
 `pdwModuleId`  
 [out] Ein Zeiger auf einen eindeutigen Bezeichner für die `IStream` , enthält das geladene Modul.  
  
 `ppStmModuleImage`  
 [out] Ein Zeiger auf die Adresse des ein `IStream` Objekts, das enthält die Datei (portable Executable)-Image geladen werden, oder null, wenn das Modul nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 [out] Ein Zeiger auf die Adresse des ein `IStream` Objekts, das Programm (PDB) Debuginformationen für das angeforderte Modul enthält, oder null, wenn die PDB-Datei nicht gefunden werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ProvideModule` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0 X 80070002)|Die angeforderte Assembly oder verknüpfte Ressource konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` ist nicht groß genug für den Bezeichner enthalten, den möchte, dass der Host zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Der Identitätswert zurückgegeben wird, für die `pdwModuleId` wird vom Host angegeben. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den zugeordneten Stream. Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die durch Aufrufe von [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) und mit den Werten für `pdwModuleId` zurückgegeben, die von anderen Aufrufen von `ProvideModule`. Wenn der Host den gleichen Bezeichnerwert für eine andere zurückgibt `IStream`, die CLR überprüft, ob der Inhalt dieses Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Abbilds statt ein neues Konto zuordnen. Aus diesem Grund der Bezeichner muss auch nicht überschneiden sich mit der Assembly-IDs, die von zurückgegeben `ProvideAssembly`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
