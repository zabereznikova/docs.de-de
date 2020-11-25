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
ms.openlocfilehash: 80d33da2eb2a7f0cfbe5dcb7279fff9973dada2e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712923"
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
 in Die Anzahl von Bytes in `pbHashValue` .  
  
 `import`  
 in Die-Schnittstelle für den Import Metadatenbereich.  
  
 `pbSigBlob`  
 in Die Signatur, die importiert werden soll.  
  
 `cbSigBlob`  
 in Die Größe von in Bytes `pbSigBlob` .  
  
 `pAssemEmit`  
 in Die Schnittstelle für die exportierungsassembly.  
  
 `emit`  
 in Die-Schnittstelle für den Export Metadatenbereich.  
  
 `pvTranslatedSig`  
 vorgenommen Der Puffer, der das übersetzte Signatur-BLOB enthalten soll.  
  
 `cbTranslatedSigMax`  
 in Die Kapazität von in Byte `pvTranslatedSig` .  
  
 `pcbTranslatedSig`  
 vorgenommen Die Anzahl der tatsächlichen Bytes in der übersetzten Signatur.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
