---
title: ICLRMetadataLocator::GetMetadata-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetadataLocator.GetMetadata
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8758a96464d1465d92fb17314f1e36ab8d9169c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata-Methode
Wird aufgerufen, von der common Language Runtime (CLR) Daten Access Services zum Abrufen der Metadaten eines Bilds.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `imagePath`  
 [in] Eine Zeichenfolge, die den Pfad der Bilddatei angibt.  
  
 `imageTimestamp`  
 [in] Der Zeitstempel der Bilddatei.  
  
 `imageSize`  
 [in] Die Größe der Bilddatei.  
  
 `mvid`  
 [in] Der global eindeutige Bezeichner des Bilds.  
  
 `mdRva`  
 [in] Die relative virtuelle Adresse (RVA) der Metadaten. Die Adresse ist relativ zur Basisadresse Abbilds.  
  
 `flags`  
 [in] Für zukünftige Verwendung reserviert.  
  
 `bufferSize`  
 [in] Die Größe des Puffers, in dem die Metadaten zu platzieren.  
  
 `buffer`  
 [out] Der Puffer, in dem die Metadaten gespeichert werden soll.  
  
 `dataSize`  
 [out] Die Größe der Metadaten, die zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRMetadataLocator-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
