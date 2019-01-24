---
title: IMetaDataImport2::GetVersionString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e041efed929255d4ce3af2d051a391bc4179cda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630917"
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString-Methode
Ruft die Version der Laufzeit, die verwendet wurde, zur Erstellung der Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzBuf`  
 [out] Ein Array zum Speichern der Zeichenfolge, die die Version angibt.  
  
 `ccBufSize`  
 [in] Die Größe in Breitzeichen, der die `pwzBuf` Array.  
  
 `pccBufSize`  
 [out] Die Anzahl von Breitzeichen, einschließlich eines null-Terminators zurückgegeben wird, der `pwzBuf` Array.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetVersionString` Methode ruft die für die Version der im aktuellen Metadatenbereich ab. Wenn der Bereich nicht gespeichert wurde, hat keine für die Version, und eine leere Zeichenfolge zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
