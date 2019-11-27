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
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434337"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize-Methode
Ruft die geschätzte binäre Größe der Assembly und ihrer Metadaten im aktuellen Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fSave`  
 in Ein Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe angezeigt werden soll. Nur drei Werte sind gültig: cssexakten, cssQuick und cssverwerdtransientcas:  
  
- cssexact gibt die genaue Speichergröße zurück, dauert aber länger für die Berechnung.  
  
- cssQuick gibt eine Größe zurück, die für die Sicherheit aufgefüllt ist, aber weniger Zeit für die Berechnung benötigt.  
  
- cssverwerdtransientcas weist `GetSaveSize` an, dass Sie verwertbare benutzerdefinierte Attribute verwerfen kann.  
  
 `pdwSaveSize`  
 vorgenommen Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 `GetSaveSize` berechnet den erforderlichen Speicherplatz (in Bytes), um die Assembly und alle zugehörigen Metadaten im aktuellen Bereich zu speichern. (Ein Aufrufe der [IMetaDataEmit:: savedestream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) -Methode würde diese Anzahl von Bytes ausgeben.)  
  
 Wenn der Aufrufer die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Schnittstelle implementiert (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), führt `GetSaveSize` zwei Durchgänge über die Metadaten aus, um ihn zu optimieren und zu komprimieren. Andernfalls werden keine Optimierungen ausgeführt.  
  
 Wenn die Optimierung durchgeführt wird, sortiert der erste Durchlauf einfach die Metadatenstrukturen, um die Leistung von Import Zeit suchen zu optimieren. Dieser Schritt führt in der Regel dazu, dass Datensätze verschoben werden, mit dem Nebeneffekt, dass Token, die vom Tool für zukünftige Verweise aufbewahrt werden, ungültig werden. Die Metadaten informieren den Aufrufer über diese Tokenänderungen erst nach dem zweiten Durchlauf. Im zweiten Durchlauf werden verschiedene Optimierungen ausgeführt, mit denen die Gesamtgröße der Metadaten reduziert werden soll, z. b. die Optimierung von (frühe Bindung) `mdTypeRef` und `mdMemberRef` Tokens, wenn der Verweis auf einen Typ oder Member ist, der im aktuellen Metadatenbereich deklariert ist. In diesem Durchlauf erfolgt eine weitere Runde der Tokenzuordnung. Nach diesem Durchlauf benachrichtigt die metadatenengine den Aufrufer über seine `IMapToken`-Schnittstelle über geänderte Tokenwerte.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
