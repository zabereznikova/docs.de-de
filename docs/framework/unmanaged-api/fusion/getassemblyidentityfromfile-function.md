---
title: GetAssemblyIdentityFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ea151417a1cb53104ec29fff1e76e21f82ec9bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431642"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile-Funktion
Ruft einen Zeiger auf eine `IUnknown` Objekt mit dem angegebenen `IID` in der Assembly im angegebenen Dateipfad.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzFilePath`  
 [in] Ein gültiger Pfad zu der angeforderten Assembly.  
  
 `riid`  
 [in] Die `IID` der zurückzugebenden Schnittstelle.  
  
 `ppIdentity`  
 [out] Der zurückgegebene Schnittstellenzeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <<!--zzxref:IUnknown --> `IUnknown`>  
 [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
