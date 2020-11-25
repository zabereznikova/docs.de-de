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
ms.openlocfilehash: 3729f06097fa4dce6de009307183d5e97c24479b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728302"
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
 in Ein Metadatentoken vom Typ `mdtFile` oder `mdtAssemblyRef` , das dem Ressourcenanbieter zugeordnet wird. Ein NULL-Wert gibt an, dass die Datei, in die die Metadaten eingebettet sind, der Ressourcenanbieter ist.  
  
 `dwOffset`  
 in Der Offset zum Anfang der Ressource innerhalb der Datei. Für Ressourcen in eigenständigen Dateien ist dies immer 0 (null). Wenn die Ressource in eine ausführbare PE-Datei (portable ausführbare Datei) eingebettet ist, handelt es sich hierbei um einen Offset des ressourcenblobs, der an dem in der "Cor. h"-Header Datei angegebenen Speicherort beginnt.  
  
 `dwResourceFlags`  
 in Eine bitweise Kombination von Flagwerten, die Eigenschafts Einstellungen für die Ressourcendefinition angeben.  
  
 `pmdmr`  
 vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  

 Eine `ManifestResource` Metadatenstruktur muss für jede Ressource definiert werden, die in jeder der Assemblydateien implementiert wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
