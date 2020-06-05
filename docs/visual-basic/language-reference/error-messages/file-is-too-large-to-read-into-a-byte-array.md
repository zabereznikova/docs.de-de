---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: b81fc9332d5f1347404fcdd73bce72b6b09778b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363123"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Die Datei ist zu groß, um in ein Bytearray geladen zu werden
Die Größe der Datei, die Sie in ein Bytearray einlesen möchten, überschreitet 4 GB. Die- `My.Computer.FileSystem.ReadAllBytes` Methode kann eine Datei nicht lesen, die diese Größe überschreitet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden <xref:System.IO.StreamReader> Sie, um die Datei zu lesen. Weitere Informationen finden Sie unter [Grundlagen der .NET Framework Datei-e/a und des Dateisystems (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Dateizugriff mit Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Vorgehensweise: Lesen von Text aus Dateien mit StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
