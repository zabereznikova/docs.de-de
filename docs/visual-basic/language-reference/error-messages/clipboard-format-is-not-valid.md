---
title: Das Format der Zwischenablage ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586220"
---
# <a name="clipboard-format-is-not-valid"></a>Das Format der Zwischenablage ist ungültig.
Das angegebene Format der Zwischenablage ist nicht kompatibel mit der Methode, die gerade ausgeführt wird. Zu den möglichen Ursachen für diesen Fehler sind:  
  
-   Verwenden der Zwischenablage `GetText` oder `SetText` Methode mit einem Zwischenablageformat außer `vbCFText` oder `vbCFLink`.  
  
-   Verwenden der Zwischenablage `GetData` oder `SetData` Methode mit einem Zwischenablageformat außer `vbCFBitmap`, `vbCFDIB`, oder `vbCFMetafile`.  
  
-   Mithilfe der `DataObject``GetData` Methode oder `SetData` Methode mit einem Zwischenablageformat im Bereich von Microsoft Windows für registrierte Formate (& HC000- & HFFFF reserviert), wenn dieses Format der Zwischenablage wurde noch nicht registriert mit Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das ungültige Format, und geben Sie einen gültigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zwischenablage: Hinzufügen anderer Formate](/cpp/mfc/clipboard-adding-other-formats)
