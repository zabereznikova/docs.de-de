---
title: LoadLibraryShim-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fe1ba15f8a9f8ee79582158209049c1e502a61d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418654"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim-Funktion
Lädt die angegebene Version einer DLL, die in .NET Framework redistributable-Paket enthalten ist.  
  
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
 [in] Eine 0 (null) endende Zeichenfolge mit dem Namen der DLL aus dem .NET Framework-Klassenbibliothek geladen werden.  
  
 `szVersion`  
 [in] Eine 0 (null) endende Zeichenfolge, die die Version der DLL zu ladende darstellt. Wenn `szVersion` null ist, ist die Version, die für das Laden, die neueste Version der angegebenen DLL ist, die kleiner als die Version 4 ist ausgewählt. D. h. alle Versionen gleich oder größer als 4-Version werden ignoriert, wenn `szVersion` null ist, und wenn keine Version kleiner als 4-Version installiert ist, kann die DLL zu laden. Dies ist, um sicherzustellen, dass die Installation von der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] wirkt sich nicht bereits vorhandene Anwendungen oder Komponenten. Finden Sie im Eintrag [In-Proc SxS und Migration Schnellstart](https://go.microsoft.com/fwlink/?LinkId=200329) im CLR-Teamblog.  
  
 `pvReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `phModDll`  
 [out] Ein Zeiger auf das Handle des Moduls.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|CLR_E_SHIM_RUNTIMELOAD|Laden von `szDllName` ist das Laden, die die common Language Runtime (CLR), und die erforderliche Version der CLR kann nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird zum Laden von DLLs, die in .NET Framework redistributable-Paket enthalten sind. Es wird nicht vom Benutzer generierte DLLs geladen werden.  
  
> [!NOTE]
>  Ab .NET Framework, Version 2.0, bewirkt, dass Fusion.dll Laden der CLR geladen werden. Dies ist, da die Funktionen in Fusion.dll jetzt Wrapper sind, deren Implementierungen von der Runtime bereitgestellt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
