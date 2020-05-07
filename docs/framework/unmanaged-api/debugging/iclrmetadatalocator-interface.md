---
title: ICLRMetadataLocator-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859718"
---
# <a name="iclrmetadatalocator-interface"></a>ICLRMetadataLocator-Schnittstelle
Wird von der Ebene der Datenzugriffs Dienste verwendet, um Metadaten von Assemblys in einem Ziel Prozess zu suchen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetMetadata-Methode](iclrmetadatalocator-getmetadata-method.md)|Ruft die Metadaten eines Bilds aus dem Ziel Prozess ab.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren. Beispielsweise unterscheidet sich die Implementierung für einen Live Prozess von der eines Speicher Abbilds.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Debugschnittstellen](debugging-interfaces.md)
