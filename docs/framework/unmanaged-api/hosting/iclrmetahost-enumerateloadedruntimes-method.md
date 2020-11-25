---
title: ICLRMetaHost::EnumerateLoadedRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 98184dd6ea16df066905039b028acd689ff3f290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730434"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>ICLRMetaHost::EnumerateLoadedRuntimes-Methode

Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede Version der Common Language Runtime (CLR) enthält, die in einem bestimmten Prozess geladen wird. Diese Methode ersetzt die [GetVersionFromProcess](getversionfromprocess-function.md) -Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `hndProcess`  
 in Das Handle des Prozesses, der auf geladene Runtimes überprüft werden soll.  
  
 `ppEnumerator`  
 vorgenommen Eine <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Enumeration von [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstellen, die jeder vom Prozess geladenen CLR entsprechen.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`ppEnumerator` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode listet alle geladenen Runtimes auf, auch wenn Sie mit veralteten Funktionen wie [CorBindToRuntime](corbindtoruntime-function.md)geladen wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)
- [Hosting](index.md)
