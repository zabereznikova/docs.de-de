---
title: IMetaDataValidate::ValidatorInit-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708555"
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit-Methode

Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Überprüfungsfehler.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwModule`  
 in Ein Wert der [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.  
  
 `pUnk`  
 in Ein Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Instanz, die als Funktions Rückruf für Validierungs Fehler fungiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataValidate-Schnittstelle](imetadatavalidate-interface.md)
