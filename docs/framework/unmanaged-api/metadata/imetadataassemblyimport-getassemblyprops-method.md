---
title: IMetaDataAssemblyImport::GetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449443"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps-Methode
Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mda`  
 [in]. Das `mdAssembly` Metadatentoken, das die Assembly darstellt, für die die Eigenschaften zu erhalten sind.  
  
 `ppbPublicKey`  
 vorgenommen Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKey`  
 vorgenommen Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel.  
  
 `pulHashAlgId`  
 vorgenommen Ein Zeiger auf den Algorithmus, der zum Hash der Dateien in der Assembly verwendet wird.  
  
 `szName`  
 vorgenommen Der einfache Name der Assembly.  
  
 `cchName`  
 in Die Größe `szName`in breiten Zeichen.  
  
 `pchName`  
 vorgenommen Die Anzahl der breit Zeichen, die in `szName`tatsächlich zurückgegeben werden.  
  
 `pMetaData`  
 vorgenommen Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.  
  
 `pdwAssemblyFlags`  
 vorgenommen Flags, die die auf eine Assembly angewendeten Metadaten beschreiben. Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) -Werten.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
