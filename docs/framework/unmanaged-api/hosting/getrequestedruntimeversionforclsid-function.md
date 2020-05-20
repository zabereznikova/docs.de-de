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
ms.openlocfilehash: 899d6e74902e47f1f41b849bd5c25048baa175f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617138"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID-Funktion
Ruft die entsprechenden Common Language Runtime (CLR)-Versionsinformationen für die-Klasse mit dem angegebenen ab `CLSID` .  
  
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
 in  Der der `CLSID` Komponente.  
  
 `pVersion`  
 vorgenommen  Ein Puffer, der nach erfolgreichem Abschluss die Zeichenfolge der Versionsnummer enthält.  
  
 `cchBuffer`  
 in  Die Größe des Puffers in breit Zeichen `pVersion` .  
  
 `dwLength`  
 vorgenommen Die Länge des zurückgegebenen Puffers in Bytes.  
  
 `dwResolutionFlags`  
 in  Einer der CLSID_RESOLUTION_FLAGS-Werte. Die folgenden Werte werden unterstützt:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) gibt an, dass das standardmäßige Interop-Verhalten verwendet werden soll.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) gibt an, dass die Registrierung durchsucht werden soll und dass die Shim-Richtlinie angewendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Funktion wurde erfolgreich zurückgegeben.|  
|E_INVALIDARG|Einer der Parameter weist einen ungültigen Typ oder ein ungültiges Format auf.|  
|ERROR_INSUFFICIENT_BUFFER|Der `pVersion` Puffer ist nicht groß genug, um die gesamte Versions Zeichenfolge zu speichern.|  
|REGDB_E_CLASSNOTREG|Es ist keine Klasse mit dem angegebenen registriert `CLSID` .|  
|E_POINTER|`dwLength`ist NULL, oder `cchBuffer` ist groß genug, um die Versions Zeichenfolge aufzunehmen, aber `pVersion` ist NULL.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
