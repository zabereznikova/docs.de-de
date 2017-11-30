---
title: "Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher"
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
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="44ee8-102">Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="44ee8-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>
<span data-ttu-id="44ee8-103">Code, der isolierten Speicherung verwendet durch eingeschränkt ist ein [Kontingent](../../../docs/standard/io/isolated-storage.md#quotas) , die gibt die maximale Größe für das Datendepot in der isolierten Speicherdateien und Verzeichnisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="44ee8-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="44ee8-104">Das Kontingent wird durch die Sicherheitsrichtlinie definiert und kann von Administratoren konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="44ee8-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="44ee8-105">Wenn die maximal Größe überschritten wird zulässige, wenn Sie versuchen, Daten Schreiben einer <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst, und der Vorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="44ee8-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="44ee8-106">Dies hilft, Denial-of-Service-Angriffe zu vermeiden, die verursachen könnte die Anwendung Anforderungen verweigern, da die Speicherung von Daten gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="44ee8-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>  
  
 <span data-ttu-id="44ee8-107">Um zu ermitteln, ob ein bestimmter Versuch kommt es zu Verbindungsfehlern aus diesem Grund ist die <xref:System.IO.IsolatedStorage.IsolatedStorage> Klasse enthält drei schreibgeschützte Eigenschaften: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, und <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="44ee8-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="44ee8-108">Sie können diese Eigenschaften verwenden, um zu bestimmen, ob das Schreiben in den Speicher die maximal zulässige Größe des Speichers, der überschritten werden soll.</span><span class="sxs-lookup"><span data-stu-id="44ee8-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="44ee8-109">Denken Sie daran, die isolierte Speicher kann gleichzeitig zugegriffen werden. Deshalb, wenn Sie die verbleibenden Speichermenge berechnen, konnte der Speicherplatz nach der Zeit genutzt werden, die Sie versuchen, in den Speicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="44ee8-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="44ee8-110">Allerdings können Sie die maximale Größe des Speichers verwenden, um zu ermitteln, ob der obere Grenzwert für verfügbaren Speicher ist bald erreicht.</span><span class="sxs-lookup"><span data-stu-id="44ee8-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>  
  
 <span data-ttu-id="44ee8-111">Die <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> Eigenschaft hängt Beweis aus der Assembly ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="44ee8-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="44ee8-112">Aus diesem Grund sollten Sie diese Eigenschaft nur auf abrufen <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte, die erstellt wurden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44ee8-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="44ee8-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile>Objekte, die auf andere Weise erstellt wurden (z. B. Objekte, die von zurückgegeben wurden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode) keine genaue maximale Größe zurück.</span><span class="sxs-lookup"><span data-stu-id="44ee8-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44ee8-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44ee8-114">Example</span></span>  
 <span data-ttu-id="44ee8-115">Im folgenden Codebeispiel wird ein isolierter Speicher abgerufen, einige Dateien erstellt und ruft die <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="44ee8-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="44ee8-116">Der verbleibende Speicherplatz wird in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="44ee8-116">The remaining space is reported in bytes.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="44ee8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44ee8-117">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="44ee8-118">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="44ee8-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="44ee8-119">Gewusst wie: Erhalten von Speichern für isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="44ee8-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
