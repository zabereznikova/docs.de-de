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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa633d554652050af51065e11221f898b34d5c63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772674"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps-Methode
Ruft den Satz von Eigenschaften für den der Assemblyverweis verweist mit der angegebenen Metadaten-Signatur ab.  
  
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
 [in] Die `mdAssemblyRef` Metadatentoken, das die Assemblyverweis für das Abrufen der Eigenschaften darstellt.  
  
 `ppbPublicKeyOrToken`  
 [out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.  
  
 `pcbPublicKeyOrToken`  
 [out] Die Anzahl der Bytes im öffentlichen Schlüssel oder ein token zurückgegeben.  
  
 `szName`  
 [out] Der einfache Name der Assembly.  
  
 `cchName`  
 [in] Die Größe in Breitzeichen von `szName`.  
  
 `pchName`  
 [out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.  
  
 `pMetaData`  
 [out] Ein Zeiger auf ein ASSEMBLYMETADATA-Struktur, die die Metadaten der Assembly an.  
  
 `ppbHashValue`  
 [out] Ein Zeiger auf den Hashwert. Dies ist der Hash, mit dem SHA-1-Algorithmus, der die `PublicKey` die Assemblyeigenschaft auf die verwiesen wird, es sei denn, das ArfFullOriginator-flag von der [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) Enumeration festgelegt ist.  
  
 `pcbHashValue`  
 [out] Die Anzahl von Breitzeichen in den zurückgegebenen Hashwert.  
  
 `pdwAssemblyRefFlags`  
 [out] Ein Zeiger auf Flags, die auf eine Assembly angewendete Metadaten beschreiben. Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt S_OK zurück, wenn er erfolgreich abgeschlossen wurde; Andernfalls wird eine der in der Headerdatei "Winerror.h" definierten Fehlercodes zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
