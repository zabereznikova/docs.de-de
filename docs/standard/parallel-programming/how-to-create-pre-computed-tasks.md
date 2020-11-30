---
title: 'Gewusst wie: Erstellen von vorberechneten Aufgaben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
ms.openlocfilehash: e83b467e23013b5690db7cc63d061cab4d5d0e31
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734503"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="a479f-102">Gewusst wie: Erstellen von vorberechneten Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a479f-102">How to: Create Pre-Computed Tasks</span></span>

<span data-ttu-id="a479f-103">Dieses Dokument beschreibt, wie mithilfe der <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>-Methode die Ergebnisse asynchroner Downloadvorgänge aus einem Cache abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a479f-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="a479f-104">Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode gibt ein fertig gestelltes <xref:System.Threading.Tasks.Task%601>-Objekt zurück, das den angegebenen Wert als <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="a479f-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="a479f-105">Diese Methode ist nützlich, wenn Sie einen asynchronen Vorgang ausführen, der ein <xref:System.Threading.Tasks.Task%601>-Objekt zurückgibt, und das Ergebnis dieses <xref:System.Threading.Tasks.Task%601>-Objekts bereits berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="a479f-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a479f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a479f-106">Example</span></span>  

 <span data-ttu-id="a479f-107">Im folgenden Beispiel werden Zeichenfolgen aus dem Web heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="a479f-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="a479f-108">Es definiert die `DownloadStringAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a479f-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="a479f-109">Diese Methode lädt Zeichenfolgen asynchron aus dem Web herunter.</span><span class="sxs-lookup"><span data-stu-id="a479f-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="a479f-110">In diesem Beispiel wird außerdem ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt verwendet, um die Ergebnisse vorangegangener Vorgänge zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="a479f-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="a479f-111">Wenn die Eingabeadresse in diesem Cache gespeichert wird, verwendet `DownloadStringAsync` die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode zum Erzeugen eines <xref:System.Threading.Tasks.Task%601>-Objekts, das den Inhalt an dieser Adresse beibehält.</span><span class="sxs-lookup"><span data-stu-id="a479f-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="a479f-112">Andernfalls lädt `DownloadStringAsync` die Datei aus dem Web herunter und fügt das Ergebnis dem Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="a479f-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="a479f-113">In diesem Beispiel wird die zum zweimaligen Herunterladen mehrerer Zeichenfolgen erforderliche Zeit berechnet.</span><span class="sxs-lookup"><span data-stu-id="a479f-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="a479f-114">Die zweite Gruppe von Downloadvorgängen sollte weniger Zeit in Anspruch nehmen als die erste, da die Ergebnisse im Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a479f-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="a479f-115">Die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode ermöglicht der `DownloadStringAsync`-Methode, <xref:System.Threading.Tasks.Task%601>-Objekte zu erstellen, die diese vorberechneten Ergebnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="a479f-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a479f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a479f-116">See also</span></span>

- [<span data-ttu-id="a479f-117">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="a479f-117">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
