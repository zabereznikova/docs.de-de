---
title: 'Gewusst wie: Erstellen von vorberechneten Aufgaben'
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
helpviewer_keywords: tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4596b28afe48aad4a84a7dd72b4a1d44a9ada8a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-pre-computed-tasks"></a>Gewusst wie: Erstellen von vorberechneten Aufgaben
Dieses Dokument beschreibt, wie die <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> Methode, um die Ergebnisse asynchroner Downloadvorgänge abzurufen, die in einem Cache gespeichert werden. Die <xref:System.Threading.Tasks.Task.FromResult%2A> Methodenrückgabe fertig ist <xref:System.Threading.Tasks.Task%601> Objekt, das den angegebenen Wert als enthält seine <xref:System.Threading.Tasks.Task%601.Result%2A> Eigenschaft. Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden Zeichenfolgen aus dem Web herunterlädt. Definiert die `DownloadStringAsync` Methode. Diese Methode lädt asynchron Zeichenfolgen aus dem Web herunter. Dieses Beispiel verwendet außerdem eine <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt, das die Ergebnisse von vorangegangenen Operationen im cache. Wenn die Eingabe Adresse in diesem Cache aufrechterhalten wird `DownloadStringAsync` verwendet die <xref:System.Threading.Tasks.Task.FromResult%2A> Methode erzeugt eine <xref:System.Threading.Tasks.Task%601> Objekt, das den Inhalt an dieser Adresse enthält. Andernfalls `DownloadStringAsync` die Datei aus dem Web herunterlädt und das Ergebnis dem Cache hinzugefügt.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 In diesem Beispiel berechnet die Zeit, die erforderlich ist, um mehrere Zeichenfolgen zweimal herunterzuladen. Die zweite Gruppe von Downloadvorgänge geboten weniger Zeit als die erste Menge aus, da die Ergebnisse in den Cache gespeichert sind. Die <xref:System.Threading.Tasks.Task.FromResult%2A> Methode ermöglicht die `DownloadStringAsync` Methode zum Erstellen der <xref:System.Threading.Tasks.Task%601> Objekte, die diese enthalten vorberechnet Ergebnisse.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `CachedDownloads.cs` (`CachedDownloads.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgabenbasierte asynchrone Programmierung](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
