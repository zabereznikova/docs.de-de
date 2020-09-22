---
title: Das Format der Zwischenablage ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874593"
---
# <a name="clipboard-format-is-not-valid"></a>Das Format der Zwischenablage ist ungültig.

Das angegebene Zwischenablage Format ist mit der ausgeführten Methode nicht kompatibel. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Verwenden der-oder-Methode der Zwischenablage `GetText` `SetText` mit einem anderen Zwischenablage Format als `vbCFText` oder `vbCFLink` .  
  
- Verwenden der-oder-Methode der Zwischenablage `GetData` `SetData` mit einem anderen Zwischenablage Format als `vbCFBitmap` , `vbCFDIB` oder `vbCFMetafile` .  
  
- Verwenden der `GetData` - `SetData` Methode oder der-Methode eines `DataObject` mit einem Zwischenablage Format in dem von Microsoft Windows reservierten Bereich für registrierte Formate (&HC000-&HFFFF), wenn dieses Zwischenablage Format nicht bei Microsoft Windows registriert wurde.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie das ungültige Format, und geben Sie ein gültiges Format an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zwischenablage: Hinzufügen anderer Formate](/cpp/mfc/clipboard-adding-other-formats)
