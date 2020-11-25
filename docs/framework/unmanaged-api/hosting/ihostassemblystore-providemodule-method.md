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
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732995"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule-Methode

Löst ein Modul in einer Assembly oder einer verknüpften (aber nicht eingebetteten) Ressourcen Datei auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pBindInfo`  
 in Ein Zeiger auf eine [ModuleBindInfo](modulebindinfo-structure.md) -Instanz, die die, die <xref:System.AppDomain> Assembly und den Modulnamen des angeforderten Moduls beschreibt.  
  
 `pdwModuleId`  
 vorgenommen Ein Zeiger auf einen eindeutigen Bezeichner für das, `IStream` das das geladene Modul enthält.  
  
 `ppStmModuleImage`  
 vorgenommen Ein Zeiger auf die Adresse eines `IStream` Objekts, das das PE-Bild (portable ausführbare Datei) enthält, das geladen werden soll, oder NULL, wenn das Modul nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 vorgenommen Ein Zeiger auf die Adresse eines `IStream` Objekts, das die Programm Debuginformationen (PDB) für das angeforderte Modul enthält, oder NULL, wenn die PDB-Datei nicht gefunden wurde.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`ProvideModule` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0x80070002)|Die angeforderte Assembly oder verknüpfte Ressource konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` ist nicht groß genug, um den Bezeichner zu enthalten, der vom Host zurückgegeben werden soll.|  
  
## <a name="remarks"></a>Hinweise  

 Der für zurückgegebene Identitäts Wert `pdwModuleId` wird vom Host angegeben. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutigen Bezeichner für den zugeordneten Stream. Er überprüft jeden Wert anhand der Werte, die `pAssemblyId` von Aufrufen von [ProvideAssembly](ihostassemblystore-provideassembly-method.md) zurückgegeben werden, und `pdwModuleId` mit den Werten, die von anderen Aufrufen von zurückgegeben werden `ProvideModule` . Wenn der Host denselben Bezeichnerwert für einen anderen zurückgibt `IStream` , überprüft die CLR, ob der Inhalt dieses Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Bilds, anstatt eine neue zu ordnen. Daher muss sich der Bezeichner auch nicht mit den von zurückgegebenen Assemblybezeichnern überschneiden `ProvideAssembly` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
