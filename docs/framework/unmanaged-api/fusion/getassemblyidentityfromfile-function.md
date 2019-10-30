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
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134524"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile-Funktion
Ruft einen Zeiger auf ein `IUnknown`-Objekt mit dem angegebenen `IID` in der Assembly am angegebenen Dateipfad ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzFilePath`  
 in Ein gültiger Pfad zur angeforderten Assembly.  
  
 `riid`  
 in Der `IID` der zurück zugebende Schnittstelle.  
  
 `ppIdentity`  
 vorgenommen Der zurückgegebene Schnittstellen Zeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IUnknown](/cpp/atl/iunknown)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
