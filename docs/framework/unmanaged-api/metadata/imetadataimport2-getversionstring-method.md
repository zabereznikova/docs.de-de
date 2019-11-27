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
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445223"
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString-Methode
Ruft die Versionsnummer der Laufzeit ab, die zum Erstellen der Assembly verwendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzBuf`  
 vorgenommen Ein Array zum Speichern der Zeichenfolge, die die Version angibt.  
  
 `ccBufSize`  
 in Die Größe des `pwzBuf` Arrays in breit Zeichen.  
  
 `pccBufSize`  
 vorgenommen Die Anzahl der breit Zeichen (einschließlich eines NULL-Terminator), die im `pwzBuf` Array zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetVersionString`-Methode ruft die integrierte Version des aktuellen Metadatenbereichs ab. Wenn der Bereich noch nicht gespeichert wurde, verfügt er nicht über eine integrierte Version, und es wird eine leere Zeichenfolge zurückgegeben.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
