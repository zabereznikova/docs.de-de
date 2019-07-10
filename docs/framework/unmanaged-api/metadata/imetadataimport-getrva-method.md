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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d305aa59c1b9e9e1225b30f12e36fc689d584db1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778884"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA-Methode
Ruft ab, die relative virtuelle Adresse (RVA) sowie die Implementierung der Methode oder des Felds, die durch das angegebene Token dargestellt wird.  
  
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
 [in] Ein MethodDef oder FieldDef Metadatentoken, das die RVA für zurückzugebenden Code darstellt. Wenn das Token ein FieldDef ist, muss das Feld eine globale Variable sein.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse der vom Token dargestellten Codeobjekts.  
  
 `pdwImplFlags`  
 [out] Ein Zeiger auf die Implementierungsflags für die Methode. Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration. Der Wert des `pdwImplFlags` gilt nur, wenn `tk` ist ein MethodDef-Token.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
