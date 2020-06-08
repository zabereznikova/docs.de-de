---
title: IMetaDataFilter-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503782"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter-Schnittstelle
Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[IsTokenMarked-Methode](imetadatafilter-istokenmarked-method.md)|Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.|  
|[MarkToken-Methode](imetadatafilter-marktoken-method.md)|Legt einen Wert fest, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.|  
|[UnmarkAll-Methode](imetadatafilter-unmarkall-method.md)|Entfernt die Verarbeitungs Markierungen aus allen Token im aktuellen Metadatenbereich.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Metadatenschnittstellen](metadata-interfaces.md)
