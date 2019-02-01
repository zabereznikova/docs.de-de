---
title: 'Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 125c8ba03c4d1006535dd1e10cbd162b32fede4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740982"
---
# <a name="how-to-write-characters-to-a-string"></a>Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge
In den folgenden Codebeispielen werden Zeichen synchron und asynchron aus einem Zeichenarray in eine Zeichenfolge geschrieben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden 5 Zeichen synchron aus einem Array in eine Zeichenfolge geschrieben.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a>Beispiel  
 Im nächsten Beispiel werden alle Zeichen asynchron aus einem <xref:System.Windows.Controls.TextBox>-Steuerelement gelesen und in einem Array gespeichert. Dann wird jeder Buchstabe bzw. jedes Leerzeichen in einem <xref:System.Windows.Controls.TextBlock>-Steuerelement asynchron gefolgt von einem Zeilenumbruch in eine separate Zeile geschrieben.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StringWriter>
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>
- <xref:System.Text.StringBuilder>
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
- [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
- [Vorgehensweise: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Vorgehensweise: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Vorgehensweise: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
