---
title: IMetaDataEmit::SetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ef6771ec3f458c20701cc330a5730367b3c5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445925"
---
# <a name="imetadataemitsetmethodprops-method"></a>IMetaDataEmit::SetMethodProps-Methode
Legt fest oder aktualisiert das Feature "" an der angegebenen relativen virtuellen Adresse, einer Methode, die durch einen vorherigen Aufruf definierten gespeicherte [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `md`  
 [in] Das Token für die Methode geändert werden.  
  
 `dwMethodFlags`  
 [in] Die Attribute des Elements.  
  
 `ulCodeRVA`  
 [in] Die Adresse des Codes.  
  
 `dwImplFlags`  
 [in] Die Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
