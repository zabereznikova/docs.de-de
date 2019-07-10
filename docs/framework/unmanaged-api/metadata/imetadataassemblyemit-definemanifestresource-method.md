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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 781953fe5bf209f195ef4887dff45e1902741f0c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775309"
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
 [in] Ein Metadatentoken des Typs `mdtFile` oder `mdtAssemblyRef` , der dem Ressourcenanbieter zugeordnet. Ein NULL-Wert gibt an, dass die Datei, in der die Metadaten eingebettet ist, der Ressourcenanbieter ist.  
  
 `dwOffset`  
 [in] Der Offset auf den Anfang der Ressource in der Datei. Für Ressourcen in eigenständigen Dateien wird dies immer 0 (null) sein. Wenn die Ressource in einer PE (portable ausführbare Datei)-Datei eingebettet ist, ist dies ein Offset von der Ressource ein BLOB, der an der in der Headerdatei cor.h angegebenen Position beginnt.  
  
 `dwResourceFlags`  
 [in] Eine bitweise Kombination der Flagwerte, die eigenschaftseinstellungen für die Definition der Ressource angeben.  
  
 `pmdmr`  
 [out] Ein Zeiger auf die zurückgegebenen Metadaten-Token.  
  
## <a name="remarks"></a>Hinweise  
 Eine `ManifestResource` Metadatenstruktur muss definiert werden, für jede Ressource, die in jeder der die Dateien der Assembly implementiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
