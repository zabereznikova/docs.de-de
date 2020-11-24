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
ms.openlocfilehash: ba53ff30f0b6d0ae7fed7db422b7c0a242204a2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689432"
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
 in Der öffentliche Schlüssel des Verlegers der Assembly, auf die verwiesen wird. Die Hilfsfunktion [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) kann verwendet werden, um den Hash des öffentlichen Schlüssels zu erhalten, der als dieser Parameter übergeben werden soll.  
  
 `cbPublicKeyOrToken`  
 in Die Größe von in Bytes `pbPublicKeyOrToken` .  
  
 `szName`  
 in Der lesbare Textname der Assembly. Dieser Wert darf nicht länger als 1024 Zeichen sein.  
  
 `pMetaData`  
 in Eine ASSEMBLYMETADATA-Instanz, die die Informationen zu Version, Plattform und Gebiets Schema der Assembly enthält, auf die verwiesen wird.  
  
 `pbHashValue`  
 in Die der referenzierten Assembly zugeordneten Hashdaten. Dies ist optional.  
  
 `cbHashValue`  
 in Die Größe von in Bytes `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 in Eine bitweise Kombination von [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten, die das Verhalten der Ausführungs-Engine beeinflussen.  
  
 `pmdar`  
 vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken `AssemblyRef` .  
  
## <a name="remarks"></a>Hinweise  

 `AssemblyRef`Für jede Assembly, auf die diese Assembly verweist, muss eine Metadatenstruktur definiert werden.  
  
 Zur Laufzeit werden die Details einer Assembly, auf die verwiesen wird, an den Assemblyresolver übermittelt, die darauf hinweist, dass Sie die "als erstellt"-Informationen darstellen. Der Assemblyresolver wendet dann die Richtlinie an  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
