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
ms.openlocfilehash: 112ddcf51a5637bb89df9479850c2a4a70d2e1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448725"
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString-Methode
Ruft die Version der Laufzeit, die verwendet wurde, zum Erstellen der Assembly ab.  
  
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
 [out] Die Anzahl der Breitzeichen, einschließlich eines null-Terminators zurückgegeben, der `pwzBuf` Array.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetVersionString` Methode ruft die für die Version des aktuellen Metadatenbereich ab. Wenn der Bereich nie gespeichert wurde, sind eine für die Version und eine leere Zeichenfolge zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
