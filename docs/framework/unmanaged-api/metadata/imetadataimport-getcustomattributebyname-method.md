---
title: IMetaDataImport::GetCustomAttributeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: 3eb894aaf8ccdc99ea23ddf946f39f3ec71773d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711207"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName-Methode

Ruft das benutzerdefinierte Attribut ab, wenn Name und Besitzer angegeben sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `tkObj`  
 in Ein Metadatentoken, das das Objekt darstellt, das das benutzerdefinierte Attribut besitzt.  
  
 `szName`  
 in Der Name des benutzerdefinierten Attributs.  
  
 `ppData`  
 vorgenommen Ein Zeiger auf ein Array von Daten, das den Wert des benutzerdefinierten Attributs ist.  
  
 `pcbData`  
 vorgenommen Die Größe der Daten in Bytes, die in * zurückgegeben werden `ppData` .  
  
## <a name="remarks"></a>Hinweise  

 Es ist zulässig, mehrere benutzerdefinierte Attribute für denselben Besitzer zu definieren. Sie haben möglicherweise sogar denselben Namen. Es wird jedoch `GetCustomAttributeByName` nur eine Instanz von zurückgegeben. ( `GetCustomAttributeByName` gibt die erste Instanz zurück, die erkannt wird.) Um alle Instanzen eines benutzerdefinierten Attributs zu suchen, müssen Sie die [IMetaDataImport:: enumcustomtribute](imetadataimport-enumcustomattributes-method.md) -Methode aufzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
