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
ms.openlocfilehash: 4f05eb2e6ef31cf1993a623c38bb177f7e3c297e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935653"
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
  
## <a name="parameters"></a>Parameters  
 `szFile`  
 in Der Dateiname der Typbibliothek.  
  
 `pTypeLibID`  
 vorgenommen Die GUID der Typbibliothek.  
  
 `pTypeLibLCID`  
 vorgenommen Die Lokalisierungs-ID der Typbibliothek.  
  
 `pTypeLibPlatform`  
 vorgenommen Ein [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das das Ziel Betriebssystem für die Typbibliothek identifiziert. Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 vorgenommen Die Hauptversionsnummer der Typbibliothek. Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.  
  
 `pTypeLibMinorVer`  
 vorgenommen Die neben Versionsnummer der Typbibliothek. Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetTypeLibInfo`-Funktion wird von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen. Dieses Tool generiert eine Typbibliothek, die die Typen in einer Common Language Runtime-Assembly (CLR) beschreibt.  
  
 Wenn ein beliebiger Parameter NULL ist, gibt die Funktion eine `HRESULT` `E_POINTER`zurück. Andernfalls wird `S_OK` zurückgegeben.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** TlbRef. h  
  
 **Bibliothek:** TlbRef. lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
