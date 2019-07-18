---
title: _CorExeMain-Funktion
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e90e3953a01f07d77e604628fbdb79eb9efa0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779178"
---
# <a name="corexemain-function"></a>_CorExeMain-Funktion
Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Ladeprogramm in Prozesse, die von verwalteten ausführbare Assemblys erstellt aufgerufen. Für DLL-Assemblys, die das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) stattdessen funktionieren.  
  
 Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die Image-Datei angegeben.  
  
 In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorExeMain` Funktion wird durch einen Fixup im Betriebssystem-Lader indirekt aufgerufen. In allen anderen Versionen von Windows spricht man direkt vom Ladeprogramm Betriebssystems.  
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
