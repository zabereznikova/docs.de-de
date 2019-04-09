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
ms.openlocfilehash: b95a583aec87e3ba3e247d1ef800302b62657837
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176006"
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
  
## <a name="parameters"></a>Parameter  
 `pbPublicKey`  
 [in] Der öffentliche Schlüssel, der den Verleger der der Assembly oder NULL, wird ermittelt, ob die Assembly keinen starken Namen aufweist.  
  
 `cbPublicKey`  
 [in] Die Größe in Bytes der `pbPublicKey`.  
  
 `uHashAlgId`  
 [in] Der Bezeichner des Hashalgorithmus zu verwenden, um die Dateien in der Assembly, oder NULL zum Angeben des SHA-1-Algorithmus zu verschlüsseln.  
  
 `szName`  
 [in] Der Benutzer lesbarer Textname der Assembly. Dieser Wert darf 1024 Zeichen nicht überschreiten.  
  
 `pMetaData`  
 [in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema-Informationen für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 [in] Eine Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die Features der Assembly zu beschreiben.  
  
 `pmda`  
 [out] Ein Zeiger auf das Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 Nur ein `Assembly` Metadatenstruktur kann in einem Manifest definiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
