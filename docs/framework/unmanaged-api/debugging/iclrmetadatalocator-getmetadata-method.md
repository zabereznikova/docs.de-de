---
title: ICLRMetadataLocator::GetMetadata-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: 66b3934d000b4f000c368acb1f57c8fc82a5c453
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793623"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata-Methode
Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um die Metadaten eines Bilds abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameters  
 `imagePath`  
 in Eine Zeichenfolge, die den Pfad der Bilddatei angibt.  
  
 `imageTimestamp`  
 in Der Zeitstempel der Bilddatei.  
  
 `imageSize`  
 in Die Größe der Bilddatei.  
  
 `mvid`  
 in Die Globally Unique Identifier des Bilds.  
  
 `mdRva`  
 in Die relative virtuelle Adresse (RVA) der Metadaten. Die Adresse ist relativ zur Basisadresse des Images.  
  
 `flags`  
 in Reserviert für zukünftige Verwendung.  
  
 `bufferSize`  
 in Die Größe des Puffers, in dem die Metadaten platziert werden sollen.  
  
 `buffer`  
 vorgenommen Der Puffer, in den die Metadaten platziert werden sollen.  
  
 `dataSize`  
 vorgenommen Die Größe der Metadaten, die zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetadataLocator-Schnittstelle](iclrmetadatalocator-interface.md)
