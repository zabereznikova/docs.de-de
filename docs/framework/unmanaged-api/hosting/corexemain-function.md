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
ms.openlocfilehash: 8541e7761e2f8e1839d028fdaea3eb71307ba615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131198"
---
# <a name="_corexemain-function"></a>_CorExeMain-Funktion
Initialisiert den Common Language Runtime (CLR), den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und beginnt die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Lade Programm in Prozessen aufgerufen, die aus verwalteten ausführbaren Assemblys erstellt wurden. Bei dll-Assemblys Ruft das Lade Modul stattdessen die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) -Funktion auf.  
  
 Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der Bilddatei angegeben ist.  
  
 In Windows 98, Windows Me, Windows NT und Windows 2000 wird die `_CorExeMain`-Funktion indirekt über einen Fixup im Betriebssystem-Lade Modul aufgerufen. In allen anderen Versionen von Windows wird Sie direkt vom Betriebssystem-Lade Modul aufgerufen.  
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" des Themas [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
