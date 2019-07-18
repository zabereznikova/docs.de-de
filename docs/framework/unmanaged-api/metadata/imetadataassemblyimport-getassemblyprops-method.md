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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec04588bd1cc21e585d89c734c152a86fb835b15
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772732"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps-Methode
Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadaten-Signatur ab.  
  
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
 [in]. Die `mdAssembly` Metadatentoken, das die Assembly für das Abrufen der Eigenschaften darstellt.  
  
 `ppbPublicKey`  
 [out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKey`  
 [out] Die Anzahl der Bytes in den zurückgegebenen öffentlichen Schlüssel.  
  
 `pulHashAlgId`  
 [out] Ein Zeiger auf den Algorithmus für die Dateien in der Assembly zu hashen.  
  
 `szName`  
 [out] Der einfache Name der Assembly.  
  
 `cchName`  
 [in] Die Größe in Breitzeichen von `szName`.  
  
 `pchName`  
 [out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.  
  
 `pMetaData`  
 [out] Ein Zeiger auf ein ASSEMBLYMETADATA-Struktur, die die Metadaten der Assembly an.  
  
 `pdwAssemblyFlags`  
 [out] Flags, die auf eine Assembly angewendete Metadaten beschreiben. Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
