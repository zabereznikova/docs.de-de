---
title: IMetaDataAssemblyImport::EnumExportedTypes-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54b5a51dc0a12bb4c159b61252c9db0a82f03518
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes-Methode
Listet die exportierten Typen, die im Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss ein NULL-Wert sein Wert der `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.  
  
 `rExportedTypes`  
 [out] Die Enumeration von `mdExportedType` Metadatentoken verwendet.  
  
 `cMax`  
 [in] Die maximale Anzahl von `mdExportedType` Token, die in platziert werden, können die `rExportedTypes` Array.  
  
 `pcTokens`  
 [out] Die Anzahl der `mdExportedType` Token, die tatsächlich in `rExportedTypes`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token aufgelistet werden. In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
