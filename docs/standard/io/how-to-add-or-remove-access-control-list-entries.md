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
# <a name="how-to-add-or-remove-access-control-list-entries"></a>Gewusst wie: Hinzufügen oder Entfernen von Zugriffssteuerungslisten-Einträgen
Um ACL-Einträge (Access Control List, Zugriffssteuerungsliste) zu einer Datei hinzuzufügen oder aus einer Datei zu entfernen, muss das <xref:System.Security.AccessControl.FileSecurity>-Objekt oder das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt aus der Datei oder aus dem Verzeichnis abgerufen, geändert und dann wieder auf die Datei oder das Verzeichnis angewendet werden.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a>So fügen Sie einen ACL-Eintrag zu einer Datei hinzu bzw. entfernen ihn aus einer Datei  
  
1.  Rufen Sie die <xref:System.IO.File.GetAccessControl%2A>-Methode auf, um ein <xref:System.Security.AccessControl.FileSecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge einer Datei enthält.  
  
2.  Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.FileSecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.  
  
3.  Übergeben Sie das <xref:System.Security.AccessControl.FileSecurity>-Objekt an die <xref:System.IO.File.SetAccessControl%2A>-Methode, um die Änderungen anzuwenden.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a>So fügen Sie einen ACL-Eintrag einem Verzeichnis hinzu bzw. entfernen ihn aus einem Verzeichnis  
  
1.  Rufen Sie die <xref:System.IO.Directory.GetAccessControl%2A>-Methode auf, um ein <xref:System.Security.AccessControl.DirectorySecurity>-Objekt abzurufen, das die aktuellen ACL-Einträge eines Verzeichnisses enthält.  
  
2.  Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.DirectorySecurity>-Objekt, indem Sie ihm ACL-Einträge hinzufügen oder ACL-Einträge aus ihm entfernen.  
  
3.  Übergeben Sie das <xref:System.Security.AccessControl.DirectorySecurity>-Objekt an die <xref:System.IO.Directory.SetAccessControl%2A>-Methode, um die Änderungen anzuwenden.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie müssen ein gültiges Benutzer- oder Gruppenkonto angeben, um dieses Beispiel auszuführen. Dieses Beispiel verwendet ein <xref:System.IO.File>-Objekt. Dasselbe Verfahren wird jedoch auch für die Klassen <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo> verwendet.
