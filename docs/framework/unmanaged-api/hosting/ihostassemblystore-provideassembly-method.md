---
title: IHostAssemblyStore::ProvideAssembly-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fab4ef0d67ab6b86510bd4b2f814d9456213fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763992"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly-Methode
Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) von zurückgegebene [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Ruft die common Language Runtime (CLR) `ProvideAssembly` für jede Assembly, die nicht in der Liste angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBindInfo`  
 [in] Ein Zeiger auf ein [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) -Instanz, die vom Host verwendet, um bestimmte Bindungsmerkmale, einschließlich das Vorhandensein oder fehlen, versionsverwaltung, Richtlinien zu ermitteln und die Assembly zum Binden an.  
  
 `pAssemblyId`  
 [out] Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für diese `IStream`.  
  
 `pHostContext`  
 [out] Ein Zeiger auf hostspezifische Daten an, die verwendet wird, um zu bestimmen, die Beweise für die angeforderte Assembly ohne die Notwendigkeit einer Plattform Plattformaufrufs. `pHostContext` entspricht der <xref:System.Reflection.Assembly.HostContext%2A> Eigenschaft der verwalteten <xref:System.Reflection.Assembly> Klasse.  
  
 `ppStmAssemblyImage`  
 [out] Ein Zeiger auf die Adresse einer `IStream` , enthält das PE (portable Executable)-Image geladen werden, oder null, wenn die Assembly nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 [out] Ein Zeiger auf die Adresse einer `IStream` , enthält die Programm-Debuginformationen (PDB) oder Null, wenn die PDB-Datei nicht gefunden werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0x80070002)|Die angeforderte Assembly konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|Durch die angegebene Puffergröße `pAssemblyId` ist nicht groß genug für den Bezeichner, der der Host zurückgeben möchte.|  
  
## <a name="remarks"></a>Hinweise  
 Der Identitätswert zurückgegeben wird, für die `pAssemblyId` vom Host angegeben ist. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den Stream. Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die von anderen Aufrufen von `ProvideAssembly`. Wenn der Host die gleiche zurückgibt `pAssemblyId` Wert für eine andere `IStream`, die CLR wird überprüft, ob der Inhalt des Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die Runtime die vorhandene Kopie des Bildes statt ein neues zuzuordnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
