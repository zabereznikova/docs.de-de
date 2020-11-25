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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722101"
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
 in Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.  
  
 `szName`  
 vorgenommen Der Name des exportierten Typs.  
  
 `cchName`  
 in Die Größe von in breit Zeichen `szName` .  
  
 `pchName`  
 vorgenommen Die Anzahl der tatsächlich zurückgegebenen breit Zeichen. `szName`  
  
 `ptkImplementation`  
 vorgenommen Ein-,-oder-Metadatentoken, `mdFile` `mdAssemblyRef` `mdExportedType` das den Zugriff auf die Eigenschaften des exportierten Typs enthält oder zulässt.  
  
 `ptkTypeDef`  
 vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.  
  
 `pdwExportedTypeFlags`  
 vorgenommen Ein Zeiger auf die Flags, die die auf den exportierten Typ angewendeten Metadaten beschreiben. Der Flags-Wert kann ein oder mehrere [CorTypeAttr](cortypeattr-enumeration.md) -Werte sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
