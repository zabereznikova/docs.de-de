---
title: "How to: Create Pre-Computed Tasks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, creating pre-computed"
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Create Pre-Computed Tasks
Dieses Dokument beschreibt, wie die <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=fullName>\-Methode verwendet, um die Ergebnisse der asynchronen Downloadvorgänge abzurufen, die in einem Cache gehalten werden.  Die <xref:System.Threading.Tasks.Task.FromResult%2A>\-Methode gibt einem fertigen <xref:System.Threading.Tasks.Task%601>\-Objekt zurück, das den bereitgestellten Wert als die <xref:System.Threading.Tasks.Task%601.Result%2A>\-Eigenschaft enthält.  Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>\-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>\-Objekts bereits berechnet wurde.  
  
## Beispiel  
 Im folgenden Beispiel werden Zeichenfolgen aus dem Web herunter.  Es definiert die `DownloadStringAsync`\-Methode.  Diese Methode lädt Zeichenfolgen vom Web asynchron herunter.  Das Beispiel verwendet außerdem ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>\-Objekt, um die Ergebnisse von vorangegangenen Operationen zwischenzuspeichern.  Wenn die Eingabeadresse in diesem Cache gehalten wird, verwendet `DownloadStringAsync` die <xref:System.Threading.Tasks.Task.FromResult%2A>\-Methode, um ein <xref:System.Threading.Tasks.Task%601>\-Objekt erzeugt, das den Inhalt an diese Adresse enthält.  Andernfalls wird die Datei `DownloadStringAsync` aus dem Web herunter und das Ergebnis dem Cache hinzu.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 In diesem Beispiel wird die Zeit, die erforderlich ist, um Mehrfachverbindungsstellenzeichenfolgen zweimal herunterzuladen.  Der zweite Satz von Downloadvorgängen sollte weniger Zeit als nehmen zuerst festgelegt, da die Ergebnisse im Cache gehalten werden.  Die <xref:System.Threading.Tasks.Task.FromResult%2A>\-Methode aktiviert die `DownloadStringAsync`\-Methode <xref:System.Threading.Tasks.Task%601>, um Objekte zu erstellen, die diese vorausberechneten Ergebnisse enthalten.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `CachedDownloads.cs` \(`CachedDownloads.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## Robuste Programmierung  
  
## Siehe auch  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)