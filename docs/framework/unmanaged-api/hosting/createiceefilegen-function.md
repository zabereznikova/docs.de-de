---
title: CreateICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136826"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen-Funktion
Erstellt ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) -Objekt.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ceeFileGen`  
 vorgenommen Ein Zeiger auf die Adresse eines neuen `ICeeFileGen` Objekts.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt com-Standard Fehlercodes zurück.  
  
## <a name="remarks"></a>Hinweise  
 Das `ICeeFileGen`-Objekt wird verwendet, um Common Language Runtime (CLR) portable ausführbare Dateien (PE) zu erstellen.  
  
 Nennen Sie die [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) -Funktion, um das `ICeeFileGen` Objekt zu zerstören, wenn Sie fertig sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ICeeFileGen. h  
  
 **Bibliothek:** Mscorpe. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
