---
title: GetRequestedRuntimeVersionForCLSID-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: ce0c6307defd93dcf63ac4e9051fc798041475f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127055"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID-Funktion
Ruft die entsprechenden Common Language Runtime (CLR)-Versionsinformationen für die-Klasse mit dem angegebenen `CLSID`ab.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `rclsid`  
 in  Der `CLSID` der Komponente.  
  
 `pVersion`  
 vorgenommen  Ein Puffer, der nach erfolgreichem Abschluss die Zeichenfolge der Versionsnummer enthält.  
  
 `cchBuffer`  
 in  Die Größe des `pVersion` Puffers in breit Zeichen.  
  
 `dwLength`  
 vorgenommen Die Länge des zurückgegebenen Puffers in Bytes.  
  
 `dwResolutionFlags`  
 in  Einer der CLSID_RESOLUTION_FLAGS-Werte. Die folgenden Werte werden unterstützt:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) gibt an, dass das standardmäßige Interop-Verhalten verwendet werden soll.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) gibt an, dass die Registrierung durchsucht werden soll und dass die Shim-Richtlinie angewendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Funktion wurde erfolgreich zurückgegeben.|  
|E_INVALIDARG|Einer der Parameter weist einen ungültigen Typ oder ein ungültiges Format auf.|  
|ERROR_INSUFFICIENT_BUFFER|Der `pVersion` Puffer ist nicht groß genug, um die gesamte Versions Zeichenfolge zu speichern.|  
|REGDB_E_CLASSNOTREG|Es ist keine Klasse mit dem angegebenen `CLSID`registriert.|  
|E_POINTER|`dwLength` ist NULL, oder `cchBuffer` ist groß genug, um die Versions Zeichenfolge zu speichern, `pVersion` ist jedoch NULL.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
