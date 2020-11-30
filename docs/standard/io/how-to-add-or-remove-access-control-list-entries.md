---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen (nur .NET Framework)'
ms.date: 01/14/2019
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
ms.openlocfilehash: 53daa88b761f46dab26b1c12c73741e880512d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682691"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>Vorgehensweise: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen (nur .NET Framework)

Um ACL-Einträge (Access Control List, Zugriffssteuerungsliste) zu einer Datei hinzuzufügen oder aus einer Datei oder einem Verzeichnis zu entfernen, rufen Sie das <xref:System.Security.AccessControl.FileSecurity>- oder <xref:System.Security.AccessControl.DirectorySecurity>-Objekt aus der Datei oder dem Verzeichnis ab. Bearbeiten Sie das Objekt, und wenden Sie es dann wieder auf die Datei oder das Verzeichnis an.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>Hinzufügen oder Entfernen eines ACL-Eintrags zu bzw. aus einer Datei  
  
1. Rufen Sie die <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType>-Methode auf, um ein <xref:System.Security.AccessControl.FileSecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge einer Datei enthält.  
  
2. Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.FileSecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.  
  
3. Um die Änderungen anzuwenden, übergeben Sie das <xref:System.Security.AccessControl.FileSecurity>-Objekt an die <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>-Methode.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>Hinzufügen oder Entfernen eines ACL-Eintrags zu bzw. aus einem Verzeichnis  
  
1. Rufen Sie die <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType>-Methode auf, um ein <xref:System.Security.AccessControl.DirectorySecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge eines Verzeichnisses enthält.  
  
2. Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.DirectorySecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.  
  
3. Um die Änderungen anzuwenden, übergeben Sie das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt an die <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>-Methode.  
  
## <a name="example"></a>Beispiel  

 Sie müssen ein gültiges Benutzer- oder Gruppenkonto verwenden, um dieses Beispiel auszuführen. In diesem Beispiel wird ein <xref:System.IO.File>-Objekt verwendet. Gehen Sie für die Klassen <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo> genauso vor.

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
