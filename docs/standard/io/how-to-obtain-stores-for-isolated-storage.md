---
title: "Gewusst wie: Erhalten von Speichern für isolierten Speicher"
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
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a><span data-ttu-id="f0f5d-102">Gewusst wie: Erhalten von Speichern für isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="f0f5d-102">How to: Obtain Stores for Isolated Storage</span></span>
<span data-ttu-id="f0f5d-103">Ein isolierter Speicher verfügbar macht, ein virtuelles Dateisystem in einem Datendepot.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-103">An isolated store exposes a virtual file system within a data compartment.</span></span> <span data-ttu-id="f0f5d-104">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse stellt eine Reihe von Methoden für die Interaktion mit einem isolierten Speicher.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-104">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies a number of methods for interacting with an isolated store.</span></span> <span data-ttu-id="f0f5d-105">Zum Erstellen und Abrufen von Speichern <xref:System.IO.IsolatedStorage.IsolatedStorageFile> stellt drei statische Methoden bereit:</span><span class="sxs-lookup"><span data-stu-id="f0f5d-105">To create and retrieve stores, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> provides three static methods:</span></span>  
  
-   <span data-ttu-id="f0f5d-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Gibt zurück, Speicher, der nach Benutzer und Assembly isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> returns storage that is isolated by user and assembly.</span></span>  
  
-   <span data-ttu-id="f0f5d-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Gibt den Speicher, die isoliert ist nach Domäne und Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> returns storage that is isolated by domain and assembly.</span></span>  
  
     <span data-ttu-id="f0f5d-108">Beide Methoden rufen einen Speicher, der an den Code gehört, von dem sie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-108">Both methods retrieve a store that belongs to the code from which they are called.</span></span>  
  
-   <span data-ttu-id="f0f5d-109">Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> gibt einen isolierten Speicher, der durch die Übergabe in einer Kombination von Scope-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-109">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> returns an isolated store that is specified by passing in a combination of scope parameters.</span></span>  
  
 <span data-ttu-id="f0f5d-110">Der folgende Code gibt einen Speicher, der nach Benutzer, Assembly und Domäne isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-110">The following code returns a store that is isolated by user, assembly, and domain.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <span data-ttu-id="f0f5d-111">Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode, um anzugeben, dass ein Speicher mit einem Roamingbenutzerprofil aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-111">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method to specify that a store should roam with a roaming user profile.</span></span> <span data-ttu-id="f0f5d-112">Details dazu, wie Sie dies einrichten, finden Sie unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="f0f5d-112">For details on how to set this up, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span>  
  
 <span data-ttu-id="f0f5d-113">Isolierter Speicher, die von innerhalb von anderen Assemblys abgerufen werden, sind standardmäßig, unterschiedliche Speicher.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-113">Isolated stores obtained from within different assemblies are, by default, different stores.</span></span> <span data-ttu-id="f0f5d-114">Sie können Zugriff auf den Store von einer anderen Assembly oder einer Domäne durch Übergabe des in der Assembly oder Domäne Beweis in den Parametern von der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-114">You can access the store of a different assembly or domain by passing in the assembly or domain evidence in the parameters of the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="f0f5d-115">Erfordert die Berechtigung Zugriff auf isolierten Speicherplatz durch die Identität der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-115">This requires permission to access isolated storage by application domain identity.</span></span> <span data-ttu-id="f0f5d-116">Weitere Informationen finden Sie unter der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Überladungen der Methode.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-116">For more information, see the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method overloads.</span></span>  
  
 <span data-ttu-id="f0f5d-117">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> -Methoden zurückgeben einer <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-117">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> methods return an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object.</span></span> <span data-ttu-id="f0f5d-118">Damit können Sie entscheiden, welche Isolationstyp für Ihre Situation am besten geeignet ist, finden Sie unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="f0f5d-118">To help you decide which isolation type is most appropriate for your situation, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span> <span data-ttu-id="f0f5d-119">Wenn Sie ein Objekt "Datei" isolierten Speicher haben, können Sie Methoden der isolierten Speicherung verwenden, lesen, schreiben, erstellen und Löschen von Dateien und Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-119">When you have an isolated storage file object, you can use the isolated storage methods to read, write, create, and delete files and directories.</span></span>  
  
 <span data-ttu-id="f0f5d-120">Es gibt keinen Mechanismus der Übergabe Code verhindert, dass ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Objekt, dass der code verfügt nicht über ausreichende Zugriffsrechte für den Speicher selbst.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-120">There is no mechanism that prevents code from passing an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object to code that does not have sufficient access to get the store itself.</span></span> <span data-ttu-id="f0f5d-121">Domäne und Assembly Identitäten und Berechtigungen für isolierten Speicher werden nur überprüft, wenn ein Verweis auf ein <xref:System.IO.IsolatedStorage.IsolatedStorage> -Objekt abgerufen wird, in der Regel in der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-121">Domain and assembly identities and isolated storage permissions are checked only when a reference to an <xref:System.IO.IsolatedStorage.IsolatedStorage> object is obtained, typically in the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="f0f5d-122">Verweise auf Schutz <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte wird daher der Verantwortung des Codes, der diese Verweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-122">Protecting references to <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects is, therefore, the responsibility of the code that uses these references.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0f5d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0f5d-123">Example</span></span>  
 <span data-ttu-id="f0f5d-124">Der folgende Code bietet ein einfaches Beispiel einer Klasse, erhalten einen Speicher, der nach Benutzer und Assembly isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-124">The following code provides a simple example of a class obtaining a store that is isolated by user and assembly.</span></span> <span data-ttu-id="f0f5d-125">Der Code kann geändert werden, um einen Speicher abzurufen, die durch Hinzufügen von nach Benutzer, Domäne und Assembly isoliert ist <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> auf die Argumente, die die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> -Methode übergibt.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-125">The code can be changed to retrieve a store that is isolated by user, domain, and assembly by adding <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> to the arguments that the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method passes.</span></span>  
  
 <span data-ttu-id="f0f5d-126">Nachdem Sie den Code ausführen, können Sie sicherstellen, dass ein Speicher, indem Sie Folgendes eingeben erstellt wurde **StoreAdm/List** in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-126">After you run the code, you can confirm that a store was created by typing **StoreAdm /LIST** at the command line.</span></span> <span data-ttu-id="f0f5d-127">Dadurch wird ausgeführt, die [Isolated Storage-Tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) und listet alle aktuellen isolierten, für den Benutzer speichert.</span><span class="sxs-lookup"><span data-stu-id="f0f5d-127">This runs the [Isolated Storage tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) and lists all the current isolated stores for the user.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="f0f5d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0f5d-128">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="f0f5d-129">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="f0f5d-129">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="f0f5d-130">Isolationstypen</span><span class="sxs-lookup"><span data-stu-id="f0f5d-130">Types of Isolation</span></span>](../../../docs/standard/io/types-of-isolation.md)  
 [<span data-ttu-id="f0f5d-131">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="f0f5d-131">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
