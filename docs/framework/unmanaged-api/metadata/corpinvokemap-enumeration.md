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
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176148"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap-Enumeration
Gibt Optionen für einen PInvoke-Aufruf an.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pmNoMangle`|Verwenden Sie jeden Mitgliedsnamen wie angegeben.|  
|`pmCharSetMask`|Reserviert.|  
|`pmCharSetNotSpec`|Reserviert.|  
|`pmCharSetAnsi`|Marshallt Zeichenfolgen als Mehrfachbyte-Zeichenfolgen.|  
|`pmCharSetUnicode`|Marshallt Zeichenfolgen als 2-Byte-Unicode-Zeichen.|  
|`pmCharSetAuto`|Marshallt Zeichenfolgen automatisch entsprechend dem Zielbetriebssystem. Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und der Windows Server 2003-Produktreihe. Der Standardwert ist ANSI unter Windows 98 und Windows Me.|  
|`pmBestFitUseAssem`|Reserviert.|  
|`pmBestFitEnabled`|Führen Sie die optimale Zuordnung von Unicode-Zeichen durch, denen eine exakte Übereinstimmung im ANSI-Zeichensatz fehlt.|  
|`pmBestFitDisabled`|Führen Sie keine optimale Zuordnung von Unicode-Zeichen durch. In diesem Fall werden alle nicht bespielbaren Zeichen durch ein '?' ersetzt.|  
|`pmBestFitMask`|Reserviert.|  
|`pmThrowOnUnmappableCharUseAssem`|Reserviert.|  
|`pmThrowOnUnmappableCharEnabled`|Auslösen einer Ausnahme, wenn der Interop-Marshaller auf ein nicht zu treffendes Zeichen trifft.|  
|`pmThrowOnUnmappableCharDisabled`|Werfen Sie keine Ausnahme aus, wenn der Interop-Marshaller auf ein nicht bewertes Zeichen trifft.|  
|`pmThrowOnUnmappableCharMask`|Reserved|  
|`pmSupportsLastError`|Erlauben Sie dem Angerufenen, die `SetLastError` Win32-Funktion aufzurufen, bevor er von der attributierten Methode zurückkehrt.|  
|`pmCallConvMask`|Reserved|  
|`pmCallConvWinapi`|Verwenden Sie die Standardplattformaufrufkonvention. Unter Windows ist `StdCall` z. B. der Standardwert `Cdecl`und unter Windows CE .NET ist es .|  
|`pmCallConvCdecl`|Verwenden `Cdecl` Sie die Aufrufkonvention. In diesem Fall reinigt der Aufrufer den Stapel. Dadurch werden Aufruffunktionen mit `varargs` (d. h. Funktionen, die eine variable Anzahl von Parametern akzeptieren) aktiviert.|  
|`pmCallConvStdcall`|Verwenden `StdCall` Sie die Aufrufkonvention. In diesem Fall reinigt der Angerufene den Stapel. Dies ist die Standardkonvention für das Aufrufen nicht verwalteter Funktionen mit Plattformaufruf.|  
|`pmCallConvThiscall`|Verwenden `ThisCall` Sie die Aufrufkonvention. In diesem Fall ist der `this` erste Parameter der Zeiger und wird im Register ECX gespeichert. Weitere Parameter werden in den Stapel verschoben. Die `ThisCall` aufrufende Konvention wird verwendet, um Methoden für Klassen aufzurufen, die aus einer nicht verwalteten DLL exportiert werden.|  
|`pmCallConvFastcall`|Reserviert.|  
|`pmMaxValue`|Reserviert.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
