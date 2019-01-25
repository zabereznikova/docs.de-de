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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59dad67db9f9f9184a139f848020cf866a3a6771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716829"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps-Methode
Ruft die Eigenschaften der Datei mit der angegebenen Metadaten-Signatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `mdf`  
 [in] Die `mdFile` Metadatentoken, das die Datei für das Abrufen der Eigenschaften darstellt.  
  
 `szName`  
 [out] Der einfache Name der Datei.  
  
 `cchName`  
 [in] Die Größe in Breitzeichen von `szName`.  
  
 `pchName`  
 [out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.  
  
 `ppbHashValue`  
 [out] Ein Zeiger auf den Hashwert. Dies ist der Hash, mit dem SHA-1-Algorithmus, der Datei.  
  
 `pcbHashValue`  
 [out] Die Anzahl von Breitzeichen in den zurückgegebenen Hashwert.  
  
 `pdwFileFlags`  
 [out] Ein Zeiger auf die Flags, die auf eine Datei angewendete Metadaten beschreiben. Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
