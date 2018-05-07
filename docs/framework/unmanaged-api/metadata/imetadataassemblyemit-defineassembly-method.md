---
title: IMetaDataAssemblyEmit::DefineAssembly-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9115657c52f31d9b7b7da3c843338670343da26c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly-Methode
Erstellt eine `Assembly` Struktur, die Metadaten für die angegebene Assembly und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pbPublicKey`  
 [in] Der öffentliche Schlüssel, der den Herausgeber der Assembly oder NULL angibt, wenn die Assembly keinen starken Namen aufweist.  
  
 `cbPublicKey`  
 [in] Die Größe in Bytes des `pbPublicKey`.  
  
 `uHashAlgId`  
 [in] Der Bezeichner des Hashalgorithmus für die Verschlüsselung von Dateien in der Assembly oder NULL, wenn der SHA-1-Algorithmus angegeben werden.  
  
 `szName`  
 [in] Der lesbare Name der Assembly. Dieser Wert darf 1024 Zeichen nicht überschreiten.  
  
 `pMetaData`  
 [in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 [in] Eine Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die Funktionen der Assembly zu beschreiben.  
  
 `pmda`  
 [out] Ein Zeiger auf das Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 Nur ein `Assembly` Metadatenstruktur innerhalb eines Manifests definiert werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
