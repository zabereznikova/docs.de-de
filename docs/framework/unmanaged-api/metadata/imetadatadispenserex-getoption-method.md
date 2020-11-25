---
title: IMetaDataDispenserEx::GetOption-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 0ceadf42ac49fd3fc89c78a6a26b2f529afeeaf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700560"
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption-Methode

Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `optionId`  
 in Ein Zeiger auf eine GUID, die die abzurufende Option angibt. Eine Liste der unterstützten GUIDs finden Sie im Abschnitt "Hinweise".  
  
 `pValue`  
 vorgenommen Der Wert der zurückgegebenen Option. Der Typ dieses Werts ist eine Variante des Typs der angegebenen Option.  
  
## <a name="remarks"></a>Hinweise  

 In der folgenden Liste werden die GUIDs angezeigt, die für diese Methode unterstützt werden. Beschreibungen finden Sie unter der [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) -Methode. Wenn `optionId` nicht in dieser Liste enthalten ist, gibt diese Methode HRESULT zurück `E_INVALIDARG` , wodurch ein falscher Parameter angegeben wird.  
  
- MetaDataCheckDuplicatesFor  
  
- MetaDataRefToDefCheck  
  
- MetaDataNotificationForTokenMovement  
  
- MetaDataSetENC  
  
- MetaDataErrorIfEmitOutOfOrder  
  
- MetaDataGenerateTCEAdapters  
  
- MetaDataLinkerOptions  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
