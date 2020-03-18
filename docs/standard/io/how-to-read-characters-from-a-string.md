---
title: 'Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
ms.openlocfilehash: ed267ad62e46f6216c94906df1bcefb0684ab51b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155762"
---
# <a name="how-to-read-characters-from-a-string"></a>Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge
In den folgenden Codebeispielen wird das synchrone und asynchrone Lesen von Zeichen aus einer Zeichenfolge veranschaulicht.  
  
## <a name="example-read-characters-synchronously"></a>Beispiel: Synchrones Lesen von Zeichen
 In diesem Beispiel werden 13 Zeichen synchron aus einer Zeichenfolge gelesen, in einem Array gespeichert und angezeigt. Anschließend werden in dem Beispiel die restlichen Zeichen in der Zeichenfolge gelesen und im Array beginnend mit dem sechsten Element gespeichert. Dann wird der Inhalt des Arrays angezeigt.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>Beispiel: Asynchrones Lesen von Zeichen  
 Im nächsten Beispiel wird der Code hinter einer WPF-App gezeigt. Beim Laden des Fensters werden in diesem Beispiel alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert. Dann wird jeder Buchstabe bzw. jedes Leerzeichen asynchron in eine separate Zeile in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement geschrieben.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [How to: Erstellen einer Verzeichnisauflistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [How to: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [How to: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [How to: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [How to: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
