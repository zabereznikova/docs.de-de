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
ms.openlocfilehash: cc5324683daa9a02a6a89b2a3fb57ee9fd5dbe72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136963"
---
# <a name="_corexemain2-function"></a>_CorExeMain2-Funktion
Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus. Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein Zeiger auf den Speicher Abbild-Code.  
  
 `cUnmappedPE`  
 in Die Anzahl der Elemente, die `pUnmappedPE` enthalten kann.  
  
 `pImageNameIn`  
 in Ein Zeiger auf den Namen des ausführbaren Bilds.  
  
 `pLoadersFileName`  
 in Der Name der Lade Datei.  
  
 `pCmdLine`  
 in Befehlszeilenparameter (sofern vorhanden).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
