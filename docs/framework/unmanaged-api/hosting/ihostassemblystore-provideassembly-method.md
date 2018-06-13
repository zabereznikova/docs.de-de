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
ms.openlocfilehash: e32d48931177a42dd14092b4052370764a217abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440362"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly-Methode
Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) von zurückgegebenen [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Ruft die common Language Runtime (CLR) `ProvideAssembly` für jede Assembly, die nicht in der Liste angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBindInfo`  
 [in] Ein Zeiger auf ein [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) -Instanz, die vom Host verwendet werden, um bestimmte Bindungsmerkmale, z. B. das Vorhandensein oder fehlen alle Versionskontrollrichtlinien zu bestimmen und die Assembly zum Binden an.  
  
 `pAssemblyId`  
 [out] Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für diese `IStream`.  
  
 `pHostContext`  
 [out] Ein Zeiger auf hostspezifische Daten, die verwendet wird, um zu bestimmen, den Beweis der angeforderten Assembly ohne die Notwendigkeit einer Plattform aufrufen. `pHostContext` entspricht der <xref:System.Reflection.Assembly.HostContext%2A> Eigenschaft der verwalteten <xref:System.Reflection.Assembly> Klasse.  
  
 `ppStmAssemblyImage`  
 [out] Ein Zeiger auf die Adresse des ein `IStream` , enthält der PE (portable Executable)-Image geladen werden, oder null, wenn die Assembly nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 [out] Ein Zeiger auf die Adresse des ein `IStream` , das Programmdebuginformationen (PDB) oder Null enthält, wenn die PDB-Datei nicht gefunden werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0 X 80070002)|Die angeforderte Assembly konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|Durch die angegebene Puffergröße `pAssemblyId` ist nicht groß genug für den Bezeichner, die möchte, dass der Host zurückzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 Der Identitätswert zurückgegeben wird, für die `pAssemblyId` wird vom Host angegeben. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den Stream. Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die von anderen Aufrufen von `ProvideAssembly`. Wenn der Host die gleiche zurückgibt `pAssemblyId` Wert für eine andere `IStream`, die CLR überprüft, ob der Inhalt dieses Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die Common Language Runtime die vorhandene Kopie des Abbilds statt ein neues Konto zuordnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
