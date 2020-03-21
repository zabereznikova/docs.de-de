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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177716"
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption-Methode
Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Die Option steuert, wie Aufrufe des aktuellen Metadatenbereichs verarbeitet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `optionId`  
 [in] Ein Zeiger auf eine GUID, der die abzudannende Option angibt. Eine Liste der unterstützten GUIDs finden Sie im Abschnitt "Hinweise".  
  
 `pValue`  
 [out] Der Wert der zurückgegebenen Option. Der Typ dieses Werts ist eine Variante des Typs der angegebenen Option.  
  
## <a name="remarks"></a>Bemerkungen  
 Die folgende Liste zeigt die GUIDs, die für diese Methode unterstützt werden. Beschreibungen finden Sie in der [IMetaDataDispenserEx::SetOption-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) Wenn `optionId` dies nicht in dieser Liste `E_INVALIDARG`enthalten ist, gibt diese Methode HRESULT zurück, was auf einen falschen Parameter hinweist.  
  
- MetaDataCheckDuplicatesFor  
  
- MetaDataRefToDefCheck  
  
- MetaDataNotificationForTokenMovement  
  
- MetaDataSetENC  
  
- MetaDataErrorIfEmitOutOfOrder  
  
- MetaDataGenerateTCEAdapter  
  
- MetaDataLinkerOptionen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
