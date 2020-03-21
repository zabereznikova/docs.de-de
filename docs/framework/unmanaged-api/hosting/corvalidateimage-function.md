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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178214"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage-Funktion
Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ImageBase`  
 [in] Ein Zeiger auf den Startspeicherort des Bildes, der als verwalteter Code überprüft werden soll. Das Bild muss bereits in den Speicher geladen werden.  
  
 `FileName`  
 [in] Der Dateiname des Bildes.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt `E_INVALIDARG`die `E_OUTOFMEMORY` `E_UNEXPECTED`Standardwerte `E_FAIL`, , und sowie die folgenden Werte zurück.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Das Bild ist ungültig. Dieser Wert hat den HRESULT 0xC00007BL.|  
|`STATUS_SUCCESS`|Das Bild ist gültig. Dieser Wert hat den HRESULT 0x0000000L.|  
  
## <a name="remarks"></a>Bemerkungen  
 In Windows XP und neueren Versionen sucht der Betriebssystemlader nach verwalteten Modulen, indem er das COM Descriptor Directory-Bit im COFF-Header (Common Object File Format) untersucht. Ein festgelegtes Bit gibt ein verwaltetes Modul an. Wenn der Lader ein verwaltetes Modul erkennt, lädt er `_CorValidateImage`MsCorEE.dll und ruft auf, die die folgenden Aktionen ausführt:  
  
- Bestätigt, dass es sich bei dem Abbild um ein gültiges verwaltetes Modul handelt.  
  
- Ändert den Einstiegspunkt im Bild in einen Einstiegspunkt in der Common Language Runtime (CLR).  
  
- Ändert bei 64-Bit-Versionen von Windows das im Speicher enthaltene Bild, indem es vom PE32 in das PE32+-Format transformiert wird.  
  
- Kehrt zum Ladeprogramm zurück, wenn die Images des verwalteten Moduls geladen werden.  
  
 Bei ausführbaren Images ruft der Betriebssystemlader dann die [_CorExeMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) auf, unabhängig vom in der ausführbaren Datei angegebenen Einstiegspunkt. Bei DLL-Assemblybildern ruft der Lader die [_CorDllMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) auf.  
  
 `_CorExeMain`oder `_CorDllMain` führt die folgenden Aktionen aus:  
  
- Initialisiert die CLR.  
  
- Sucht den verwalteten Einstiegspunkt aus dem CLR-Header der Assembly.  
  
- Beginnt mit der Ausführung.  
  
 Der Loader ruft die [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) Funktion auf, wenn verwaltete Modulabbilder entladen werden. Diese Funktion führt jedoch keine Aktion aus. es kehrt einfach zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
