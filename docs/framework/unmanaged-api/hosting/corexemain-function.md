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
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616590"
---
# <a name="_corexemain-function"></a>_CorExeMain-Funktion
Initialisiert den Common Language Runtime (CLR), den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und beginnt die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Lade Programm in Prozessen aufgerufen, die aus verwalteten ausführbaren Assemblys erstellt wurden. Bei dll-Assemblys Ruft das Lade Modul stattdessen die [_CorDllMain](cordllmain-function.md) -Funktion auf.  
  
 Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der Bilddatei angegeben ist.  
  
 In Windows 98, Windows Me, Windows NT und Windows 2000 `_CorExeMain` wird die Funktion indirekt über einen Fixup im Betriebssystem-Lade Modul aufgerufen. In allen anderen Versionen von Windows wird Sie direkt vom Betriebssystem-Lade Modul aufgerufen.  
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" im [_CorValidateImage](corvalidateimage-function.md) Thema.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
