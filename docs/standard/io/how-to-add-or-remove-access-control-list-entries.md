---
title: 'Gewusst wie: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24c428a80f18b35d0aa3119a3c5fa1a6dcb2130e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573422"
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a><span data-ttu-id="e0efe-102">Gewusst wie: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen</span><span class="sxs-lookup"><span data-stu-id="e0efe-102">How to: Add or Remove Access Control List Entries</span></span>
<span data-ttu-id="e0efe-103">Um ACL-Einträge (Access Control List, Zugriffssteuerungsliste) zu einer Datei hinzuzufügen oder aus einer Datei zu entfernen, muss das <xref:System.Security.AccessControl.FileSecurity>-Objekt oder das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt aus der Datei oder aus dem Verzeichnis abgerufen, geändert und dann wieder auf die Datei oder das Verzeichnis angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0efe-103">To add or remove Access Control List (ACL) entries to or from a file, the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object must be obtained from the file or directory, modified, and then applied back to the file or directory.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="e0efe-104">So fügen Sie einen ACL-Eintrag zu einer Datei hinzu bzw. entfernen ihn aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="e0efe-104">To add or remove an ACL entry from a File</span></span>  
  
1.  <span data-ttu-id="e0efe-105">Rufen Sie die <xref:System.IO.File.GetAccessControl%2A>-Methode auf, um ein <xref:System.Security.AccessControl.FileSecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge einer Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="e0efe-105">Call the <xref:System.IO.File.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2.  <span data-ttu-id="e0efe-106">Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.FileSecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.</span><span class="sxs-lookup"><span data-stu-id="e0efe-106">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="e0efe-107">Übergeben Sie das <xref:System.Security.AccessControl.FileSecurity>-Objekt an die <xref:System.IO.File.SetAccessControl%2A>-Methode, um die Änderungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e0efe-107">Pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A> method to apply the changes.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="e0efe-108">So fügen Sie einen ACL-Eintrag einem Verzeichnis hinzu bzw. entfernen ihn aus einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="e0efe-108">To add or remove an ACL entry from a Directory</span></span>  
  
1.  <span data-ttu-id="e0efe-109">Rufen Sie die <xref:System.IO.Directory.GetAccessControl%2A>-Methode auf, um ein <xref:System.Security.AccessControl.DirectorySecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge eines Verzeichnisses enthält.</span><span class="sxs-lookup"><span data-stu-id="e0efe-109">Call the <xref:System.IO.Directory.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2.  <span data-ttu-id="e0efe-110">Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.DirectorySecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.</span><span class="sxs-lookup"><span data-stu-id="e0efe-110">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="e0efe-111">Übergeben Sie das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt an die <xref:System.IO.Directory.SetAccessControl%2A>-Methode, um die Änderungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e0efe-111">Pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A> method to apply the changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0efe-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0efe-112">Example</span></span>  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0efe-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e0efe-113">Compiling the Code</span></span>  
 <span data-ttu-id="e0efe-114">Sie müssen ein gültiges Benutzer- oder Gruppenkonto angeben, um dieses Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e0efe-114">You must supply a valid user or group account to run this example.</span></span> <span data-ttu-id="e0efe-115">Dieses Beispiel verwendet ein <xref:System.IO.File>-Objekt. Dasselbe Verfahren wird jedoch auch für die Klassen <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo> verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0efe-115">This example uses a <xref:System.IO.File> object; however, the same procedure is used for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>
