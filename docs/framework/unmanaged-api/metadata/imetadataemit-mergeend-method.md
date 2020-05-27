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
ms.openlocfilehash: feb81b86190f953b50f43f244f4e58a0a482f86e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003918"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd-Methode

Führt alle Metadatenbereiche, die von einem oder mehreren vorherigen Aufrufen von [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)angegeben werden, in den aktuellen Bereich zusammen.

## <a name="syntax"></a>Syntax

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>Parameter

Diese Methode nimmt keine Parameter an.

## <a name="remarks"></a>Hinweise

Diese Routine löst die tatsächliche Zusammenführung von Metadaten für alle Import Bereiche aus, die durch vorherige Aufrufe von angegeben `IMetaDataEmit::Merge` werden, in den aktuellen Ausgabebereich.

Die folgenden speziellen Bedingungen gelten für den Merge:

- Ein Modul Versions Bezeichner (MVID) wird nie importiert, da er für die Metadaten im Import Bereich eindeutig ist.

- Keine vorhandenen Modul weiten Eigenschaften werden überschrieben.

  Wenn Modul Eigenschaften bereits für den aktuellen Gültigkeitsbereich festgelegt wurden, werden keine Modul Eigenschaften importiert. Wenn jedoch Modul Eigenschaften im aktuellen Bereich nicht festgelegt wurden, werden Sie nur einmal importiert, wenn Sie zum ersten Mal gefunden werden. Wenn diese Modul Eigenschaften wieder gefunden werden, sind Sie Duplikate. Wenn die Werte aller Modul Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.

- Für Typdefinitionen ( `TypeDef` ) werden keine Duplikate im aktuellen Bereich zusammengeführt. `TypeDef`Objekte werden für jede *voll qualifizierte Objektnamen*-  +  *GUID*-  +  *Versionsnummer*auf Duplikate überprüft. Wenn eine Entsprechung für "Name" oder "GUID" vorliegt und eines der beiden anderen Elemente unterschiedlich ist, wird ein Fehler ausgelöst. Wenn alle drei Elemente übereinstimmen, `MergeEnd` wird von eine kurze Prüfung durchführt, um sicherzustellen, dass es sich bei den Einträgen tatsächlich um Duplikate handelt. andernfalls wird ein Fehler ausgelöst. Diese flüchtige Prüfung sucht nach:

  - Dieselben Member-Deklarationen, die in derselben Reihenfolge auftreten. Member, die als gekennzeichnet sind `mdPrivateScope` (siehe die [CorMethodAttr](cormethodattr-enumeration.md) -Enumeration), werden in dieser Überprüfung nicht berücksichtigt. Sie werden speziell zusammengeführt.

  - Das gleiche Klassen Layout.

  Dies bedeutet, dass ein `TypeDef` -Objekt immer vollständig und konsistent in jedem Metadatenbereich definiert werden muss, in dem es deklariert ist. wenn seine Member-Implementierungen (für eine Klasse) auf mehrere Kompilierungs Einheiten verteilt sind, wird davon ausgegangen, dass die vollständige Definition in jedem Bereich vorhanden und nicht in jedem Bereich inkrementell ist. Wenn z. b. Parameternamen für den Vertrag relevant sind, müssen Sie in jedem Bereich auf dieselbe Weise ausgegeben werden. Wenn Sie nicht relevant sind, sollten Sie nicht in Metadaten ausgegeben werden.

  Die Ausnahme besteht darin, dass für ein- `TypeDef` Objekt inkrementelle Member als gekennzeichnet werden können `mdPrivateScope` . Beim begegnen werden diese `MergeEnd` inkrementell dem aktuellen Bereich hinzugefügt, ohne dass Duplikate berücksichtigt werden. Da der Compiler den privaten Bereich versteht, muss der Compiler für die Erzwingung von Regeln verantwortlich sein.

- Relative virtuelle Adressen (RVAs) werden nicht importiert oder zusammengeführt. der Compiler erwartet, dass diese Informationen erneut ausgegeben werden.

- Benutzerdefinierte Attribute werden nur zusammengeführt, wenn das Element, an das Sie angefügt sind, zusammengeführt wird. Beispielsweise werden benutzerdefinierte Attribute, die einer-Klasse zugeordnet sind, beim ersten Auftreten der-Klasse zusammengeführt. Wenn benutzerdefinierte Attribute einem oder zugeordnet `TypeDef` sind `MemberDef` , das für die Kompilierungseinheit spezifisch ist (z. b. der Zeitstempel eines kompilierten Members), werden Sie nicht zusammengeführt, und der Compiler muss solche Metadaten entfernen oder aktualisieren.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Cor. h

**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.

**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
