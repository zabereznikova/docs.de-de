---
title: _CorDllMain-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985f2284026054217671de767c316b1fba35c098
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
 `hInst`  
 [in] Der Instanzhandle des geladenen Moduls.  
  
 `dwReason`  
 [in] Gibt an, warum die DLL-Einstiegspunkt-Funktion aufgerufen wird. Dieser Parameter kann einen der folgenden Werte sein: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH oder DLL_PROCESS_DETACH. Eine Beschreibung dieser Werte finden Sie unter der `DllMain` Dokumentation im Plattform-SDK.  
  
 `lpReserved`  
 [in] Wird nicht verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `true` für Erfolg und `false` , wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird für DLL-Assemblys durch das Betriebssystemladeprogramm aufgerufen. Für ausführbare Assemblys ruft das Ladeprogramm die [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) stattdessen-Funktion.  
  
 Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von den Einstiegspunkt in die DLL-Datei angegeben.  
  
 In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorDllMain` Funktion wird aufgerufen, indirekt über eine Fixupin vom Ladeprogramm des Betriebssystems. In allen anderen Versionen von Windows wird er direkt vom Ladeprogramm Betriebssystems aufgerufen.  
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
