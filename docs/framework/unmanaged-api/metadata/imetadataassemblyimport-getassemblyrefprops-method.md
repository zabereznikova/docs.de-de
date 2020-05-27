---
title: IMetaDataAssemblyImport::GetAssemblyRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 2858e924ab6effe192955ce53dad9d333d2d244d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009066"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps-Methode
Ruft den Satz von Eigenschaften für den Assemblyverweis mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdar`  
 in Das `mdAssemblyRef` Metadatentoken, das den Assemblyverweis darstellt, für den die Eigenschaften zu erhalten sind.  
  
 `ppbPublicKeyOrToken`  
 vorgenommen Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKeyOrToken`  
 vorgenommen Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel oder Token.  
  
 `szName`  
 vorgenommen Der einfache Name der Assembly.  
  
 `cchName`  
 in Die Größe von in breit Zeichen `szName` .  
  
 `pchName`  
 vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, die tatsächlich in zurückgegeben werden `szName` .  
  
 `pMetaData`  
 vorgenommen Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.  
  
 `ppbHashValue`  
 vorgenommen Ein Zeiger auf den Hashwert. Dabei handelt es sich um den Hash mit dem SHA-1-Algorithmus der `PublicKey` Eigenschaft der Assembly, auf die verwiesen wird, es sei denn, das arffulloriginator-Flag der [AssemblyRefFlags](assemblyrefflags-enumeration.md) -Enumeration wurde festgelegt.  
  
 `pcbHashValue`  
 vorgenommen Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.  
  
 `pdwAssemblyRefFlags`  
 vorgenommen Ein Zeiger auf Flags, die die auf eine Assembly angewendeten Metadaten beschreiben. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt S_OK zurück, wenn Sie erfolgreich ausgeführt wird. Andernfalls wird einer der in der Header Datei "Winerror. h" definierten Fehlercodes zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
