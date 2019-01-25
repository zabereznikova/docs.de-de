---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567034"
---
# <a name="file-already-open"></a>Die Datei ist bereits geöffnet.
Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
-   Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.  
  
-   Eine Anweisung verweist auf eine geöffnete Datei.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Schließen Sie die Datei, bevor die Anweisung ausgeführt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
