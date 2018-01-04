---
title: IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 123bd37d189477eade72e3b0e74f923fecce57a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef-Methode
Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `pbPublicKeyOrToken`  
 [in] Der öffentliche Schlüssel des Herausgebers der Assembly, auf die verwiesen wird. Die Hilfsfunktion [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) dienen zum Abrufen des Hashs des öffentlichen Schlüssels an diesen Parameter zu übergeben.  
  
 `cbPublicKeyOrToken`  
 [in] Die Größe in Bytes des `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Der lesbare Name der Assembly. Dieser Wert darf 1024 Zeichen nicht überschreiten.  
  
 `pMetaData`  
 [in] Eine ASSEMBLYMETADATA-Instanz, die Version, Plattform und Gebietsschema-Informationen der referenzierten Assembly enthält.  
  
 `pbHashValue`  
 [in] Der Hashwert der Daten die referenzierte Assembly zugeordnet. Dies ist optional.  
  
 `cbHashValue`  
 [in] Die Größe in Bytes des `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Eine bitweise Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die das Verhalten des Ausführungsmoduls beeinflussen.  
  
 `pmdar`  
 [out] Ein Zeiger auf das zurückgegebene `AssemblyRef` Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 Eine `AssemblyRef` Metadatenstruktur muss definiert werden, für jede Assembly, die diese Assembly verweist.  
  
 Zur Laufzeit werden die Details einer referenzierten Assembly, das der Assemblyresolver mit Angabe übergeben, dass sie die Informationen "wie erstellt" darstellen. Der Assemblyresolver wendet dann die Richtlinie.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
