---
title: 'Vorgehensweise: Löschen von Speichern im isolierten Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
ms.openlocfilehash: 6b1e8e651fd8e18c79dd629c154fb6c4d74243e3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707826"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a><span data-ttu-id="23083-102">Vorgehensweise: Löschen von Speichern im isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="23083-102">How to: Delete Stores in Isolated Storage</span></span>
<span data-ttu-id="23083-103">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse stellt zwei Methoden zum Löschen von isolierten Speicherdateien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="23083-103">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies two methods for deleting isolated storage files:</span></span>  
  
- <span data-ttu-id="23083-104">Die Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> akzeptiert keine Argumente und löscht den Speicher, von dem sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="23083-104">The instance method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> does not take any arguments and deletes the store that calls it.</span></span> <span data-ttu-id="23083-105">Für diesen Vorgang sind keine Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23083-105">No permissions are required for this operation.</span></span> <span data-ttu-id="23083-106">Jeder Code, der auf den Speicher zugreifen kann, kann beliebige oder sogar alle Daten darin löschen.</span><span class="sxs-lookup"><span data-stu-id="23083-106">Any code that can access the store can delete any or all the data inside it.</span></span>  
  
- <span data-ttu-id="23083-107">Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> akzeptiert den Enumerationswert <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> als Argument und löscht alle Speicher für den Benutzer, der den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="23083-107">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> takes the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> enumeration value, and deletes all the stores for the user who is running the code.</span></span> <span data-ttu-id="23083-108">Für diesen Vorgang ist die <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Berechtigung für den <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> -Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23083-108">This operation requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission for the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23083-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23083-109">Example</span></span>  
 <span data-ttu-id="23083-110">Im folgenden Codebeispiel wird die Verwendung der statischen und der Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="23083-110">The following code example demonstrates the use of the static and instance <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> methods.</span></span> <span data-ttu-id="23083-111">Die Klasse ruft zwei Speicher ab; einer ist für Benutzer und Assembly und der andere für Benutzer, Domäne und Assembly isoliert.</span><span class="sxs-lookup"><span data-stu-id="23083-111">The class obtains two stores; one is isolated for user and assembly and the other is isolated for user, domain, and assembly.</span></span> <span data-ttu-id="23083-112">Der für Benutzer, Domäne und Assembly isolierte Speicher wird dann durch Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> -Methode der isolierten Speicherdatei  `isoStore1`gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23083-112">The user, domain, and assembly store is then deleted by calling the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> method of the isolated storage file  `isoStore1`.</span></span> <span data-ttu-id="23083-113">Anschließend werden alle verbleibenden Speicher für den Benutzer durch Aufrufen der statischen Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23083-113">Then, all remaining stores for the user are deleted by calling the static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="23083-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23083-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="23083-115">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="23083-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
