---
title: StrongNameKeyInstall-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a8dbc84f375b7bbbad47971936650d81c5c63df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall-Funktion
Importiert ein öffentliches/privates Schlüsselpaar in einen Container.  
  
 Diese Funktion ist veraltet. Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers. `wszKeyContainer`eine nicht leere Zeichenfolge muss sein.  
  
 `pbKeyBlob`  
 [in] Das binäre Schlüsselpaar.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, der `pbKeyBlob`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) Funktion, um den Schlüsselcontainer zu löschen.  
  
 Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameKeyInstall-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [StrongNameKeyDelete-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
