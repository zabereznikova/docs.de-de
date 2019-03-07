---
title: _CorDllMain-Funktion
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3c529e77cad16f0bde12e34491829b58add17aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500379"
---
# <a name="cordllmain-function"></a>_CorDllMain-Funktion
Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hInst`  
 [in] Der Instanzhandle des geladenen Moduls.  
  
 `dwReason`  
 [in] Gibt an, warum die DLL-Einstiegspunkt-Funktion aufgerufen wird. Dieser Parameter kann einen der folgenden Werte sein: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH. Beschreibungen dieser Werte finden Sie die `DllMain` Dokumentation im Platform SDK.  
  
 `lpReserved`  
 [in] Nicht verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `true` für Erfolg und `false` Wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Ladeprogramm Betriebssystems für DLL-Assemblys aufgerufen werden. Für ausführbare Assemblys ruft das Ladeprogramm die [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) stattdessen funktionieren.  
  
 Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die DLL-Datei angegeben.  
  
Die `_CorDllMain` Funktion direkt vom Ladeprogramm Betriebssystems aufgerufen wird.
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
