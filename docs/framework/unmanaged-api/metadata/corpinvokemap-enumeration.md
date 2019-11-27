---
title: CorPinvokeMap-Enumeration
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 17b7af7016cf88fd3ae263dd952502d515b0c833
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441557"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap-Enumeration
Gibt Optionen für einen PInvoke-Befehl an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`pmNoMangle`|Verwenden Sie die einzelnen Elementnamen wie angegeben.|  
|`pmCharSetMask`|Reserviert.|  
|`pmCharSetNotSpec`|Reserviert.|  
|`pmCharSetAnsi`|Marshallt Zeichen folgen als multibyte-Zeichen folgen.|  
|`pmCharSetUnicode`|Marshallt Zeichen folgen als Unicode-2-Byte-Zeichen.|  
|`pmCharSetAuto`|Automatisches Marshalling von Zeichen folgen für das Ziel Betriebssystem. Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und der Windows Server 2003-Familie. der Standardwert ist ANSI unter Windows 98 und Windows Me.|  
|`pmBestFitUseAssem`|Reserviert.|  
|`pmBestFitEnabled`|Führt eine Zuordnung mit einer optimalen Anpassung von Unicode-Zeichen durch, bei denen keine genaue Entsprechung im ANSI-Zeichensatz vorliegt.|  
|`pmBestFitDisabled`|Führen Sie keine Zuordnung mit einer optimalen Anpassung von Unicode-Zeichen durch. In diesem Fall werden alle nicht mappbaren Zeichen durch ein "?" ersetzt.|  
|`pmBestFitMask`|Reserviert.|  
|`pmThrowOnUnmappableCharUseAssem`|Reserviert.|  
|`pmThrowOnUnmappableCharEnabled`|Löst eine Ausnahme aus, wenn der Interop-Mars Haller auf ein nicht mappbares Zeichen stößt.|  
|`pmThrowOnUnmappableCharDisabled`|Lösen Sie keine Ausnahme aus, wenn der Interop-Mars Haller auf ein nicht mappbares Zeichen stößt.|  
|`pmThrowOnUnmappableCharMask`|Reserviert|  
|`pmSupportsLastError`|Ermöglicht dem aufgerufenen das Abrufen der Win32-`SetLastError`-Funktion vor der Rückgabe von der attributierten Methode.|  
|`pmCallConvMask`|Reserviert|  
|`pmCallConvWinapi`|Verwenden Sie die standardmäßige Platt Form Aufruf Konvention. Beispielsweise ist unter Windows der Standardwert `StdCall` und bei Windows CE .net `Cdecl`.|  
|`pmCallConvCdecl`|Verwenden Sie die `Cdecl`-Aufruf Konvention. In diesem Fall bereinigt der Aufrufer den Stapel. Dies ermöglicht das Aufrufen von Funktionen mit `varargs` (d. h. Funktionen, die eine Variable Anzahl von Parametern akzeptieren).|  
|`pmCallConvStdcall`|Verwenden Sie die `StdCall`-Aufruf Konvention. In diesem Fall bereinigt der aufgerufene den Stapel. Dies ist die Standard Konvention zum Aufrufen nicht verwalteter Funktionen mit Platt Form Aufruf.|  
|`pmCallConvThiscall`|Verwenden Sie die `ThisCall`-Aufruf Konvention. In diesem Fall ist der erste Parameter der `this` Zeiger und wird in Register ECX gespeichert. Andere Parameter werden auf dem Stapel abgelegt. Die `ThisCall`-Aufruf Konvention wird zum Aufrufen von Methoden für Klassen verwendet, die aus einer nicht verwalteten DLL exportiert wurden.|  
|`pmCallConvFastcall`|Reserviert.|  
|`pmMaxValue`|Reserviert.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
