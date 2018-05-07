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
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo-Funktion
Gibt Informationen zu der angegebenen Typbibliothek durch Untersuchen der [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szFile`  
 [in] Der Dateiname der Typbibliothek.  
  
 `pTypeLibID`  
 [out] Die GUID der Typbibliothek.  
  
 `pTypeLibLCID`  
 [out] Die Lokalisierungs-ID der Typbibliothek.  
  
 `pTypeLibPlatform`  
 [out] Ein [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) Flag, das das Zielbetriebssystem für die Typbibliothek identifiziert. Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Die Hauptversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.  
  
 `pTypeLibMinorVer`  
 [out] Die Nebenversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetTypeLibInfo` Funktion wird aufgerufen, indem Sie die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Dieses Tool generiert eine Typbibliothek, die die Typen in einer Assembly der common Language Runtime (CLR) beschreibt.  
  
 Wenn ein der Parameter null ist, gibt die Funktion ein `HRESULT` von `E_POINTER`. Andernfalls wird zurückgegeben `S_OK`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx-Funktion](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
