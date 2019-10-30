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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136964"
---
# <a name="_cordllmain-function"></a>\_cordllmain-Funktion

Initialisiert die Common Language Runtime (CLR), gibt den verwalteten Einstiegspunkt im CLR-Header der dll-Assembly an und beginnt die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hInst`  
 in Der Instanzhandle des geladenen Moduls.  
  
 `dwReason`  
 in Gibt an, warum die DLL-Einstiegspunkt Funktion aufgerufen wird. Dieser Parameter kann einen der folgenden Werte aufweisen: dll\_PROCESS_ATTACH, dll\_Thread\_Attach, dll\_Thread\_Attach oder dll\_Prozess\_Detach. Beschreibungen dieser Werte finden Sie in der `DllMain`-Dokumentation im Platform SDK.  
  
 `lpReserved`  
 in Genutzt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `true` für Erfolg und `false` zurück, wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Betriebssystem-Lade Modul für dll-Assemblys aufgerufen. Bei ausführbaren Assemblys Ruft das Lade Programm stattdessen die [\_CORExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion auf.  
  
 Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der DLL-Datei angegeben ist.  
  
Die `_CorDllMain`-Funktion wird direkt vom Betriebssystem-Lade Modul aufgerufen.
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" des Themas [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Anforderungen  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
