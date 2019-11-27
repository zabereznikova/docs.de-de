---
title: IMetaDataAssemblyImport::GetManifestResourceProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436316"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps-Methode
Ruft den Satz von Eigenschaften der Manifestressource mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdmr`  
 in Ein `mdManifestResource` Token, das die Ressource darstellt, für die die Eigenschaften zu erhalten sind.  
  
 `szName`  
 vorgenommen Der Name der Ressource.  
  
 `cchName`  
 in Die Größe `szName`in breiten Zeichen.  
  
 `pchName`  
 vorgenommen Ein Zeiger auf die Anzahl der breiten Zeichen, die tatsächlich in `szName`zurückgegeben werden.  
  
 `ptkImplementation`  
 vorgenommen Ein Zeiger auf ein `mdFile` Token oder ein `mdAssemblyRef` Token, das bzw. die bzw. die bzw. die bzw. die die Ressource enthält.  
  
 `pdwOffset`  
 vorgenommen Ein Zeiger auf einen-Wert, der den Offset bis zum Anfang der Ressource innerhalb der Datei angibt.  
  
 `pdwResourceFlags`  
 vorgenommen Ein Zeiger auf Flags, die die auf eine Ressource angewendeten Metadaten beschreiben. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) -Werten.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
