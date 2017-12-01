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
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Gewusst wie: Erhalten von Speichern für isolierten Speicher
Ein isolierter Speicher verfügbar macht, ein virtuelles Dateisystem in einem Datendepot. Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse stellt eine Reihe von Methoden für die Interaktion mit einem isolierten Speicher. Zum Erstellen und Abrufen von Speichern <xref:System.IO.IsolatedStorage.IsolatedStorageFile> stellt drei statische Methoden bereit:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Gibt zurück, Speicher, der nach Benutzer und Assembly isoliert ist.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Gibt den Speicher, die isoliert ist nach Domäne und Assembly zurück.  
  
     Beide Methoden rufen einen Speicher, der an den Code gehört, von dem sie aufgerufen werden.  
  
-   Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> gibt einen isolierten Speicher, der durch die Übergabe in einer Kombination von Scope-Parameter angegeben wird.  
  
 Der folgende Code gibt einen Speicher, der nach Benutzer, Assembly und Domäne isoliert ist.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode, um anzugeben, dass ein Speicher mit einem Roamingbenutzerprofil aktiviert. Details dazu, wie Sie dies einrichten, finden Sie unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md).  
  
 Isolierter Speicher, die von innerhalb von anderen Assemblys abgerufen werden, sind standardmäßig, unterschiedliche Speicher. Sie können Zugriff auf den Store von einer anderen Assembly oder einer Domäne durch Übergabe des in der Assembly oder Domäne Beweis in den Parametern von der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode. Erfordert die Berechtigung Zugriff auf isolierten Speicherplatz durch die Identität der Anwendungsdomäne. Weitere Informationen finden Sie unter der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Überladungen der Methode.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> -Methoden zurückgeben einer <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekt. Damit können Sie entscheiden, welche Isolationstyp für Ihre Situation am besten geeignet ist, finden Sie unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md). Wenn Sie ein Objekt "Datei" isolierten Speicher haben, können Sie Methoden der isolierten Speicherung verwenden, lesen, schreiben, erstellen und Löschen von Dateien und Verzeichnissen.  
  
 Es gibt keinen Mechanismus der Übergabe Code verhindert, dass ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Objekt, dass der code verfügt nicht über ausreichende Zugriffsrechte für den Speicher selbst. Domäne und Assembly Identitäten und Berechtigungen für isolierten Speicher werden nur überprüft, wenn ein Verweis auf ein <xref:System.IO.IsolatedStorage.IsolatedStorage> -Objekt abgerufen wird, in der Regel in der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode. Verweise auf Schutz <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte wird daher der Verantwortung des Codes, der diese Verweise verwendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code bietet ein einfaches Beispiel einer Klasse, erhalten einen Speicher, der nach Benutzer und Assembly isoliert ist. Der Code kann geändert werden, um einen Speicher abzurufen, die durch Hinzufügen von nach Benutzer, Domäne und Assembly isoliert ist <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> auf die Argumente, die die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> -Methode übergibt.  
  
 Nachdem Sie den Code ausführen, können Sie sicherstellen, dass ein Speicher, indem Sie Folgendes eingeben erstellt wurde **StoreAdm/List** in der Befehlszeile. Dadurch wird ausgeführt, die [Isolated Storage-Tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) und listet alle aktuellen isolierten, für den Benutzer speichert.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)  
 [Isolationstypen](../../../docs/standard/io/types-of-isolation.md)  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
