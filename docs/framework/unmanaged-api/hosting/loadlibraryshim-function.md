---
title: LoadLibraryShim-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b8fe8413d0eff332e60508a083f03574e58d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim-Funktion
Lädt die angegebene Version einer DLL, die in das verteilbare .NET Framework-Paket enthalten ist.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet. Verwenden der [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szDllName`  
 [in] Eine NULL-terminierte Zeichenfolge mit dem Namen der DLL aus dem .NET Framework-Klassenbibliothek geladen werden.  
  
 `szVersion`  
 [in] Eine NULL-terminierte Zeichenfolge, die die Version der DLL zu ladende darstellt. Wenn `szVersion` null ist, ist die Version, die für die ausgewählte laden die neueste Version der angegebenen DLL, die kleiner als der Version 4 ist. D. h., alle Versionen gleich oder größer als der Version 4 werden ignoriert, wenn `szVersion` null ist, und wenn keine Version kleiner als 4-Version installiert ist, kann die DLL zu laden. Wird verwendet, um diese Installation sicher, dass die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] hat keine Auswirkungen auf bereits vorhandene Anwendungen oder Komponenten. Finden Sie im Eintrag [prozessinterne SxS und Migration Schnellstart](http://go.microsoft.com/fwlink/?LinkId=200329) im CLR-Teamblog.  
  
 `pvReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `phModDll`  
 [out] Ein Zeiger auf das Handle des Moduls.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|CLR_E_SHIM_RUNTIMELOAD|Laden von `szDllName` erfordert laden, die die common Language Runtime (CLR) und die erforderliche Version der CLR kann nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion dient zum Laden von DLLs, die in das verteilbare .NET Framework-Paket enthalten sind. Es wird nicht vom Benutzer generierte DLLs geladen.  
  
> [!NOTE]
>  Ab .NET Framework, Version 2.0, bewirkt das Laden von Fusion.dll die CLR geladen werden soll. Dies ist, da die Funktionen in Fusion.dll jetzt Wrapper sind, deren Implementierung von der Runtime bereitgestellt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
