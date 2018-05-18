---
title: 'Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2e128f1011b6daa5c0e8b62252c8adc3175586c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-characters-from-a-string"></a>Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge
In den folgenden Codebeispielen wird das synchrone und asynchrone Lesen von Zeichen aus einer Zeichenfolge veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden 13 Zeichen synchron aus einer Zeichenfolge gelesen, in einem Array gespeichert und als Zeichen angezeigt. Anschließend werden die restlichen Zeichen in der Zeichenfolge gelesen und im Array beginnend mit dem sechsten Element gespeichert. Dann wird der Inhalt des Arrays angezeigt.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Im nächsten Beispiel werden alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert. Dann wird jeder Buchstabe bzw. jedes Leerzeichen in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement asynchron gefolgt von einem Zeilenumbruch in eine separate Zeile geschrieben.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: Gewusst wie: Erstellen einer Verzeichnisauflistung](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Gewusst wie: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
