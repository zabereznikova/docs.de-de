---
title: _CorExeMain2-Funktion
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f968d84ae695eb1da127538ebdc5e4f55d6ebf39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183156"
---
# <a name="corexemain2-function"></a>_CorExeMain2-Funktion
Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus. Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pUnmappedPE`  
 [in] Ein Zeiger auf den Speicher abgebildeten Code.  
  
 `cUnmappedPE`  
 [in] Die Anzahl der Elemente `pUnmappedPE` enthalten kann.  
  
 `pImageNameIn`  
 [in] Ein Zeiger auf den Namen des ausführbaren Images.  
  
 `pLoadersFileName`  
 [in] Der Name der Ladeprogrammdatei.  
  
 `pCmdLine`  
 [in] Befehlszeilenparameter, sofern vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
