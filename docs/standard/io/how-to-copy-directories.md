---
title: 'Vorgehensweise: Kopieren von Verzeichnissen'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 5d40db7f902dac8bd6bbdc1510be8e56a321be30
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159454"
---
# <a name="how-to-copy-directories"></a>Vorgehensweise: Kopieren von Verzeichnissen
In diesem Thema wird gezeigt, wie E/A-Klassen zum synchronen Kopieren der Inhalte eines Verzeichnisses an einen anderen Speicherort verwendet werden.

Ein Beispiel für das asynchrone Kopieren von Dateien finden Sie unter [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md).

In diesem Beispiel werden Unterverzeichnisse kopiert, indem `copySubDirs` der `DirectoryCopy`-Methode auf `true` festgelegt wird. Die `DirectoryCopy`-Methode kopiert Unterverzeichnisse rekursiv, indem sie sich selbst so lange für jedes weitere Unterverzeichnis aufruft, bis alle kopiert wurden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
- [Allgemeine E/A-Aufgaben](../../../docs/standard/io/common-i-o-tasks.md)
- [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md)
