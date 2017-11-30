---
title: 'Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher
Nachdem Sie einen isolierten Speicher erhalten haben, können Sie Verzeichnisse und Dateien zum Speichern von Daten erstellen. In einem Speicher werden Datei- und Verzeichnisnamen in Bezug auf den Stamm des virtuellen Dateisystems angegeben.  
  
 Um ein Verzeichnis zu erstellen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> -Instanzmethode. Wenn Sie einem Unterverzeichnis des ein Verzeichnis, die nicht vorhanden ist angeben, werden beide Verzeichnisse erstellt. Wenn Sie ein Verzeichnis, die bereits vorhanden ist angeben, gibt die Methode zurück, ohne dass ein Verzeichnis erstellt, und keine Ausnahme ausgelöst wird. Jedoch, wenn Sie einen Verzeichnisnamen angeben, enthält ungültige Zeichen, eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst.  
  
 Verwenden Sie zum Erstellen einer Datei, die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> Methode.  
  
 In der Windows-Betriebssystem, isolierte Speicherdatei und Verzeichnis sind Namen Groß-/Kleinschreibung. D. h., wenn Sie eine Datei mit dem Namen erstellen `ThisFile.txt`, und erstellen Sie eine andere Datei mit dem Namen `THISFILE.TXT`, wird nur eine Datei erstellt. Der Dateiname behält seine ursprüngliche Groß-/Kleinschreibung zu Anzeigezwecken.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Dateien und Verzeichnissen in einem isolierten Speicher zu erstellen.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
