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
ms.openlocfilehash: e28659f3c6912489775dd09951610f19e4400942
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672746"
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
 in Das Metadatentoken, das die `AssemblyRef` zu ändernde Metadatenstruktur angibt.  
  
 `pbPublicKeyOrToken`  
 in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird.  
  
 `cbPublicKeyOrToken`  
 in Die Größe von in Bytes `pbPublicKeyOrToken` .  
  
 `szName`  
 in Der lesbare Textname der Assembly.  
  
 `pMetaData`  
 in Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Versions-, Platt Form-und Gebiets Schema Informationen für die Assembly enthält.  
  
 `pbHashValue`  
 in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.  
  
 `cbHashValue`  
 in Die Größe von in Bytes `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 in Eine bitweise Kombination von [AssemblyRefFlags](assemblyrefflags-enumeration.md) -Werten, die Attribute der Assembly angeben, auf die verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie zum Erstellen einer `AssemblyRef` Metadatenstruktur die [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
