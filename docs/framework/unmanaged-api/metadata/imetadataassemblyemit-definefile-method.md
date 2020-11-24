---
title: IMetaDataAssemblyEmit::DefineFile-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 1dd71dbe0ddb894cb5ed05c32e50429d27c66aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689328"
---
# <a name="imetadataassemblyemitdefinefile-method"></a>IMetaDataAssemblyEmit::DefineFile-Methode

Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szName`  
 in Der Name der zu verwendenden Datei.  
  
 `pbHashValue`  
 in Ein Zeiger auf die Hashdaten, die der Assembly zugeordnet sind.  
  
 `cbHashValue`  
 in Die Größe von in Bytes `pbHashValue` .  
  
 `dwFileFlags`  
 in Eine bitweise Kombination von- `FileFlags` Werten, die Eigenschafts Einstellungen angeben.  
  
 `pmdf`  
 vorgenommen Ein Zeiger auf das zurückgegebene `File` Token.  
  
## <a name="remarks"></a>Hinweise  

 Für jede Datei, die zum Zeitpunkt der Erstellung `File` dieser Assembly Bestandteil dieser Assembly war, muss eine Metadatenstruktur definiert werden, ausgenommen die Datei, die die Metadaten enthält.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
