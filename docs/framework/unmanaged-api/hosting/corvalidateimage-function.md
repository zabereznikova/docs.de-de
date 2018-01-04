---
title: _CorValidateImage-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
 `ImageBase`  
 [in] Ein Zeiger auf die Startposition des Bilds als überprüfen zu verwaltetem Code. Das Bild muss bereits in den Arbeitsspeicher geladen werden.  
  
 `FileName`  
 [in] Der Dateiname des Bilds.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt die Standardwerte `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, und `E_FAIL`, sowie die folgenden Werte.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Das Bild ist ungültig. Dieser Wert hat den HRESULT 0xC000007BL auf.|  
|`STATUS_SUCCESS`|Das Bild ist ungültig. Dieser Wert hat den HRESULT 0x00000000L auf.|  
  
## <a name="remarks"></a>Hinweise  
 In Windows XP und höheren Versionen überprüft vom Ladeprogramm des Betriebssystems nach verwalteten Modulen durch untersuchen das Verzeichnis der COM-Deskriptor Bit im Header common Object-Datei-Format (COFF). Ein festgelegtes Bit gibt ein verwaltetes Modul an. Wenn das Ladeprogramm eine verwaltete Module erkennt, lädt es "Mscoree.dll" und Aufrufe `_CorValidateImage`, die folgenden Aktionen ausgeführt:  
  
-   Bestätigt, dass das Bild ein gültiges verwaltetes Modul ist.  
  
-   Ändert den Einstiegspunkt in das Image auf einen Einstiegspunkt in die common Language Runtime (CLR).  
  
-   Für 64-Bit-Versionen von Windows ändert das Image im Arbeitsspeicher vom Format PE32 in das Format PE32 + transformiert.  
  
-   Benachrichtigt das Ladeprogramm, wenn die Images der verwalteten Module geladen werden.  
  
 Für ausführbare Images vom Ladeprogramm des Betriebssystems dann ruft der [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) -Funktion, unabhängig von den Einstiegspunkt in die ausführbare Datei angegeben. Für DLL-Assembly-Images, das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) Funktion.  
  
 `_CorExeMain`oder `_CorDllMain` führt die folgenden Aktionen aus:  
  
-   Initialisiert die CLR.  
  
-   Sucht den verwalteten Einstiegspunkt aus der Assembly aneinander gehängt CLR-Header.  
  
-   Beginnt die Ausführung.  
  
 Ruft die Ladeprogramm der [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funktionieren bei verwalteten Images des Moduls entladen werden. Diese Funktion ist jedoch keine Aktion ausgeführt; Es gibt nur zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
