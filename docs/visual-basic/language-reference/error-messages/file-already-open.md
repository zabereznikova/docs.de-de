---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874177"
---
# <a name="file-already-open"></a>Die Datei ist bereits geöffnet.

Manchmal muss eine Datei geschlossen werden, bevor ein anderer `FileOpen` oder ein anderer Vorgang ausgeführt werden kann. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- `FileOpen`Für eine Datei, die bereits geöffnet ist, wurde ein sequenzieller Ausgabemodus ausgeführt.  
  
- Eine-Anweisung verweist auf eine geöffnete Datei.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Schließen Sie die Datei, bevor Sie die Anweisung ausführen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
