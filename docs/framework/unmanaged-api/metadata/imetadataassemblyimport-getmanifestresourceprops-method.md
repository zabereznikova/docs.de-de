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
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177659"
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
 [in] Ein `mdManifestResource` Token, das die Ressource darstellt, für die die Eigenschaften abgerufen werden sollen.  
  
 `szName`  
 [out] Der Name der Ressource.  
  
 `cchName`  
 [in] Die Größe, in breiten `szName`Zeichen, von .  
  
 `pchName`  
 [out] Ein Zeiger auf die Anzahl der breiten `szName`Zeichen, die tatsächlich in zurückgegeben wurden.  
  
 `ptkImplementation`  
 [out] Ein Zeiger auf `mdFile` ein `mdAssemblyRef` Token oder ein Token, das die Datei bzw. Assembly darstellt, die die Ressource enthält.  
  
 `pdwOffset`  
 [out] Ein Zeiger auf einen Wert, der den Offset zum Anfang der Ressource in der Datei angibt.  
  
 `pdwResourceFlags`  
 [out] Ein Zeiger auf Flags, die die Metadaten beschreiben, die auf eine Ressource angewendet werden. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags-Werten.](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
