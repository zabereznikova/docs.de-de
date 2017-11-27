---
title: _CorExeMain-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: _CorExeMain
helpviewer_keywords: _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c341d578a45d72804d9ac33e2aefe513fd33922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corexemain-function"></a>_CorExeMain-Funktion
Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird durch das aus verwalteten ausführbaren Assemblys erstellte Prozesse-Ladeprogramm aufgerufen. DLL-Assemblys erfordert das Ladeprogramm die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) stattdessen-Funktion.  
  
 Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von den Einstiegspunkt in der Bilddatei enthaltenen angegeben.  
  
 In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorExeMain` Funktion indirekt durch einen Fixup im Ladeprogramm Betriebssystems aufgerufen. In allen anderen Versionen von Windows wird er direkt vom Ladeprogramm Betriebssystems aufgerufen.  
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
