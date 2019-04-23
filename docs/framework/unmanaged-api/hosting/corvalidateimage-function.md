---
title: _CorValidateImage-Funktion
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df9cc0cc86237b1ec439a4ec4fa6a75429c416d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111175"
---
# <a name="corvalidateimage-function"></a>_CorValidateImage-Funktion
Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ImageBase`  
 [in] Ein Zeiger auf den Anfangsort des Bildes, das als Überprüfen von verwaltetem Code. Das Image muss bereits in den Arbeitsspeicher geladen werden.  
  
 `FileName`  
 [in] Der Dateiname des Bilds.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt die Standardwerte zurück `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, und `E_FAIL`, sowie die folgenden Werte.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Das Image ist ungültig. Dieser Wert muss es sich um das HRESULT 0xC000007BL auf.|  
|`STATUS_SUCCESS`|Das Image ist ungültig. Dieser Wert muss es sich um das HRESULT 0x00000000L auf.|  
  
## <a name="remarks"></a>Hinweise  
 In Windows XP und höheren Versionen überprüft vom Ladeprogramm des Betriebssystems nach verwalteten Modulen durch untersuchen das Verzeichnis der COM-Deskriptor-Bit in den Header zu common Object File-Format (COFF). Ein festgelegtes Bit gibt an, ein verwaltetes Modul. Wenn das Ladeprogramm ein verwaltetes Modul erkannt wird, lädt es "Mscoree.dll" und ruft `_CorValidateImage`, die die folgenden Aktionen ausführt:  
  
-   Bestätigt, dass das Bild, ein gültiges verwaltetes Modul ist.  
  
-   Ändert den Einstiegspunkt in das Abbild an einen Einstiegspunkt in die common Language Runtime (CLR).  
  
-   Für 64-Bit-Versionen von Windows ändert das Image im Arbeitsspeicher vom Format PE32 in das Format PE32 + transformieren.  
  
-   Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls geladen werden.  
  
 Für ausführbare Images vom Ladeprogramm des Betriebssystems dann ruft der [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion, unabhängig von der Einstiegspunkt in die ausführbare Datei angegeben. DLL-Assembly-Images, das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) Funktion.  
  
 `_CorExeMain` oder `_CorDllMain` führt folgende Aktionen aus:  
  
-   Initialisiert die CLR.  
  
-   Sucht den verwalteten Einstiegspunkt von CLR-Header der Assembly an.  
  
-   Beginnt die Ausführung.  
  
 Die Aufrufe der Loader die [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funktionieren, wenn verwaltete Modulimages entladen. Diese Funktion führt jedoch keine Maßnahmen; Es gibt nur zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
