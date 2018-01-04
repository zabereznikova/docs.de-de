---
title: CorPinvokeMap-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPinvokeMap
helpviewer_keywords: CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e0771ce54e7e2973525bfcf4aba4c1f7ddf0a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap-Enumeration
Gibt Optionen für PInvoke-Aufrufs.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pmNoMangle`|Verwenden Sie alle Elementnamen, wie angegeben.|  
|`pmCharSetMask`|Reserviert.|  
|`pmCharSetNotSpec`|Reserviert.|  
|`pmCharSetAnsi`|Marshallen von Zeichenfolgen als Zeichenfolgen mit mehreren Byte-Zeichen.|  
|`pmCharSetUnicode`|Marshallen von Zeichenfolgen als Unicode-2-Byte-Zeichen.|  
|`pmCharSetAuto`|Zeichenfolgen für DSA zielbetriebsystem entsprechend automatisch zu marshallen. Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und Windows Server 2003-Produktfamilie. Die Standardeinstellung ist, d. h. ANSI unter Windows 98 und Windows Me.|  
|`pmBestFitUseAssem`|Reserviert.|  
|`pmBestFitEnabled`|Führen Sie die Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen, die eine genaue Übereinstimmung in der ANSI-Zeichensatz hat.|  
|`pmBestFitDisabled`|Führen Sie keine Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen. In diesem Fall werden alle zuzuordnenden Zeichen durch ersetzt ein "?".|  
|`pmBestFitMask`|Reserviert.|  
|`pmThrowOnUnmappableCharUseAssem`|Reserviert.|  
|`pmThrowOnUnmappableCharEnabled`|Eine Ausnahme stößt der Interop-Marshaller ein Zeichen nicht zugeordnet werden kann.|  
|`pmThrowOnUnmappableCharDisabled`|Stößt der Interop-Marshaller ein zuzuordnendes Zeichen keine Ausnahme ausgelöst.|  
|`pmThrowOnUnmappableCharMask`|Reserviert|  
|`pmSupportsLastError`|Ermöglicht es dem aufgerufenen zum Aufrufen von Win32 `SetLastError` Funktion vor der Rückgabe von die attributierte Methode.|  
|`pmCallConvMask`|Reserviert|  
|`pmCallConvWinapi`|Verwenden Sie die Standardplattform Aufrufkonvention. Unter Windows ist die Standardeinstellung `StdCall` und auf Windows CE .NET ist `Cdecl`.|  
|`pmCallConvCdecl`|Verwenden der `Cdecl` Aufrufkonvention. In diesem Fall löscht der Aufrufer den Stapel. Aufrufende von Funktionen mit dadurch `varargs` (d. h. Funktionen, die eine Variable Anzahl von Parametern akzeptieren).|  
|`pmCallConvStdcall`|Verwenden der `StdCall` Aufrufkonvention. In diesem Fall entleert der aufgerufene den Stapel. Dies ist die Standardkonvention für das Aufrufen von nicht verwalteten Funktionen mit Plattformaufruf.|  
|`pmCallConvThiscall`|Verwenden der `ThisCall` Aufrufkonvention. Der erste Parameter in diesem Fall ist die `this` Zeiger und in ECX-Register gespeichert ist. Andere Parameter werden auf dem Stapel abgelegt. Die `ThisCall` -Aufrufkonvention wird zum Aufrufen von Methoden für Klassen, die aus einer nicht verwalteten DLL exportiert.|  
|`pmCallConvFastcall`|Reserviert.|  
|`pmMaxValue`|Reserviert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
