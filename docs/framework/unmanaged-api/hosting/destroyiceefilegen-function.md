---
title: DestroyICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136500"
---
# <a name="destroyiceefilegen-function"></a>DestroyICeeFileGen-Funktion
Zerstört ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) -Objekt.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ceeFileGen`  
 in Das `ICeeFileGen` Objekt, das zerstört werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt com-Standard Fehlercodes zurück.  
  
## <a name="remarks"></a>Hinweise  
 `DestroyICeeFileGen` zerstört das `ICeeFileGen` Objekt [, das von der Funktion "](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) -Funktion" erstellt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ICeeFileGen. h  
  
 **Bibliothek:** Mscorpe. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
