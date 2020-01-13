---
title: 'Vorgehensweise: Vorhersehen von Speicherengpässen bei isoliertem Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
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
ms.openlocfilehash: 5666019e1a65880221261ef5ad704f82c37263b2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708114"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="7a8c5-102">Vorgehensweise: Vorhersehen von Speicherengpässen bei isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="7a8c5-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>

<span data-ttu-id="7a8c5-103">Code, der isolierten Speicher verwendet, ist durch ein [Kontingent](../../../docs/standard/io/isolated-storage.md#quotas) eingeschränkt, das die maximale Größe für das Datendepot festlegt, in dem isolierte Speicherdateien und Verzeichnisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="7a8c5-104">Das Kontingent wird durch die Sicherheitsrichtlinie definiert und kann von Administratoren konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="7a8c5-105">Falls die maximal zulässige Größe überschritten wird, wenn Sie versuchen, Daten zu schreiben, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme ausgelöst, und bei dem Vorgang tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="7a8c5-106">Dies hilft, bösartige Denial-of-Service-Angriffe zu vermeiden, die dazu führen könnten, dass die Anwendung Anforderungen verweigert, da der Datenspeicher gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>

<span data-ttu-id="7a8c5-107">Um Ihnen bei der Bestimmung zu helfen, ob bei einem bestimmten Schreibversuch wahrscheinlich aus diesem Grund ein Fehler auftritt, bietet die <xref:System.IO.IsolatedStorage.IsolatedStorage>-Klasse drei schreibgeschützte Eigenschaften: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="7a8c5-108">Sie können diese Eigenschaften verwenden, um zu bestimmen, ob beim Schreiben in den Speicher die maximal zulässige Größe des Speichers überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="7a8c5-109">Berücksichtigen Sie, dass paralleler Zugriff auf isolierten Speicher möglich ist. Darum denken Sie beim Berechnen der verbleibenden Speichermenge daran, dass der Speicherplatz verbraucht sein könnte, wenn Sie versuchen, in den Speicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="7a8c5-110">Allerdings können Sie mithilfe der maximalen Größe des Speichers ermitteln, ob der obere Grenzwert verfügbaren Speichers bald erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>

<span data-ttu-id="7a8c5-111">Die <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>-Eigenschaft hängt von dem Beweis ab, dass die Assembly ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="7a8c5-112">Aus diesem Grund sollten Sie diese Eigenschaft nur bei <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekten abrufen, die mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>-, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>- oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="7a8c5-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekte, die auf andere Weise erstellt wurden (z.B. Objekte, die von der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>-Methode zurückgegeben wurden), geben keine genaue maximale Größe zurück.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>

## <a name="example"></a><span data-ttu-id="7a8c5-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a8c5-114">Example</span></span>

<span data-ttu-id="7a8c5-115">Im folgenden Codebeispiel werden ein isolierter Speicher abgerufen, einige Dateien erstellt und die <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>-Eigenschaft abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="7a8c5-116">Der verbleibende Speicherplatz wird in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a8c5-116">The remaining space is reported in bytes.</span></span>

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a><span data-ttu-id="7a8c5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a8c5-117">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="7a8c5-118">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="7a8c5-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
- [<span data-ttu-id="7a8c5-119">Vorgehensweise: Erhalten von Speichern für isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="7a8c5-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
