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
ms.openlocfilehash: 7406a6118a9cca7087f913b3b2dd6f37a2d9238c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599893"
---
# <a name="imetadataemitsetmethodprops-method"></a>IMetaDataEmit::SetMethodProps-Methode
Legt fest oder aktualisiert die Funktion, die an der angegebenen relativen virtuellen Adresse, einer Methode, die von einem vorherigen Aufruf von definiert gespeicherte [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).  
  
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
 [in] Das Token für die Methode, die geändert werden.  
  
 `dwMethodFlags`  
 [in] Die Elementattribute.  
  
 `ulCodeRVA`  
 [in] Die Adresse des Codes.  
  
 `dwImplFlags`  
 [in] Die Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
