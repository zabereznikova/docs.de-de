---
title: IMetaDataAssemblyImport::GetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: 1e1a86cdf55812197aae653dca256fb910a7f168
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733892"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps-Methode

Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mda`  
 [in] Das `mdAssembly` Metadatentoken, das die Assembly darstellt, für die die Eigenschaften zu erhalten sind.  
  
 `ppbPublicKey`  
 vorgenommen Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKey`  
 vorgenommen Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel.  
  
 `pulHashAlgId`  
 vorgenommen Ein Zeiger auf den Algorithmus, der zum Hash der Dateien in der Assembly verwendet wird.  
  
 `szName`  
 vorgenommen Der einfache Name der Assembly.  
  
 `cchName`  
 in Die Größe von in breit Zeichen `szName` .  
  
 `pchName`  
 vorgenommen Die Anzahl der breit Zeichen, die in tatsächlich zurückgegeben wurden `szName` .  
  
 `pMetaData`  
 vorgenommen Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.  
  
 `pdwAssemblyFlags`  
 vorgenommen Flags, die die auf eine Assembly angewendeten Metadaten beschreiben. Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
