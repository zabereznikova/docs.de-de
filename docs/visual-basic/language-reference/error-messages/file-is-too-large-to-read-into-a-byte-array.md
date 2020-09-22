---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 89459aaf766a70f69008f847dda7ac6e2a1e41d1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874183"
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
