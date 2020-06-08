---
title: IMetaDataImport::GetClassLayout-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 36c0ffef2d984604be4ae19899e8f3f912cee123
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491471"
---
# <a name="imetadataimportgetclasslayout-method"></a>IMetaDataImport::GetClassLayout-Methode
Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das TypeDef-Token für die Klasse mit dem Layout, das zurückgegeben werden soll.  
  
 `pdwPackSize`  
 vorgenommen Einer der Werte 1, 2, 4, 8 oder 16, der die Paketgröße der Klasse darstellt.  
  
 `rFieldOffset`  
 vorgenommen Ein Array von [COR_FIELD_OFFSET](cor-field-offset-structure.md) Werten.  
  
 `cMax`  
 [in] Die maximale Größe des `rFieldOffset`-Arrays.  
  
 `pcFieldOffset`  
 vorgenommen Die Anzahl der Elemente, die in zurückgegeben werden `rFieldOffset` .  
  
 `pulClassSize`  
 vorgenommen Die Größe der durch dargestellten Klasse in Bytes `td` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
