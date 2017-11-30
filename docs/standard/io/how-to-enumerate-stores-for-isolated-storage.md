---
title: "Gewusst wie: Auflisten von Speichern für isolierten Speicher"
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
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="fa68b-102">Gewusst wie: Auflisten von Speichern für isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="fa68b-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="fa68b-103">Sie können alle isolierten Speicher für den aktuellen Benutzer auflisten, mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> statische Methode.</span><span class="sxs-lookup"><span data-stu-id="fa68b-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="fa68b-104">Diese Methode nimmt ein <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Wert und gibt eine <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Enumerator.</span><span class="sxs-lookup"><span data-stu-id="fa68b-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="fa68b-105">Zum Auflisten von speichern, benötigen Sie die <xref:System.Security.Permissions.IsolatedStorageFilePermission> Berechtigung, der angibt, die <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> Wert.</span><span class="sxs-lookup"><span data-stu-id="fa68b-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="fa68b-106">Beim Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode mit dem <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> Wert, es gibt ein Array von <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte, die für den aktuellen Benutzer definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fa68b-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa68b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa68b-107">Example</span></span>  
 <span data-ttu-id="fa68b-108">Im folgenden Codebeispiel wird erhält einen Speicher, der nach Benutzer und Assembly isoliert ist, erstellt einige Dateien und ruft diese Dateien ab, indem die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fa68b-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fa68b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa68b-109">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="fa68b-110">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="fa68b-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
