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
ms.openlocfilehash: 4f5dd25ec2a6a1b0b5d6266c3d8e728bd128a9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697757"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile-Funktion
Ruft einen Zeiger auf ein `IUnknown` Objekt mit dem angegebenen `IID` in der Assembly im angegebenen Dateipfad.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzFilePath`  
 [in] Ein gültiger Pfad auf die angeforderte Assembly.  
  
 `riid`  
 [in] Die `IID` der zurückzugebenden Schnittstelle.  
  
 `ppIdentity`  
 [out] Der zurückgegebene Schnittstellenzeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IUnknown](/cpp/atl/iunknown)
- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
