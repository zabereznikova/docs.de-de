---
title: IMetaDataAssemblyEmit::SetFileProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176031"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>IMetaDataAssemblyEmit::SetFileProps-Methode
Ändert die angegebene `File`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `file`  
 [in] Das Metadatentoken, das `File` die zu ändernde Metadatenstruktur angibt.  
  
 `pbHashValue`  
 [in] Ein Zeiger auf die Hashdaten, die der Datei zugeordnet sind.  
  
 `cbHashValue`  
 [in] Die Größe in `pbHashValue`Bytes von .  
  
 `dwFileFlags`  
 [in] Eine bitweise Kombination von [CorFileFlags-Werten,](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) die verschiedene Attribute der Datei angeben.  
  
## <a name="remarks"></a>Bemerkungen  
 Um eine `File` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::DefineFile-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
