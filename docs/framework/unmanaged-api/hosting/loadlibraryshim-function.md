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
ms.openlocfilehash: d5e9ba0023b6516eb6190f32bc65b2b8b6af79f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727561"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim-Funktion

Lädt eine angegebene Version einer DLL, die im .NET Framework verteilbaren Paket enthalten ist.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert. Verwenden Sie stattdessen die [iclrruntimumfo:: LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szDllName`  
 in Eine mit NULL endende Zeichenfolge, die den Namen der DLL darstellt, die aus der .NET Framework Bibliothek geladen werden soll.  
  
 `szVersion`  
 in Eine mit NULL endende Zeichenfolge, die die Version der zu ladenden DLL darstellt. Wenn `szVersion` NULL ist, ist die für das Laden ausgewählte Version die neueste Version der angegebenen DLL, die kleiner als Version 4 ist. Das heißt, dass alle Versionen, die gleich oder größer als Version 4 sind, ignoriert werden `szVersion` , wenn NULL ist, und wenn keine Version, die kleiner als Version 4 ist, installiert ist, kann die dll nicht geladen werden. Dadurch wird sichergestellt, dass die Installation des .NET Framework 4 keine Auswirkungen auf bereits vorhandene Anwendungen oder Komponenten hat. Weitere Informationen finden Sie im Blogbeitrag [in-Proc SxS and Migration Schnellstart](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) im CLR-Teamblog.  
  
 `pvReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `phModDll`  
 vorgenommen Ein Zeiger auf das Handle des Moduls.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|CLR_E_SHIM_RUNTIMELOAD|Das Laden `szDllName` erfordert das Laden der Common Language Runtime (CLR), und die erforderliche Version der CLR kann nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Funktion wird zum Laden von DLLs verwendet, die in der .NET Framework verteilbaren Pakets enthalten sind. Benutzergenerierte DLLs werden nicht geladen.  
  
> [!NOTE]
> Beginnend mit der .NET Framework Version 2,0 bewirkt das Laden von Fusion.dll, dass die CLR geladen wird. Dies liegt daran, dass die Funktionen in Fusion.dll jetzt Wrapper sind, deren Implementierungen von der Laufzeit bereitgestellt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
