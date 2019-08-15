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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7da0986269189ba5c2dfa0f10d509bf51deb446d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040209"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo-Funktion
Gibt Informationen über die angegebene Typbibliothek zurück, indem die [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) -Struktur überprüft wird.  
  
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
 vorgenommen Ein [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert. Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 vorgenommen Die Hauptversionsnummer der Typbibliothek. Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.  
  
 `pTypeLibMinorVer`  
 vorgenommen Die neben Versionsnummer der Typbibliothek. Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetTypeLibInfo` -Funktion wird von [Tlbexp. exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)aufgerufen. Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.  
  
 Wenn ein beliebiger Parameter NULL ist, gibt die `HRESULT` Funktion `E_POINTER`einen von zurück. Andernfalls wird `S_OK`zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Fern** TlbRef.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
