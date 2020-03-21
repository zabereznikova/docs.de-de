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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178117"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID-Funktion
Ruft die entsprechenden CLR-Versionsinformationen (Common Language Runtime) für die Klasse mit der angegebenen `CLSID`ab.  
  
 Diese Funktion ist in .NET Framework 4 veraltet.  
  
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
 [in]  Die `CLSID` der Komponente.  
  
 `pVersion`  
 [out]  Ein Puffer, der die Versionsnummernzeichenfolge nach erfolgreichem Abschluss enthält.  
  
 `cchBuffer`  
 [in]  Die Größe des `pVersion` Puffers in weiten Zeichen.  
  
 `dwLength`  
 [out] Die Länge (in Bytes) des zurückgegebenen Puffers.  
  
 `dwResolutionFlags`  
 [in]  Einer der CLSID_RESOLUTION_FLAGS Werte. Die folgenden Werte werden unterstützt:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) Gibt an, dass das standardmäßige Interopverhalten verwendet werden soll.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) Gibt an, dass die Registrierung durchsucht und die Shim-Richtlinie angewendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Funktion wurde erfolgreich zurückgegeben.|  
|E_INVALIDARG|Einer der Parameter hat einen ungültigen Typ oder ein ungültiges Format.|  
|ERROR_INSUFFICIENT_BUFFER|Der `pVersion` Puffer ist nicht groß genug, um die gesamte Versionszeichenfolge zu enthalten.|  
|REGDB_E_CLASSNOTREG|Es ist keine Klasse `CLSID`registriert, die für die angegebene klasse registriert ist.|  
|E_POINTER|`dwLength`ist null `cchBuffer` oder groß genug, um die `pVersion` Versionszeichenfolge zu halten, ist aber null.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
