---
title: 'Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: b53513ef0b373cdde7703eddcd182ab7fd15cb9b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706620"
---
# <a name="how-to-write-characters-to-a-string"></a>Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge
In den folgenden Codebeispielen werden Zeichen synchron oder asynchron aus einem Zeichenarray in eine Zeichenfolge geschrieben.  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a>Beispiel: Synchrones Schreiben von Zeichen in einer Konsolen-App  
 In dem folgenden Beispiel wird ein <xref:System.IO.StringWriter> verwendet, um fünf Zeichen synchron in ein <xref:System.Text.StringBuilder>-Objekt zu schreiben. 
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a>Beispiel: Asynchrones Schreiben von Zeichen in einer WPF-App 
 Im nächsten Beispiel wird der Code hinter einer WPF-App gezeigt. Beim Laden des Fensters werden in diesem Beispiel alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert. Dann wird jeder Buchstabe bzw. jedes Leerzeichen asynchron in eine separate Zeile in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement geschrieben.  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)  
- [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Vorgehensweise: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Vorgehensweise: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Vorgehensweise: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
