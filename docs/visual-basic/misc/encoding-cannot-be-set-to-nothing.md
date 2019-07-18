---
title: Die Codierung kann nicht auf 'Nothing' festgelegt werden
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 492db7755e8b2b75ea8c60d7f4e1ccc1a5ded865
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598351"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Die Codierung kann nicht auf 'Nothing' festgelegt werden
Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.  
  
 <xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll. Der Standardwert ist UTF-8.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Geben Sie einen gültigen Wert für den `encoding` -Parameter an.  
  
## <a name="see-also"></a>Siehe auch

- [Dateicodierungen](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [Lesen aus Dateien](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Schreiben in Dateien](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
