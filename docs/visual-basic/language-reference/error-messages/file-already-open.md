---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162751"
---
# <a name="file-already-open"></a>Die Datei ist bereits geöffnet.

Manchmal muss eine Datei geschlossen werden, bevor ein anderer `FileOpen` oder ein anderer Vorgang ausgeführt werden kann. Zu den möglichen Ursachen für diesen Fehler gehören:

- `FileOpen`Für eine Datei, die bereits geöffnet ist, wurde ein sequenzieller Ausgabemodus ausgeführt.

- Eine-Anweisung verweist auf eine geöffnete Datei.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Schließen Sie die Datei, bevor Sie die Anweisung ausführen.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
