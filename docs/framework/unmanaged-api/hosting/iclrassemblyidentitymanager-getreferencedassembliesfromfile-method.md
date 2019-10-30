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
ms.openlocfilehash: 65dc330e88cb2457cc34f9994313373ab1ab84aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126703"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a>ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile-Methode
Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz ab, die eine Liste der Assemblys enthält, auf die die Assembly am angegebenen Dateipfad verweist.  
  
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
 in Ein Zeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) -Objekt, das Assemblys darstellt, die von `ppReferenceEnum`ausgeschlossen werden sollen.  
  
 `ppReferenceEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICLRReferenceAssemblyEnum` Objekts, das Assemblyidentitätsdaten für die Assemblys enthält, auf die die Assembly bei `pwzFilePath`verweist, ausgenommen der durch `pExcludeAssembliesList`dargestellten Assemblys.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Der Aufrufer kann eine Reihe bekannter Assemblyverweise aus der zurückgegebenen Liste ausschließen. Diese Gruppe wird durch den `pExcludeAssembliesList`-Parameter definiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
