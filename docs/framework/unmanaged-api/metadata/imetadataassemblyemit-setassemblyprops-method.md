---
title: IMetaDataAssemblyEmit::SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431949"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps-Methode
Ändert die angegebene `Assembly`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pma`  
 in Das Metadatentoken, das die zu ändernde `Assembly` Metadatenstruktur angibt.  
  
 `pbPublicKey`  
 in Ein Zeiger auf den öffentlichen Schlüssel des Verlegers der Assembly.  
  
 `cbPublicKey`  
 in Die Größe `pbPublicKey`in Byte.  
  
 `ulHashAlgId`  
 in Der Bezeichner für den Hash Algorithmus, der zum Hash der Assemblydateien verwendet wird.  
  
 `szName`  
 in Der lesbare Textname der Assembly.  
  
 `pMetaData`  
 in Ein Zeiger auf die ASSEMBLYMETADATA, die Informationen zu Version, Plattform und Gebiets Schema für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 in Eine bitweise Kombination von [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) -Werten, die verschiedene Attribute der Assembly angeben.  
  
## <a name="remarks"></a>Hinweise  
 Um eine `Assembly` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::D efineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) -Methode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
