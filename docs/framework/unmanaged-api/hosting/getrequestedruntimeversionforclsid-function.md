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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8d3a7168ce0ee3484384ae0e2d10ca00367fc9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID-Funktion
Ruft die entsprechende Version zur common Language Runtime (CLR) für die Klasse mit dem angegebenen `CLSID`.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `rclsid`  
 [in]  Die `CLSID` der Komponente.  
  
 `pVersion`  
 [out]  Ein Puffer, der nach dem erfolgreichen Abschluss die Versionsnummernzeichenfolge enthält.  
  
 `cchBuffer`  
 [in]  Die Größe in Breitzeichen, der die `pVersion` Puffer.  
  
 `dwLength`  
 [out] Die Länge des zurückgegebenen Puffers in Bytes.  
  
 `dwResolutionFlags`  
 [in]  Einer der CLSID_RESOLUTION_FLAGS-Werte. Die folgenden Werte werden unterstützt:  
  
-   CLSID_RESOLUTION_DEFAULT: (0 x 0) gibt an, die das Interop-Standardverhalten sollten werden verwendet.  
  
-   CLSID_RESOLUTION_REGISTERED: (0 x 1) gibt an, dass die Registrierung durchsucht werden soll, und shim-Richtlinie sollte angewendet.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Funktion wurde erfolgreich zurückgegeben.|  
|E_INVALIDARG|Einer der Parameter weist einen ungültigen Typ oder Format.|  
|ERROR_INSUFFICIENT_BUFFER|Die `pVersion` Puffer ist nicht groß genug für die gesamte Versionszeichenfolge.|  
|REGDB_E_CLASSNOTREG|Es gibt keine Klasse, die mit dem angegebenen registriert `CLSID`.|  
|E_POINTER|`dwLength` ist null, oder `cchBuffer` ist groß genug für die Versionszeichenfolge jedoch `pVersion` ist null.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
