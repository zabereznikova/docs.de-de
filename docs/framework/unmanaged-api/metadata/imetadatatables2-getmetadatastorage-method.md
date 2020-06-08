---
title: IMetaDataTables2::GetMetaDataStorage-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: 55fcde6c47705e515eb2d20f25ac870e257b92c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501130"
---
# <a name="imetadatatables2getmetadatastorage-method"></a>IMetaDataTables2::GetMetaDataStorage-Methode
Ruft die Größe und den Inhalt der Metadaten ab, die im angegebenen Abschnitt gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppvMd`  
 [in, out] Ein Zeiger auf einen Metadatenabschnitt.  
  
 `pcbMd`  
 vorgenommen Die Größe des Metadatenstreams.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
