---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301320"
---
# <a name="file-already-open"></a>Die Datei ist bereits geöffnet.
Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
-   Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.  
  
-   Eine Anweisung verweist auf eine geöffnete Datei.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Schließen Sie die Datei, bevor die Anweisung ausgeführt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
