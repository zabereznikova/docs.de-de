---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen (nur .NET Framework)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: ff5a09207b3a1d810f9611dd6bb8cfd206adf1e8
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187969"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a><span data-ttu-id="5c4f0-102">Vorgehensweise: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen (nur .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="5c4f0-102">How to: Add or remove Access Control List entries (.NET Framework only)</span></span>

<span data-ttu-id="5c4f0-103">Um ACL-Einträge (Access Control List, Zugriffssteuerungsliste) zu einer Datei hinzuzufügen oder aus einer Datei oder einem Verzeichnis zu entfernen, rufen Sie das <xref:System.Security.AccessControl.FileSecurity>- oder <xref:System.Security.AccessControl.DirectorySecurity>-Objekt aus der Datei oder dem Verzeichnis ab.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-103">To add or remove Access Control List (ACL) entries to or from a file or directory, get the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object from the file or directory.</span></span> <span data-ttu-id="5c4f0-104">Bearbeiten Sie das Objekt, und wenden Sie es dann wieder auf die Datei oder das Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-104">Modify the object, and then apply it back to the file or directory.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="5c4f0-105">Hinzufügen oder Entfernen eines ACL-Eintrags zu bzw. aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="5c4f0-105">Add or remove an ACL entry from a file</span></span>  
  
1. <span data-ttu-id="5c4f0-106">Rufen Sie die <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType>-Methode auf, um ein <xref:System.Security.AccessControl.FileSecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge einer Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-106">Call the <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2. <span data-ttu-id="5c4f0-107">Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.FileSecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-107">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="5c4f0-108">Um die Änderungen anzuwenden, übergeben Sie das <xref:System.Security.AccessControl.FileSecurity>-Objekt an die <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-108">To apply the changes, pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="5c4f0-109">Hinzufügen oder Entfernen eines ACL-Eintrags zu bzw. aus einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="5c4f0-109">Add or remove an ACL entry from a directory</span></span>  
  
1. <span data-ttu-id="5c4f0-110">Rufen Sie die <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType>-Methode auf, um ein <xref:System.Security.AccessControl.DirectorySecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge eines Verzeichnisses enthält.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-110">Call the <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2. <span data-ttu-id="5c4f0-111">Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.DirectorySecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-111">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="5c4f0-112">Um die Änderungen anzuwenden, übergeben Sie das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt an die <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-112">To apply the changes, pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c4f0-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c4f0-113">Example</span></span>  
 <span data-ttu-id="5c4f0-114">Sie müssen ein gültiges Benutzer- oder Gruppenkonto verwenden, um dieses Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-114">You must use a valid user or group account to run this example.</span></span> <span data-ttu-id="5c4f0-115">In diesem Beispiel wird ein <xref:System.IO.File>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-115">The example uses a <xref:System.IO.File> object.</span></span> <span data-ttu-id="5c4f0-116">Gehen Sie für die Klassen <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo> genauso vor.</span><span class="sxs-lookup"><span data-stu-id="5c4f0-116">Use the same procedure for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
