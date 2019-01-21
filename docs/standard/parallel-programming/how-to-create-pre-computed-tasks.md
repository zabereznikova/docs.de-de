---
title: 'Vorgehensweise: Erstellen von vorberechneten Aufgaben'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa95eccfa39073bb8ccb3cb9c49e099ac1f90ab1
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222099"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="97589-102">Vorgehensweise: Erstellen von vorberechneten Aufgaben</span><span class="sxs-lookup"><span data-stu-id="97589-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="97589-103">Dieses Dokument beschreibt, wie mithilfe der <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>-Methode die Ergebnisse asynchroner Downloadvorgänge aus einem Cache abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="97589-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="97589-104">Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode gibt ein fertig gestelltes <xref:System.Threading.Tasks.Task%601>-Objekt zurück, das den angegebenen Wert als <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="97589-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="97589-105">Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="97589-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97589-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97589-106">Example</span></span>  
 <span data-ttu-id="97589-107">Im folgenden Beispiel werden Zeichenfolgen aus dem Web heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="97589-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="97589-108">Es definiert die `DownloadStringAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="97589-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="97589-109">Diese Methode lädt Zeichenfolgen asynchron aus dem Web herunter.</span><span class="sxs-lookup"><span data-stu-id="97589-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="97589-110">In diesem Beispiel wird außerdem ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt verwendet, um die Ergebnisse vorangegangener Vorgänge zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="97589-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="97589-111">Wenn die Eingabeadresse in diesem Cache gespeichert wird, verwendet `DownloadStringAsync` die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode zum Erzeugen eines <xref:System.Threading.Tasks.Task%601>-Objekts, das den Inhalt an dieser Adresse beibehält.</span><span class="sxs-lookup"><span data-stu-id="97589-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="97589-112">Andernfalls lädt `DownloadStringAsync` die Datei aus dem Web herunter und fügt das Ergebnis dem Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="97589-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="97589-113">In diesem Beispiel wird die zum zweimaligen Herunterladen mehrerer Zeichenfolgen erforderliche Zeit berechnet.</span><span class="sxs-lookup"><span data-stu-id="97589-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="97589-114">Die zweite Gruppe von Downloadvorgängen sollte weniger Zeit in Anspruch nehmen als die erste, da die Ergebnisse im Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="97589-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="97589-115">Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode ermöglicht der `DownloadStringAsync`-Methode, <xref:System.Threading.Tasks.Task%601>-Objekte zu erstellen, die diese vorberechneten Ergebnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="97589-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97589-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="97589-116">Compiling the Code</span></span>  
 <span data-ttu-id="97589-117">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei namens `CachedDownloads.cs` ein (`CachedDownloads.vb` für Visual Basic), und führen Sie dann den folgenden Befehl in einer Developer-Eingabeaufforderung für Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="97589-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Developer Command Prompt for Visual Studio window.</span></span>  
  
 <span data-ttu-id="97589-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="97589-118">Visual C#</span></span>  
  
 <span data-ttu-id="97589-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="97589-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="97589-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97589-120">Visual Basic</span></span>  
  
 <span data-ttu-id="97589-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="97589-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="97589-122">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="97589-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97589-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97589-123">See also</span></span>

- [<span data-ttu-id="97589-124">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="97589-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
