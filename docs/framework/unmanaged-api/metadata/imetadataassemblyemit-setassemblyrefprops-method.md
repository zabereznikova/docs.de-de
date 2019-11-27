---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: 5434aa2d12bd9a29a8c2fc784421442469ceb1ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440560"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyRefProps-Methode
Ändert die angegebene `AssemblyRef`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ar`  
 in Das Metadatentoken, das die zu ändernde `AssemblyRef` Metadatenstruktur angibt.  
  
 `pbPublicKeyOrToken`  
 in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird.  
  
 `cbPublicKeyOrToken`  
 in Die Größe `pbPublicKeyOrToken`in Byte.  
  
 `szName`  
 in Der lesbare Textname der Assembly.  
  
 `pMetaData`  
 in Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Platt Form-und Gebiets Schema Informationen für die Assembly enthält.  
  
 `pbHashValue`  
 in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.  
  
 `cbHashValue`  
 in Die Größe `pbHashValue`in Byte.  
  
 `dwAssemblyRefFlags`  
 in Eine bitweise Kombination von [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) -Werten, die Attribute der Assembly angeben, auf die verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Um eine `AssemblyRef` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) -Methode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
