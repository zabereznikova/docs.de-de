---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
ms.openlocfilehash: 6b67ba9d022d94f51d7cc6a4645855f6b6ac3e19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679316"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a>ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile-Methode

Ruft eine [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) -Instanz ab, die eine Liste der Assemblys enthält, auf die die Assembly am angegebenen Dateipfad verweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pwzFilePath`  
 in Der Pfad zu der Assembly, die ausgewertet werden soll.  
  
 `dwFlags`  
 in Wird für zukünftige Erweiterbarkeit bereitgestellt. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, der von der aktuellen Version des Common Language Runtime (CLR) unterstützt wird.  
  
 `pExcludeAssembliesList`  
 in Ein Zeiger auf ein [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) -Objekt, das Assemblys darstellt, die von ausgeschlossen werden sollen `ppReferenceEnum` .  
  
 `ppReferenceEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICLRReferenceAssemblyEnum` Objekts, das Assemblyidentitätsdaten für die Assemblys enthält, auf die die Assembly bei verweist `pwzFilePath` , ausgenommen der durch dargestellten Assemblys `pExcludeAssembliesList` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Der Aufrufer kann eine Reihe bekannter Assemblyverweise aus der zurückgegebenen Liste ausschließen. Diese Gruppe wird durch den- `pExcludeAssembliesList` Parameter definiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum-Schnittstelle](iclrreferenceassemblyenum-interface.md)
