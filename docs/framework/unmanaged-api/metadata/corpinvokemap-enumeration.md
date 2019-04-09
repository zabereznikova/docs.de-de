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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079629"
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
|`pmCharSetAnsi`|Marshallt Zeichenfolgen als Zeichenfolgen mit mehreren Byte-Zeichen.|  
|`pmCharSetUnicode`|Marshallt Zeichenfolgen als 2-Byte-Unicode-Zeichen.|  
|`pmCharSetAuto`|Automatisch zu marshallen Zeichenfolgen entsprechend dem Zielbetriebssystem bereit. Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und Windows Server 2003-Familie; Der Standardwert ist ANSI unter Windows 98 und Windows Me enthalten.|  
|`pmBestFitUseAssem`|Reserviert.|  
|`pmBestFitEnabled`|Führen Sie die Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen, die eine genaue Übereinstimmung in die ANSI-Zeichensatz ausgewählt hat.|  
|`pmBestFitDisabled`|Führen Sie die Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen nicht zu. In diesem Fall alle nicht zuzuordnenden Zeichen ersetzt werden durch ein "?".|  
|`pmBestFitMask`|Reserviert.|  
|`pmThrowOnUnmappableCharUseAssem`|Reserviert.|  
|`pmThrowOnUnmappableCharEnabled`|Wenn es sich bei der Interop-Marshaller ein nicht zuzuordnendes Zeichen findet, wird eine Ausnahme ausgelöst.|  
|`pmThrowOnUnmappableCharDisabled`|Keine Ausnahme ausgelöst, wenn der interop-Marshaller ein nicht zuzuordnendes Zeichen erkannt wird.|  
|`pmThrowOnUnmappableCharMask`|Reserviert|  
|`pmSupportsLastError`|Ermöglicht es dem aufgerufenen die Win32-Aufrufen `SetLastError` vor dem Zurückgeben aus die attributierte Methode.|  
|`pmCallConvMask`|Reserviert|  
|`pmCallConvWinapi`|Verwenden Sie die Standardkonvention für Plattformaufrufe. Für Windows ist der Standardwert beispielsweise `StdCall` und auf Windows CE .NET ist `Cdecl`.|  
|`pmCallConvCdecl`|Verwenden der `Cdecl` Aufrufkonvention. Der Aufrufer entleert in diesem Fall den Stapel. Dies aktiviert Aufruffunktionen mit `varargs` (d. h. Funktionen, die eine Variable Anzahl von Parametern akzeptieren).|  
|`pmCallConvStdcall`|Verwenden der `StdCall` Aufrufkonvention. In diesem Fall entleert der aufgerufene den Stapel. Dies ist die Standardkonvention für das aufrufende nicht verwaltete Funktionen mit Plattformaufruf.|  
|`pmCallConvThiscall`|Verwenden der `ThisCall` Aufrufkonvention. Der erste Parameter in diesem Fall ist die `this` Zeiger und wird im Register ECX gespeichert. Andere Parameter sind auf dem Stapel abgelegt. Die `ThisCall` Aufrufkonvention wird zum Aufrufen von Methoden für Klassen, die aus einer nicht verwalteten DLL exportiert wurden.|  
|`pmCallConvFastcall`|Reserviert.|  
|`pmMaxValue`|Reserviert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
