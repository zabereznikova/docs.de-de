---
title: IMetaDataEmit::GetSaveSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 164cdc5c04a55e9c33dda51e10dfb37f38ec1b6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746543"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize-Methode
Ruft die binäre geschätzte Größe der Assembly und die Metadaten im aktuellen Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fSave`  
 [in] Der Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe erhalten soll. Nur drei Werte sind gültig: CssAccurate, CssQuick und CssDiscardTransientCAs:  
  
-   CssAccurate gibt die genaue Größe dauert jedoch länger zu berechnen.  
  
-   CssQuick gibt eine Größe aus, aus Sicherheitsgründen aufgefüllt, jedoch weniger Zeit zum Berechnen.  
  
-   CssDiscardTransientCAs teilt `GetSaveSize` , entfernbare benutzerdefinierte Attribute ausgelöst werden können.  
  
 `pdwSaveSize`  
 [out] Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 `GetSaveSize` berechnet den Speicherplatz in Bytes, der zum Speichern von der Assembly und alle seine Metadaten im aktuellen Bereich erforderlich. (Ein Aufruf der [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) Methode würde diese Anzahl von Bytes ausgegeben.)  
  
 Wenn der Aufrufer implementiert die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` führt zwei Durchläufe über die Metadaten zum Optimieren und zu komprimieren. Andernfalls werden keine Optimierungen durchgeführt.  
  
 Wenn die Optimierung ausgeführt wird, sortiert im ersten Durchlauf einfach die Systemmetadaten-Strukturen, um die Leistung der Imports Suchvorgänge zu optimieren. Dieser Schritt führt in der Regel bei der Umstellung von Datensätzen, mit dem Nebeneffekt, dass Token vom Tool für die zukünftige Verwendung beibehalten ungültig gemacht werden. Die Metadaten informiert den Aufrufer diese token Änderungen erst nach dem im zweiten Durchlauf jedoch nicht. Im zweiten Durchlauf, zahlreiche Optimierungen durchgeführt, die die Gesamtgröße der Metadaten, z. B. Optimierung (frühes Binden) zu reduzieren vorgesehen sind `mdTypeRef` und `mdMemberRef` Token, wenn der Verweis auf einen Typ oder Member, der in deklariert wird die aktuellen Metadatenbereich. In diesem Schritt tritt auf, eine weitere runde der token-Zuordnung. Nach diesem Durchlauf der Metadaten-Engine benachrichtigt den Aufrufer über die `IMapToken` -Schnittstelle über token Werte geändert haben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
