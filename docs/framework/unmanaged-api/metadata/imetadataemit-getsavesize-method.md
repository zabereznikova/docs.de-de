---
title: IMetaDataEmit::GetSaveSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7585f6adbca97b252fdad90276b0cd422d32c04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize-Methode
Ruft die geschätzte binäre Größe der Assembly und die zugehörigen Metadaten im aktuellen Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fSave`  
 [in] Der Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe abgerufen werden soll. Nur drei Werte sind gültig: CssAccurate, CssQuick und CssDiscardTransientCAs:  
  
-   CssAccurate gibt die genaue Größe dauert jedoch länger zu berechnen.  
  
-   CssQuick gibt eine Größe aus, aus Sicherheitsgründen aufgefüllt, jedoch weniger Zeit zum Berechnen.  
  
-   CssDiscardTransientCAs teilt `GetSaveSize` , entfernbare benutzerdefinierte Attribute ausgelöst werden können.  
  
 `pdwSaveSize`  
 [out] Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 `GetSaveSize`berechnet den Speicherplatz in Bytes, der zum Speichern von der Assembly und alle zugehörigen Metadaten im aktuellen Bereich erforderlich. (Ein Aufruf der [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) Methode würde diese Anzahl von Bytes ausgegeben.)  
  
 Wenn der Aufrufer implementiert die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` zwei Durchläufen über die Metadaten zu optimieren und komprimieren. Andernfalls werden keine Optimierungen durchgeführt.  
  
 Optimierung durchgeführt wird, sortiert die erste Übergabe einfach die Systemmetadaten-Strukturen, um die Leistung des Imports Suchvorgänge zu optimieren. Dieser Schritt führt in der Regel bei der Umstellung von Datensätzen mit dem Nebeneffekt, dass der Token, die vom Tool für die zukünftige Verwendung beibehalten für ungültig erklärt werden. Die Metadaten informiert den Aufrufer diese token Änderungen erst nach dem zweiten Schritt jedoch nicht. Im zweiten Schritt werden verschiedene Optimierungen durchgeführt, die auf die Gesamtgröße der Metadaten, z. B. Optimierung (frühes Binden) zu reduzieren `mdTypeRef` und `mdMemberRef` Token, wenn der Verweis auf einen Typ oder Member, die in deklariert wird die aktuellen Metadatenbereich. In diesem Durchgang tritt auf, eine neue Reihe von token Zuordnung. Nach diesem Durchlauf benachrichtigt das Metadatenmodul für die den Aufrufer über seine `IMapToken` Schnittstelle, eines beliebigen token Werte geändert haben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
