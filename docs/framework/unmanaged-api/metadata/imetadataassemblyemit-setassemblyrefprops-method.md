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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 984ec5dea757971081ce05c858788473a0f616e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775274"
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
 [in] Das Metadatentoken, der angibt, die `AssemblyRef` Metadatenstruktur geändert werden.  
  
 `pbPublicKeyOrToken`  
 [in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird.  
  
 `cbPublicKeyOrToken`  
 [in] Die Größe in Bytes der `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Der Benutzer lesbarer Textname der Assembly.  
  
 `pMetaData`  
 [in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema-Informationen für die Assembly enthält.  
  
 `pbHashValue`  
 [in] Ein Zeiger auf den Hashwert der Daten zu dieser Assembly zugeordneten.  
  
 `cbHashValue`  
 [in] Die Größe in Bytes der `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Eine bitweise Kombination von [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) Werte, die Attribute der referenzierten Assembly angeben.  
  
## <a name="remarks"></a>Hinweise  
 Zum Erstellen einer `AssemblyRef` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
