---
title: Das Format der Zwischenablage ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649867"
---
# <a name="clipboard-format-is-not-valid"></a>Das Format der Zwischenablage ist ungültig.
Das angegebene Zwischenablageformat ist nicht kompatibel mit der Methode ausgeführt wird. Zu den möglichen Ursachen für diesen Fehler sind:  
  
- Verwenden der Zwischenablage des `GetText` oder `SetText` -Methode mit einem anderen Zwischenablageformat als `vbCFText` oder `vbCFLink`.  
  
- Verwenden der Zwischenablage des `GetData` oder `SetData` -Methode mit einem anderen Zwischenablageformat als `vbCFBitmap`, `vbCFDIB`, oder `vbCFMetafile`.  
  
- Mithilfe der `GetData` oder `SetData` Methoden eine `DataObject` mit einem Zwischenablageformat, in dem Bereich von Microsoft Windows für registrierte Formate (& HC000- & HFFFF reserviert), wenn dieses Format der Zwischenablage wurde nicht registriert mit Microsoft Windows .  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie das ungültige Format, und geben Sie eine gültige Verbindungszeichenfolge an.  
  
## <a name="see-also"></a>Siehe auch

- [Zwischenablage: Hinzufügen anderer Formate](/cpp/mfc/clipboard-adding-other-formats)
