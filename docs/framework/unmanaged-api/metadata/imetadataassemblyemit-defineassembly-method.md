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
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432117"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly-Methode
Erstellt eine `Assembly` Struktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Der öffentliche Schlüssel, der den Verleger der Assembly identifiziert, oder NULL, wenn die Assembly nicht den starken Namen hat.  
  
 `cbPublicKey`  
 in Die Größe `pbPublicKey`in Byte.  
  
 `uHashAlgId`  
 in Der Bezeichner des Hash Algorithmus, der zum Verschlüsseln der Dateien in der Assembly verwendet werden soll, oder NULL, um den SHA-1-Algorithmus anzugeben.  
  
 `szName`  
 in Der lesbare Textname der Assembly. Dieser Wert darf nicht länger als 1024 Zeichen sein.  
  
 `pMetaData`  
 in Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Platt Form-und Gebiets Schema Informationen für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 in Eine Kombination aus [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) -Werten, mit denen die Funktionen der Assembly beschrieben werden.  
  
 `pmda`  
 vorgenommen Ein Zeiger auf das Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 In einem Manifest kann nur eine `Assembly` Metadatenstruktur definiert werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
