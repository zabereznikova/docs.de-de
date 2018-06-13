---
title: IMetaDataEmit::MergeEnd-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b794a62a0ac0d253f1431be29b43101816dc7233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449441"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd-Methode
Führt den aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere vorherigen Aufrufe von angegeben [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Diese Methode nimmt keine Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine löst das eigentliche Zusammenführen von Metadaten, importieren Sie alle angegebenen Aufrufe abgrenzen, indem Sie Bereiche `IMetaDataEmit::Merge`, in der aktuellen Ausgabebereich.  
  
 Die folgenden speziellen Bedingungen gelten für die Zusammenführung:  
  
-   Ein Modul Versions-ID (MVID) wird noch nie importiert, da er auf die Metadaten im Importbereich eindeutig ist.  
  
-   Keine vorhandenen Modul gesamten-Eigenschaften werden überschrieben.  
  
     Wenn Moduleigenschaften bereits für den aktuellen Bereich festgelegt wurden, werden keine Moduleigenschaften importiert. Wenn Moduleigenschaften nicht im aktuellen Bereich festgelegt haben, werden sie jedoch importiert nur einmal auf, wenn sie zuerst erkannt werden. Wenn diese Moduleigenschaften erneut auftreten, sind sie Duplikate. Wenn die Werte aller Module-Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.  
  
-   Bei Typdefinitionen (`TypeDef`), also keine Duplikate in den aktuellen Bereich zusammengeführt. `TypeDef` Objekte werden für alle Duplikate überprüft *vollständig qualifizierter Objektname* + *GUID* + *Versionsnummer*. Wenn eine auf Namen oder die GUID Übereinstimmung und keines der anderen beiden Elemente unterscheidet, wird ein Fehler ausgelöst. Andernfalls, wenn alle drei Elemente übereinstimmen, `MergeEnd` ist eine kurze Überprüfung, um sicherzustellen, dass die Einträge in der Tat Duplikate; Wenn nicht, wird ein Fehler ausgelöst. Diese kurze Überprüfung gesucht wird:  
  
    -   Die gleichen Memberdeklarationen, die in der gleichen Reihenfolge auftreten. Elemente, die als gekennzeichneten `mdPrivateScope` (finden Sie unter der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration) sind nicht in diese namensüberprüfung enthalten sie speziell zusammengeführt werden.  
  
    -   Die gleiche Klassenlayout.  
  
     Dies bedeutet, dass ein `TypeDef` Objekt muss immer vollständig und konsistent definiert werden in jedem Metadatenbereich in der sie deklariert wird, wenn mehrere Kompilierungseinheiten seine Memberimplementierungen (für eine Klasse) verteilt sind, die vollständige Definition wird davon ausgegangen, dass sein in jedem Bereich vorhanden und nicht inkrementelle für jeden Bereich. Z. B. wenn Parameternamen für den Vertrag relevant sind, müssen sie die gleiche Weise wie in jedem Bereich ausgegeben werden. Wenn sie nicht relevant sind, sollten sie nicht in Metadaten ausgegeben.  
  
     Die Ausnahme ist, dass eine `TypeDef` Objekt kann als inkrementelle Member haben `mdPrivateScope`. Bei diesen `MergeEnd` inkrementell auf den aktuellen Bereich ohne Berücksichtigung von Duplikaten hinzugefügt. Da der Compiler den privaten Bereich versteht, muss der Compiler verantwortlich zum Erzwingen von Regeln.  
  
-   Relative virtuelle Adresse (RVA) werden nicht importiert oder zusammengeführt werden; der Compiler muss diese Informationen erneut ausgeben.  
  
-   Benutzerdefinierte Attribute werden zusammengeführt, nur, wenn das Element mit dem sie verbunden sind zusammengeführt wird. Benutzerdefinierte Attribute einer Klasse zugeordnet werden z. B. zusammengeführt, beim ersten der Klasse auftreten. Wenn Sie benutzerdefinierte Attribute zugeordnet sind ein `TypeDef` oder `MemberDef` , der Kompilierungseinheit (z. B. den Zeitstempel, der eine Memberkompilierung) spezifisch ist, werden nicht zusammengeführt, und es liegt im Ermessen des Compilers solche Metadaten entfernen oder aktualisieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
