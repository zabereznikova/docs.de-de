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
ms.openlocfilehash: 775b3919d1468f26fc3c374dd8ca143aa17853ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708737"
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
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
