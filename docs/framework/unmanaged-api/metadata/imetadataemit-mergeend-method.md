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
ms.openlocfilehash: b4e3045476fc68dbeb545b7394b373be4ff881c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584276"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd-Methode
Merges im aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere früheren aufrufen angegeben [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a>Parameter  
 Diese Methode akzeptiert keine Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine wird ausgelöst, das tatsächliche Zusammenführen der Metadaten, importieren Sie alle Aufrufe von abgrenzen, indem Sie angegebenen Bereiche `IMetaDataEmit::Merge`, in den aktuellen Ausgabebereich.  
  
 Die folgenden speziellen Bedingungen gelten für die Zusammenführung:  
  
- Ein Modul Versions-ID (MVID) ist noch nie importiert, da er auf die Metadaten im Importbereich eindeutig ist.  
  
- Keine vorhandenen Modul-Wide-Eigenschaften werden überschrieben.  
  
     Wenn die Moduleigenschaften für den aktuellen Bereich bereits festgelegt wurden, werden keine Eigenschaften des Moduls importiert. Wenn die Moduleigenschaften im aktuellen Bereich nicht festgelegt wurden, werden sie jedoch importiert nur einmal auf, wenn sie zuerst erkannt werden. Die Moduleigenschaften erneut auftreten, werden Duplikate. Wenn die Werte aller Eigenschaften des Moduls (mit Ausnahme der MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.  
  
- Für Typdefinitionen (`TypeDef`), keine Duplikate in den aktuellen Bereich zusammengeführt werden. `TypeDef` Objekte mit jeweils auf Duplikate überprüft werden *vollständig qualifizierter Objektname* + *GUID* + *Versionsnummer*. Wenn eine Übereinstimmung auf Namen oder GUID vorhanden ist und keines der anderen beiden Elemente unterscheidet, wird ein Fehler ausgelöst. Wenn alle drei Elemente übereinstimmen, andernfalls `MergeEnd` ist eine oberflächliche, um sicherzustellen, dass die Einträge sind in der Tat Duplikate; Falls nicht, wird ein Fehler ausgelöst. Diese kurze Überprüfung sucht nach:  
  
    - Die gleichen Memberdeklarationen, die in der gleichen Reihenfolge auftreten. Elemente, die als gekennzeichnet sind `mdPrivateScope` (finden Sie unter den [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration) befinden sich nicht bei dieser Überprüfung; sie speziell zusammengeführt werden.  
  
    - Das Klassenlayout für dieselbe.  
  
     Dies bedeutet, dass eine `TypeDef` Objekt muss immer vollständig und konsistent definiert werden in jedem Metadatenbereich in dem sie deklariert wird, wenn die Implementierungen von Membern (für eine Klasse) über mehrere Kompilierungseinheiten hinweg verteilt sind, die vollständige Definition wird als in jedem Bereich vorhanden und können mit jeder Bereich nicht inkrementell. Z. B. wenn Parameternamen für den Vertrag relevant sind, müssen sie die gleiche Weise wie in jedem Bereich ausgegeben werden; Wenn sie nicht relevant sind, sollten sie nicht in Metadaten ausgegeben werden.  
  
     Die Ausnahme ist, dass eine `TypeDef` Objekt kann inkrementelle als Mitglieder haben `mdPrivateScope`. Bei diesen `MergeEnd` inkrementell auf den aktuellen Bereich ohne Berücksichtigung von Duplikaten hinzugefügt. Da der Compiler den privaten Bereich versteht, muss der Compiler zum Erzwingen von Regeln verantwortlich sein.  
  
- Relative virtuelle Adresse (RVA) werden nicht importiert oder zusammengeführt; der Compiler muss diese Informationen erneut ausgeben.  
  
- Benutzerdefinierte Attribute werden zusammengeführt, nur, wenn das Element, mit dem sie verbunden sind, zusammengeführt wird. Beispielsweise werden benutzerdefinierte Attribute einer Klasse zusammengeführt, wenn die Klasse zuerst erreicht wird. Wenn Sie benutzerdefinierte Attribute zugewiesen sind eine `TypeDef` oder `MemberDef` , der die Kompilierungseinheit (z. B. der Zeitstempel, der eine Memberkompilierung) spezifisch ist, werden sie nicht zusammengeführt, und es obliegt des Compilers solche Metadaten entfernen oder aktualisieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
