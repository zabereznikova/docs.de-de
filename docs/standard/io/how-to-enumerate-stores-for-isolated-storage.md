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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c4fa63c5c7f966831a55c9103c9ba58cfa621d6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="d0d1a-102">Gewusst wie: Auflisten von Speichern für isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="d0d1a-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="d0d1a-103">Sie können alle isolierten Speicher für den aktuellen Benutzer mit der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>-Methode auflisten.</span><span class="sxs-lookup"><span data-stu-id="d0d1a-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="d0d1a-104">Diese Methode nimmt einen <xref:System.IO.IsolatedStorage.IsolatedStorageScope>-Wert entgegen und gibt einen <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Enumerator zurück.</span><span class="sxs-lookup"><span data-stu-id="d0d1a-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="d0d1a-105">Zum Auflisten von Speichern benötigen Sie die <xref:System.Security.Permissions.IsolatedStorageFilePermission>-Berechtigung, die den <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser>-Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="d0d1a-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="d0d1a-106">Beim Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>-Methode mit dem <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User>-Wert wird ein Array von <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekten zurückgegeben, die für den aktuellen Benutzer definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d0d1a-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0d1a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0d1a-107">Example</span></span>  
 <span data-ttu-id="d0d1a-108">Im folgenden Codebeispiel werden ein Speicher abgerufen, der nach Benutzer und Assembly isoliert ist, einige Dateien erstellt und diese Dateien mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>-Methode abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d0d1a-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d0d1a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0d1a-109">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="d0d1a-110">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="d0d1a-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
