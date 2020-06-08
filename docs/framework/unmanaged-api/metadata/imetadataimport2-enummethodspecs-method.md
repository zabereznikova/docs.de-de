---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 8f6fbc570e7ea85aca5b365611d58a1700fb27cd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490717"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs-Methode
Ruft einen Enumerator für ein Array von MethodSpec-Token ab, das mit dem angegebenen MethodDef-oder mitgliedsverweistoken verknüpft ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs` .  
  
 `tk`  
 in Das mitgliedsverweis-oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgelistet werden sollen. Wenn der Wert von `tk` 0 (null) ist, werden alle MethodSpec-Token im Bereich aufgelistet.  
  
 `rMethodSpecs`  
 vorgenommen Das Array von MethodSpec-Token, das aufgelistet werden soll.  
  
 `cMax`  
 in Die angeforderte maximale Anzahl von Token, die in platziert werden sollen `rMethodSpecs` .  
  
 `pcMethodSpecs`  
 vorgenommen Die zurückgegebene Anzahl von Token, die in platziert werden `rMethodSpecs` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|`phEnum`hat keine Member-Elemente. In diesem Fall `pcMethodSpecs` wird auf 0 (null) festgelegt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
