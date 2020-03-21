---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175446"
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets-Methode
Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss NULL für den ersten Aufruf dieser Methode sein.  
  
 `tk`  
 [in] Ein Metadatentoken, das den Suchbereich einschränkt, oder NULL, um den größtmöglichen Bereich zu durchsuchen.  
  
 `dwActions`  
 [in] Flags, <xref:System.Security.Permissions.SecurityAction> die die `rPermission`Werte darstellen, die in enthalten werden sollen, oder Null, um alle Aktionen zurückzugeben.  
  
 `rPermission`  
 [out] Das Array, das zum Speichern der Berechtigungstoken verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rPermission`-Arrays.  
  
 `pcTokens`  
 [out] Die Anzahl der in `rPermission`zurückgegebenen Berechtigungstoken.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine Token zum Aufzählen vorhanden. In diesem `pcTokens` Fall ist Null.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
