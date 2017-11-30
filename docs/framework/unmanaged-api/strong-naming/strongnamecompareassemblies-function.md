---
title: StrongNameCompareAssemblies-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameCompareAssemblies
helpviewer_keywords: StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3453cffb5e98e3623565785ab64db4f455be981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies-Funktion
Bestimmt, ob zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.  
  
 Diese Funktion ist veraltet. Verwenden der [ICLRStrongName:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszAssembly1`  
 [in] Der Pfad zur ersten Assembly.  
  
 `wszAssembly2`  
 [in] Der Pfad auf die zweite Assembly.  
  
 `pdwResult`  
 [out] Einer der folgenden Werte:  
  
-   `SN_CMP_DIFFERENT`(0) – gibt an, dass die Assemblys verschiedene Daten enthalten.  
  
-   `SN_CMP_IDENTICAL`(1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.  
  
-   `SN_CMP_SIGONLY`(2) – gibt an, dass die Assemblys nur durch Signatur und Prüfsumme unterscheiden.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Hinweise  
 Die starke Namenssignatur einer Assembly besteht aus der Assembly aneinander gehängt Textnamen, Version, Kultur und öffentliches Schlüsseltoken.  
  
 Wenn die `StrongNameCompareAssemblies` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameCompareAssemblies-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
