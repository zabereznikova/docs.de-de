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
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175966"
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
 [in] Das `mdAssemblyRef` Metadatentoken, das den Assemblyverweis darstellt, für den die Eigenschaften abgerufen werden sollen.  
  
 `ppbPublicKeyOrToken`  
 [out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKeyOrToken`  
 [out] Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel oder Token.  
  
 `szName`  
 [out] Der einfache Name der Assembly.  
  
 `cchName`  
 [in] Die Größe, in breiten `szName`Zeichen, von .  
  
 `pchName`  
 [out] Ein Zeiger auf die Anzahl der breiten `szName`Zeichen, die tatsächlich in zurückgegeben wurden.  
  
 `pMetaData`  
 [out] Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.  
  
 `ppbHashValue`  
 [out] Ein Zeiger auf den Hashwert. Dies ist der Hash mithilfe des SHA-1-Algorithmus der `PublicKey` Eigenschaft der Assembly, auf die verwiesen wird, es sei denn, das arfFullOriginator-Flag der [AssemblyRefFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) wird festgelegt.  
  
 `pcbHashValue`  
 [out] Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.  
  
 `pdwAssemblyRefFlags`  
 [out] Ein Zeiger auf Flags, die die Metadaten beschreiben, die auf eine Assembly angewendet werden. Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags-Werten.](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt S_OK zurück, wenn sie erfolgreich ist. Andernfalls wird einer der in der Winerror.h-Headerdatei definierten Fehlercodes zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
