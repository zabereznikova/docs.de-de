---
title: IMetaDataTables::GetBlobHeapSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: e508bcae15e72ce592529cf4b68af5d75ea49038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721958"
---
# <a name="imetadatatablesgetblobheapsize-method"></a>IMetaDataTables::GetBlobHeapSize-Methode

Ruft die Größe des Binary Large Object (BLOB)-Heaps in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a>Parameter  

 `pcbBlobs`  
 vorgenommen Ein Zeiger auf die Größe des BLOB-Heaps in Bytes.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
