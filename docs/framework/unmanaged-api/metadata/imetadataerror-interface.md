---
title: IMetaDataError-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 46370da4e61dc90f2386170745da4f95ac7de63b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492771"
---
# <a name="imetadataerror-interface"></a>IMetaDataError-Schnittstelle
Stellt einen Rückrufmechanismus zum Melden von Fehlern während der Metadatenzusammenführung bereit.  
  
> [!NOTE]
> Die `IMetaDataError` Schnittstelle muss vom Client implementiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnError-Methode](imetadataerror-onerror-method.md)|Gibt Benachrichtigungen zu Fehlern, die während der Zusammenführung der Metadaten auftreten.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Metadatenschnittstellen](metadata-interfaces.md)
