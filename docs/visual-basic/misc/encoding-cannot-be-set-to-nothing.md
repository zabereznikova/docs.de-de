---
title: Die Codierung kann nicht auf 'Nothing' festgelegt werden
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 41565d1aa3b69f6ad92d4bbf2b2f2170014aef87
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394478"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Die Codierung kann nicht auf 'Nothing' festgelegt werden
Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.  
  
 <xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll. Der Standardwert ist UTF-8.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Geben Sie einen gültigen Wert für den `encoding` -Parameter an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Dateicodierungen](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [Lesen aus Dateien](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Schreiben in Dateien](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. Computer. File System. Read alltext](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. Computer. File System. Write-alltext](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
