---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 8ec878e04b0128c997c5be51d2c714d55abcde8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665121"
---
# <a name="file-already-open"></a>Die Datei ist bereits geöffnet.
Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann. Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.  
  
- Eine Anweisung verweist auf eine geöffnete Datei.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Schließen Sie die Datei, bevor die Anweisung ausgeführt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
