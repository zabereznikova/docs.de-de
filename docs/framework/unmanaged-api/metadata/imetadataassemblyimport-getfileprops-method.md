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
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175979"
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
 [in] Das `mdFile` Metadatentoken, das die Datei darstellt, für die die Eigenschaften abgerufen werden sollen.  
  
 `szName`  
 [out] Der einfache Name der Datei.  
  
 `cchName`  
 [in] Die Größe, in breiten `szName`Zeichen, von .  
  
 `pchName`  
 [out] Die Anzahl der breiten Zeichen, die tatsächlich in `szName`zurückgegeben wurden.  
  
 `ppbHashValue`  
 [out] Ein Zeiger auf den Hashwert. Dies ist der Hash der Datei mit dem SHA-1-Algorithmus.  
  
 `pcbHashValue`  
 [out] Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.  
  
 `pdwFileFlags`  
 [out] Ein Zeiger auf die Flags, die die Metadaten beschreiben, die auf eine Datei angewendet werden. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorFileFlags-Werten.](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
