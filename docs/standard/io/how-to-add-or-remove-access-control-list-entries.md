---
title: "Gewusst wie: Hinzuf&#252;gen oder Entfernen von Zugriffssteuerungslisten-Eintr&#228;gen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zugriffssteuerungseinträge [.NET Framework]"
  - "Zugriffssteuerungslisten [.NET Framework]"
  - "ACEs [.NET Framework]"
  - "ACLs [.NET Framework]"
  - "E/A [.NET Framework], Zugriffssteuerungslisteneinträge"
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen oder Entfernen von Zugriffssteuerungslisten-Eintr&#228;gen
Um ACL\-Einträge \(Access Control List, Zugriffssteuerungsliste\) zu einer Datei hinzuzufügen oder aus einer Datei zu entfernen, muss das <xref:System.Security.AccessControl.FileSecurity>\-Objekt oder das <xref:System.Security.AccessControl.DirectorySecurity>\-Objekt aus der Datei oder aus dem Verzeichnis abgerufen, geändert und dann wieder auf die Datei oder das Verzeichnis angewendet werden.  
  
### So fügen Sie einen ACL\-Eintrag zu einer Datei hinzu bzw. entfernen ihn aus einer Datei  
  
1.  Rufen Sie die <xref:System.IO.File.GetAccessControl%2A>\-Methode auf, um ein <xref:System.Security.AccessControl.FileSecurity>\-Objekt abzurufen, das die aktuellen ACL\-Einträge einer Datei enthält.  
  
2.  Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.FileSecurity>\-Objekt, indem Sie ihm ACL\-Einträge hinzufügen oder ACL\-Einträge aus ihm entfernen.  
  
3.  Übergeben Sie das <xref:System.Security.AccessControl.FileSecurity>\-Objekt an die <xref:System.IO.File.SetAccessControl%2A>\-Methode, um die Änderungen anzuwenden.  
  
### So fügen Sie einen ACL\-Eintrag einem Verzeichnis hinzu bzw. entfernen ihn aus einem Verzeichnis  
  
1.  Rufen Sie die <xref:System.IO.Directory.GetAccessControl%2A>\-Methode auf, um ein <xref:System.Security.AccessControl.DirectorySecurity>\-Objekt abzurufen, das die aktuellen ACL\-Einträge eines Verzeichnisses enthält.  
  
2.  Bearbeiten Sie das in Schritt 1 zurückgegebene <xref:System.Security.AccessControl.DirectorySecurity>\-Objekt, indem Sie ihm ACL\-Einträge hinzufügen oder ACL\-Einträge aus ihm entfernen.  
  
3.  Übergeben Sie das <xref:System.Security.AccessControl.DirectorySecurity>\-Objekt an die <xref:System.IO.Directory.SetAccessControl%2A>\-Methode, um die Änderungen anzuwenden.  
  
## Beispiel  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## Kompilieren des Codes  
 Sie müssen ein gültiges Benutzer\- oder Gruppenkonto angeben, um dieses Beispiel auszuführen.  Dieses Beispiel verwendet ein <xref:System.IO.File>\-Objekt. Dasselbe Verfahren wird jedoch auch für die Klassen <xref:System.IO.FileInfo>, <xref:System.IO.Directory> und <xref:System.IO.DirectoryInfo> verwendet.