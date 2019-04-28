---
title: ICLRStrongName::StrongNameCompareAssemblies-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d4b885b6968b800bc965a9be1ec6b795a42220
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771500"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies-Methode
Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszAssembly1`  
 [in] Der Pfad zu die erste Assembly.  
  
 `wszAssembly2`  
 [in] Der Pfad für die zweite Assembly.  
  
 `pdwResult`  
 [out] Eine der folgenden Werte:  
  
- `SN_CMP_DIFFERENT` (0): Gibt an, dass die Assemblys mit unterschiedliche Daten enthalten.  
  
- `SN_CMP_IDENTICAL` (1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.  
  
- `SN_CMP_SIGONLY` (2): Gibt an, dass die Assemblys nur durch die Signatur und der Prüfsumme unterscheiden.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Hinweise  
 Die Signatur einer Assembly mit starkem Namen bestehen Textnamen, Version, Kultur und öffentliches Schlüsseltoken der Assembly ab.  
  
## <a name="see-also"></a>Siehe auch

- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
