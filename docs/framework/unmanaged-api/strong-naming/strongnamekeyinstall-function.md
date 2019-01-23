---
title: StrongNameKeyInstall-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecd52fce8033876f0599fa0ba25fae0850c0e01f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508485"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall-Funktion
Importiert ein öffentliches/privates Schlüsselpaar in einen Container.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode stattdessen.  
  
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
 [in] Der Name des Containers mit dem Schlüssel. `wszKeyContainer` eine nicht leere Zeichenfolge muss sein.  
  
 `pbKeyBlob`  
 [in] Das binäre Schlüsselpaar.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, des `pbKeyBlob`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) Funktion, um den Schlüsselcontainer zu löschen.  
  
 Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [StrongNameKeyInstall-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
