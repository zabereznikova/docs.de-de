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
ms.openlocfilehash: 2662af41fbd2cdc3ce8a6df1e036dfc5b22ff6a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175550"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope-Methode
Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.  
  
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
 [in] Die Schnittstelle für die Importassembly (wobei die Signatur definiert ist).  
  
 `pbHashValue`  
 [in] Das Hash-Blob für die Assembly.  
  
 `cbHashValue`  
 [in] Die Anzahl der `pbHashValue`Bytes in .  
  
 `import`  
 [in] Die Schnittstelle für den Importmetadatenbereich.  
  
 `pbSigBlob`  
 [in] Die zu importierende Signatur.  
  
 `cbSigBlob`  
 [in] Die Größe von in `pbSigBlob`Bytes von .  
  
 `pAssemEmit`  
 [in] Die Schnittstelle für die Exportassembly.  
  
 `emit`  
 [in] Die Schnittstelle für den Export metadatenbereich.  
  
 `pvTranslatedSig`  
 [out] Der Puffer, der das übersetzte Signaturblob enthalten soll.  
  
 `cbTranslatedSigMax`  
 [in] Die Kapazität (in `pvTranslatedSig`Bytes) von .  
  
 `pcbTranslatedSig`  
 [out] Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
