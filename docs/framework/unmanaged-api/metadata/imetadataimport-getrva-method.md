---
title: IMetaDataImport::GetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: a3a5cadc1b5a9df7967aae271ff10296843121dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436954"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA-Methode
Ruft die relative virtuelle Adresse (RVA) und die Implementierungsflags der Methode oder des Felds ab, die durch das angegebene Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 in Ein MethodDef-oder FieldDef-Metadatentoken, das das Code Objekt darstellt, für das die RVA zurückgegeben werden soll. Wenn das Token ein FieldDef-Token ist, muss es sich bei dem Feld um eine globale Variable handeln.  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Code Objekts, das durch das Token dargestellt wird.  
  
 `pdwImplFlags`  
 vorgenommen Ein Zeiger auf die Implementierungsflags für die Methode. Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration. Der Wert von `pdwImplFlags` ist nur gültig, wenn `tk` ein MethodDef-Token ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
