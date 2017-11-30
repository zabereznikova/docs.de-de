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
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="2de3d-102">Gewusst wie: Erstellen von vorberechneten Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2de3d-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="2de3d-103">Dieses Dokument beschreibt, wie die <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> Methode, um die Ergebnisse asynchroner Downloadvorgänge abzurufen, die in einem Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2de3d-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="2de3d-104">Die <xref:System.Threading.Tasks.Task.FromResult%2A> Methodenrückgabe fertig ist <xref:System.Threading.Tasks.Task%601> Objekt, das den angegebenen Wert als enthält seine <xref:System.Threading.Tasks.Task%601.Result%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2de3d-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="2de3d-105">Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="2de3d-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2de3d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2de3d-106">Example</span></span>  
 <span data-ttu-id="2de3d-107">Im folgende Beispiel werden Zeichenfolgen aus dem Web herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="2de3d-108">Definiert die `DownloadStringAsync` Methode.</span><span class="sxs-lookup"><span data-stu-id="2de3d-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="2de3d-109">Diese Methode lädt asynchron Zeichenfolgen aus dem Web herunter.</span><span class="sxs-lookup"><span data-stu-id="2de3d-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="2de3d-110">Dieses Beispiel verwendet außerdem eine <xref:System.Collections.Concurrent.ConcurrentDictionary%602> Objekt, das die Ergebnisse von vorangegangenen Operationen im cache.</span><span class="sxs-lookup"><span data-stu-id="2de3d-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="2de3d-111">Wenn die Eingabe Adresse in diesem Cache aufrechterhalten wird `DownloadStringAsync` verwendet die <xref:System.Threading.Tasks.Task.FromResult%2A> Methode erzeugt eine <xref:System.Threading.Tasks.Task%601> Objekt, das den Inhalt an dieser Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="2de3d-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="2de3d-112">Andernfalls `DownloadStringAsync` die Datei aus dem Web herunterlädt und das Ergebnis dem Cache hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="2de3d-113">In diesem Beispiel berechnet die Zeit, die erforderlich ist, um mehrere Zeichenfolgen zweimal herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="2de3d-114">Die zweite Gruppe von Downloadvorgänge geboten weniger Zeit als die erste Menge aus, da die Ergebnisse in den Cache gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="2de3d-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="2de3d-115">Die <xref:System.Threading.Tasks.Task.FromResult%2A> Methode ermöglicht die `DownloadStringAsync` Methode zum Erstellen der <xref:System.Threading.Tasks.Task%601> Objekte, die diese enthalten vorberechnet Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2de3d-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2de3d-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2de3d-116">Compiling the Code</span></span>  
 <span data-ttu-id="2de3d-117">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `CachedDownloads.cs` (`CachedDownloads.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="2de3d-118">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="2de3d-118">**csc.exe CachedDownloads.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="2de3d-119">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="2de3d-119">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2de3d-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="2de3d-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de3d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2de3d-121">See Also</span></span>  
 [<span data-ttu-id="2de3d-122">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="2de3d-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
