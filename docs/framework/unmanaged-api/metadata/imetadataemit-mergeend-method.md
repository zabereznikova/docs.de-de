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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448038"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd-Methode

Führt alle Metadatenbereiche, die von einem oder mehreren vorherigen Aufrufen von [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)angegeben werden, in den aktuellen Bereich zusammen.

## <a name="syntax"></a>Syntax

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>Parameter

Diese Methode nimmt keine Parameter an.

## <a name="remarks"></a>Hinweise

Diese Routine löst die tatsächliche Zusammenführung von Metadaten für alle Import Bereiche aus, die durch vorherige Aufrufe von `IMetaDataEmit::Merge`angegeben sind, in den aktuellen Ausgabebereich.

Die folgenden speziellen Bedingungen gelten für den Merge:

- Ein Modul Versions Bezeichner (MVID) wird nie importiert, da er für die Metadaten im Import Bereich eindeutig ist.

- Keine vorhandenen Modul weiten Eigenschaften werden überschrieben.

  Wenn Modul Eigenschaften bereits für den aktuellen Gültigkeitsbereich festgelegt wurden, werden keine Modul Eigenschaften importiert. Wenn jedoch Modul Eigenschaften im aktuellen Bereich nicht festgelegt wurden, werden Sie nur einmal importiert, wenn Sie zum ersten Mal gefunden werden. Wenn diese Modul Eigenschaften wieder gefunden werden, sind Sie Duplikate. Wenn die Werte aller Modul Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.

- Für Typdefinitionen (`TypeDef`) werden keine Duplikate im aktuellen Bereich zusammengeführt. `TypeDef` Objekte werden für jeden *voll qualifizierten Objektnamen* + *GUID* + *Versionsnummer*auf Duplikate überprüft. Wenn eine Entsprechung für "Name" oder "GUID" vorliegt und eines der beiden anderen Elemente unterschiedlich ist, wird ein Fehler ausgelöst. Wenn alle drei Elemente übereinstimmen, führt `MergeEnd` eine kurze Prüfung durch, um sicherzustellen, dass es sich bei den Einträgen tatsächlich um Duplikate handelt. Andernfalls wird ein Fehler ausgelöst. Diese flüchtige Prüfung sucht nach:

  - Dieselben Member-Deklarationen, die in derselben Reihenfolge auftreten. Member, die als `mdPrivateScope` gekennzeichnet sind (siehe die [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration), sind in dieser Überprüfung nicht enthalten. Sie werden speziell zusammengeführt.

  - Das gleiche Klassen Layout.

  Dies bedeutet, dass ein `TypeDef` Objekt immer vollständig und konsistent in jedem Metadatenbereich definiert werden muss, in dem es deklariert ist. Wenn seine Member-Implementierungen (für eine Klasse) auf mehrere Kompilierungs Einheiten verteilt sind, wird davon ausgegangen, dass die vollständige Definition in jedem Bereich vorhanden und nicht in jedem Bereich inkrementell ist. Wenn z. b. Parameternamen für den Vertrag relevant sind, müssen Sie in jedem Bereich auf dieselbe Weise ausgegeben werden. Wenn Sie nicht relevant sind, sollten Sie nicht in Metadaten ausgegeben werden.

  Eine Ausnahme besteht darin, dass für ein `TypeDef` Objekt inkrementelle Member als `mdPrivateScope`gekennzeichnet werden können. Beim begegnen werden `MergeEnd` inkrementell dem aktuellen Gültigkeitsbereich hinzugefügt, ohne dass Duplikate berücksichtigt werden. Da der Compiler den privaten Bereich versteht, muss der Compiler für die Erzwingung von Regeln verantwortlich sein.

- Relative virtuelle Adressen (RVAs) werden nicht importiert oder zusammengeführt. der Compiler erwartet, dass diese Informationen erneut ausgegeben werden.

- Benutzerdefinierte Attribute werden nur zusammengeführt, wenn das Element, an das Sie angefügt sind, zusammengeführt wird. Beispielsweise werden benutzerdefinierte Attribute, die einer-Klasse zugeordnet sind, beim ersten Auftreten der-Klasse zusammengeführt. Wenn benutzerdefinierte Attribute einer `TypeDef` oder `MemberDef` zugeordnet sind, die spezifisch für die Kompilierungseinheit ist (z. b. der Zeitstempel eines kompilierten Members), werden Sie nicht zusammengeführt, und der Compiler muss solche Metadaten entfernen oder aktualisieren.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Cor. h

**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.

**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
