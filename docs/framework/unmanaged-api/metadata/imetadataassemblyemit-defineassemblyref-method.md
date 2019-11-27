---
title: IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432079"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbPublicKeyOrToken`  
 in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird. Die Hilfsfunktion [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) kann verwendet werden, um den Hash des öffentlichen Schlüssels zu erhalten, der als dieser Parameter übergeben werden soll.  
  
 `cbPublicKeyOrToken`  
 in Die Größe `pbPublicKeyOrToken`in Byte.  
  
 `szName`  
 in Der lesbare Textname der Assembly. Dieser Wert darf nicht länger als 1024 Zeichen sein.  
  
 `pMetaData`  
 in Eine ASSEMBLYMETADATA-Instanz, die die Informationen zu Version, Plattform und Gebiets Schema der Assembly enthält, auf die verwiesen wird.  
  
 `pbHashValue`  
 in Die der referenzierten Assembly zugeordneten Hashdaten. Optional.  
  
 `cbHashValue`  
 in Die Größe `pbHashValue`in Byte.  
  
 `dwAssemblyRefFlags`  
 in Eine bitweise Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) -Werten, die das Verhalten der Ausführungs-Engine beeinflussen.  
  
 `pmdar`  
 vorgenommen Ein Zeiger auf die zurückgegebene `AssemblyRef` Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 Für jede Assembly, auf die diese Assembly verweist, muss eine `AssemblyRef` Metadatenstruktur definiert werden.  
  
 Zur Laufzeit werden die Details einer Assembly, auf die verwiesen wird, an den Assemblyresolver übermittelt, die darauf hinweist, dass Sie die "als erstellt"-Informationen darstellen. Der Assemblyresolver wendet dann die Richtlinie an  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
