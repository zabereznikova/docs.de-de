---
title: IMetaDataEmit::TranslateSigWithScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440477"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope-Methode
Importiert eine Assembly in den aktuellen Gültigkeitsbereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAssemImport`  
 in Die Schnittstelle für die importierungsassembly (in der die Signatur definiert ist).  
  
 `pbHashValue`  
 in Das hashblob für die Assembly.  
  
 `cbHashValue`  
 in Die Anzahl der Bytes in `pbHashValue`.  
  
 `import`  
 in Die-Schnittstelle für den Import Metadatenbereich.  
  
 `pbSigBlob`  
 in Die Signatur, die importiert werden soll.  
  
 `cbSigBlob`  
 in Die Größe `pbSigBlob`in Byte.  
  
 `pAssemEmit`  
 in Die Schnittstelle für die exportierungsassembly.  
  
 `emit`  
 in Die-Schnittstelle für den Export Metadatenbereich.  
  
 `pvTranslatedSig`  
 vorgenommen Der Puffer, der das übersetzte Signatur-BLOB enthalten soll.  
  
 `cbTranslatedSigMax`  
 in Die Kapazität `pvTranslatedSig`in Byte.  
  
 `pcbTranslatedSig`  
 vorgenommen Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
