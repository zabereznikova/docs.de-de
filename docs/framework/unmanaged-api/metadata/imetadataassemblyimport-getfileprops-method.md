---
title: IMetaDataAssemblyImport::GetFileProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 0b9ff2716cc0bc32c81fe6fcdd4e6c367d4d835f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718175"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps-Methode

Ruft die Eigenschaften der Datei mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mdf`  
 in Das `mdFile` Metadatentoken, das die Datei darstellt, für die die Eigenschaften zu erhalten sind.  
  
 `szName`  
 vorgenommen Der einfache Name der Datei.  
  
 `cchName`  
 in Die Größe von in breit Zeichen `szName` .  
  
 `pchName`  
 vorgenommen Die Anzahl der breit Zeichen, die in tatsächlich zurückgegeben wurden `szName` .  
  
 `ppbHashValue`  
 vorgenommen Ein Zeiger auf den Hashwert. Dies ist der Hash, der den SHA-1-Algorithmus der Datei verwendet.  
  
 `pcbHashValue`  
 vorgenommen Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.  
  
 `pdwFileFlags`  
 vorgenommen Ein Zeiger auf die Flags, die die auf eine Datei angewendeten Metadaten beschreiben. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorFileFlags](corfileflags-enumeration.md) -Werten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
