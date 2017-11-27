---
title: IMetaDataDispenserEx::GetOption-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa9db222c81c2d6536b782c3e047e24c773bd018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption-Methode
Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `optionId`  
 [in] Ein Zeiger auf eine GUID fest, der angibt, die Option abgerufen werden sollen. Finden Sie im Abschnitt "Hinweise" eine Liste der unterstützten GUIDs.  
  
 `pValue`  
 [out] Der Wert der Option "zurückgegebenen". Der Typ dieses Werts wird eine Variante des Typs für die angegebene Option sein.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Liste enthält die GUIDs, die für diese Methode unterstützt werden. Beschreibungen finden Sie die [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) Methode. Wenn `optionId` ist nicht in dieser Liste, gibt diese Methode HRESULT `E_INVALIDARG`, einen falschen Parameter angibt.  
  
-   MetaDataCheckDuplicatesFor  
  
-   MetaDataRefToDefCheck  
  
-   MetaDataNotificationForTokenMovement  
  
-   MetaDataSetENC  
  
-   MetaDataErrorIfEmitOutOfOrder  
  
-   MetaDataGenerateTCEAdapters  
  
-   MetaDataLinkerOptions  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
