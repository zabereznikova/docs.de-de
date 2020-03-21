---
title: IMetaDataAssemblyEmit::DefineManifestResource-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177868"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource-Methode
Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name der Ressource.  
  
 `tkImplementation`  
 [in] Ein Metadatentoken `mdtFile` des `mdtAssemblyRef` Typs oder das dem Ressourcenanbieter zugeordnet ist. Ein NULL-Wert gibt an, dass die Datei, in die die Metadaten eingebettet sind, der Ressourcenanbieter ist.  
  
 `dwOffset`  
 [in] Der Offset zum Anfang der Ressource in der Datei. Bei Ressourcen in eigenständigen Dateien ist dies immer Null. Wenn die Ressource in eine PE-Datei (portable executable) eingebettet ist, handelt es sich um einen Offset der Ressource BLOB, der an dem in der cor.h-Headerdatei angegebenen Speicherort beginnt.  
  
 `dwResourceFlags`  
 [in] Eine bitweise Kombination von Flagwerten, die Eigenschafteneinstellungen für die Ressourcendefinition angeben.  
  
 `pmdmr`  
 [out] Ein Zeiger auf das zurückgegebene Metadatentoken.  
  
## <a name="remarks"></a>Bemerkungen  
 Für `ManifestResource` jede Ressource, die in jeder Assemblydatei implementiert ist, muss eine Metadatenstruktur definiert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
