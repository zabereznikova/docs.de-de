---
title: IMetaDataTables2::GetMetaDataStreamInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 21fc79f62dba4b16a7a067dff8fb9dcc795c9d35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708724"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>IMetaDataTables2::GetMetaDataStreamInfo-Methode

Ruft den Namen, die Größe und den Inhalt des Metadatenstreams am angegebenen Index ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ix`  
 in Der Index des angeforderten Metadatenstreams.  
  
 `ppchName`  
 vorgenommen Ein Zeiger auf den Namen des Streams.  
  
 `ppv`  
 vorgenommen Ein Zeiger auf den Metadatenstream.  
  
 `pcb`  
 vorgenommen Die Größe von in Bytes `ppv` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
