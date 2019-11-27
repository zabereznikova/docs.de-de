---
title: IMetaDataImport::GetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 4a258ce9121a287929ca5bc39c480f1ca2596e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437461"
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps-Methode
Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mb`  
 in Das MethodDef-Token, das die Methode darstellt, für die Metadaten zurückgegeben werden sollen.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.  
  
 `szMethod`  
 vorgenommen Ein Zeiger auf einen Puffer, der den Methodennamen aufweist.  
  
 `cchMethod`  
 in Die angeforderte Größe `szMethod`.  
  
 `pchMethod`  
 vorgenommen Ein Zeiger auf die Größe in breit Zeichen `szMethod`oder im Fall von abschneiden die tatsächliche Anzahl der breit Zeichen im Methodennamen.  
  
 `pdwAttr`  
 vorgenommen Ein Zeiger auf alle Flags, die der Methode zugeordnet sind.  
  
 `ppvSigBlob`  
 vorgenommen Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `pcbSigBlob`  
 vorgenommen Ein Zeiger auf die Größe `ppvSigBlob`in Byte.  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse der Methode.  
  
 `pdwImplFlags`  
 vorgenommen Ein Zeiger auf alle Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
