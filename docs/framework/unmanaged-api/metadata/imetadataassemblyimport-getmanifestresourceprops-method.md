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
ms.openlocfilehash: c0b6d53ce3be3aed6a577bf6e38a281928499848
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009027"
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
 in Die Größe von in breit Zeichen `szName` .  
  
 `pchName`  
 vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, die tatsächlich in zurückgegeben werden `szName` .  
  
 `ptkImplementation`  
 vorgenommen Ein Zeiger auf ein `mdFile` Token oder ein `mdAssemblyRef` Token, das bzw. die bzw. die bzw. die bzw. die die Ressource enthält.  
  
 `pdwOffset`  
 vorgenommen Ein Zeiger auf einen-Wert, der den Offset bis zum Anfang der Ressource innerhalb der Datei angibt.  
  
 `pdwResourceFlags`  
 vorgenommen Ein Zeiger auf Flags, die die auf eine Ressource angewendeten Metadaten beschreiben. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) -Werten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
