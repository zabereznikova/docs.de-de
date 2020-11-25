---
title: GetTypeLibInfo-Funktion
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: e9f6ae9a0fcd6651395c54c2e44973e53668c1ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708321"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo-Funktion

Gibt Informationen über die angegebene Typbibliothek zurück, indem die [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) -Struktur überprüft wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szFile`  
 in Der Dateiname der Typbibliothek.  
  
 `pTypeLibID`  
 vorgenommen Die GUID der Typbibliothek.  
  
 `pTypeLibLCID`  
 vorgenommen Die Lokalisierungs-ID der Typbibliothek.  
  
 `pTypeLibPlatform`  
 vorgenommen Ein [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert. Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 vorgenommen Die Hauptversionsnummer der Typbibliothek. Bei Version *x. y* lautet die Hauptversionsnummer z. b. *x*.  
  
 `pTypeLibMinorVer`  
 vorgenommen Die neben Versionsnummer der Typbibliothek. Beispielsweise ist für Version *x. y* die neben Versionsnummer *y*.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetTypeLibInfo` Funktion wird vom [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen. Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.  
  
 Wenn ein beliebiger Parameter NULL ist, gibt die Funktion einen `HRESULT` von zurück `E_POINTER` . Andernfalls wird `S_OK`zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** TlbRef. h  
  
 **Bibliothek:** TlbRef. lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Tlbexp-Hilfsfunktionen](index.md)
- [LoadTypeLibEx-Funktion](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
