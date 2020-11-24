---
title: 'Gewusst wie: Erstellen von vorberechneten Aufgaben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
ms.openlocfilehash: 3f2a47d2f9ba8870ff3598c5bc73b54588039702
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825766"
---
# <a name="how-to-create-pre-computed-tasks"></a>Gewusst wie: Erstellen von vorberechneten Aufgaben
Dieses Dokument beschreibt, wie mithilfe der <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>-Methode die Ergebnisse asynchroner Downloadvorgänge aus einem Cache abgerufen werden können. Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode gibt ein fertig gestelltes <xref:System.Threading.Tasks.Task%601>-Objekt zurück, das den angegebenen Wert als <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft enthält. Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Zeichenfolgen aus dem Web heruntergeladen. Es definiert die `DownloadStringAsync`-Methode. Diese Methode lädt Zeichenfolgen asynchron aus dem Web herunter. In diesem Beispiel wird außerdem ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt verwendet, um die Ergebnisse vorangegangener Vorgänge zwischenzuspeichern. Wenn die Eingabeadresse in diesem Cache gespeichert wird, verwendet `DownloadStringAsync` die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode zum Erzeugen eines <xref:System.Threading.Tasks.Task%601>-Objekts, das den Inhalt an dieser Adresse beibehält. Andernfalls lädt `DownloadStringAsync` die Datei aus dem Web herunter und fügt das Ergebnis dem Cache hinzu.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 In diesem Beispiel wird die zum zweimaligen Herunterladen mehrerer Zeichenfolgen erforderliche Zeit berechnet. Die zweite Gruppe von Downloadvorgängen sollte weniger Zeit in Anspruch nehmen als die erste, da die Ergebnisse im Cache gespeichert werden. Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode ermöglicht der `DownloadStringAsync`-Methode, <xref:System.Threading.Tasks.Task%601>-Objekte zu erstellen, die diese vorberechneten Ergebnisse enthalten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Aufgabenbasierte asynchrone Programmierung](task-based-asynchronous-programming.md)
