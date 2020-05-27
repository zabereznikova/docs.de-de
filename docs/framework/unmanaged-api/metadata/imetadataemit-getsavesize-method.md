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
ms.openlocfilehash: 22c0a317777a12294ba7a90f7af1ceeca3ad0a47
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009261"
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
 in Ein Wert der [CorSaveSize](corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe angezeigt werden soll. Nur drei Werte sind gültig: cssexakten, cssQuick und cssverwerdtransientcas:  
  
- cssexact gibt die genaue Speichergröße zurück, dauert aber länger für die Berechnung.  
  
- cssQuick gibt eine Größe zurück, die für die Sicherheit aufgefüllt ist, aber weniger Zeit für die Berechnung benötigt.  
  
- cssverwerfen dtransientcas weist `GetSaveSize` darauf hin, dass Sie verwertbare benutzerdefinierte Attribute verwerfen kann.  
  
 `pdwSaveSize`  
 vorgenommen Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 `GetSaveSize`berechnet den erforderlichen Speicherplatz in Bytes, um die Assembly und alle zugehörigen Metadaten im aktuellen Bereich zu speichern. (Ein Aufrufe der [IMetaDataEmit:: savedestream](imetadataemit-savetostream-method.md) -Methode würde diese Anzahl von Bytes ausgeben.)  
  
 Wenn der Aufrufer die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Schnittstelle (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)) implementiert, führt `GetSaveSize` zwei durch übergebenen Metadaten aus, um die Metadaten zu optimieren und zu komprimieren. Andernfalls werden keine Optimierungen ausgeführt.  
  
 Wenn die Optimierung durchgeführt wird, sortiert der erste Durchlauf einfach die Metadatenstrukturen, um die Leistung von Import Zeit suchen zu optimieren. Dieser Schritt führt in der Regel dazu, dass Datensätze verschoben werden, mit dem Nebeneffekt, dass Token, die vom Tool für zukünftige Verweise aufbewahrt werden, ungültig werden. Die Metadaten informieren den Aufrufer über diese Tokenänderungen erst nach dem zweiten Durchlauf. Im zweiten Durchlauf werden verschiedene Optimierungen ausgeführt, mit denen die Gesamtgröße der Metadaten reduziert werden soll, z. b. die Optimierung (frühe Bindung) `mdTypeRef` und `mdMemberRef` Token, wenn der Verweis auf einen Typ oder Member fest steht, der im aktuellen Metadatenbereich deklariert ist. In diesem Durchlauf erfolgt eine weitere Runde der Tokenzuordnung. Nach diesem Durchlauf benachrichtigt die metadatenengine den Aufrufer über seine- `IMapToken` Schnittstelle über geänderte Tokenwerte.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
