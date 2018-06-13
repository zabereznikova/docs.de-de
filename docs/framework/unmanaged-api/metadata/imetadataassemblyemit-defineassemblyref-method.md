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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6675d50d3222a43abc8838c3c86cb825d2dad16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445717"
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
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
