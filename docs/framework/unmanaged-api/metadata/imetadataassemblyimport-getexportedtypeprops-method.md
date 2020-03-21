---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177757"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps-Methode
Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdct`  
 [in] Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.  
  
 `szName`  
 [out] Der Name des exportierten Typs.  
  
 `cchName`  
 [in] Die Größe von in `szName`weiten Zeichen von .  
  
 `pchName`  
 [out] Die Anzahl der breiten Zeichen, die tatsächlich in`szName`  
  
 `ptkImplementation`  
 [out] Ein `mdFile` `mdAssemblyRef`, `mdExportedType` oder Metadatentoken, das die Eigenschaften des exportierten Typs enthält oder zulässt.  
  
 `ptkTypeDef`  
 [out] Ein Zeiger auf `mdTypeDef` ein Token, das einen Typ in der Datei darstellt.  
  
 `pdwExportedTypeFlags`  
 [out] Ein Zeiger auf die Flags, die die Metadaten beschreiben, die auf den exportierten Typ angewendet werden. Der Flags-Wert kann ein oder mehrere [CorTypeAttr-Werte](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
