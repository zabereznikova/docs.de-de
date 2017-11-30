---
title: "Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher"
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
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher
Code, der isolierten Speicherung verwendet durch eingeschränkt ist ein [Kontingent](../../../docs/standard/io/isolated-storage.md#quotas) , die gibt die maximale Größe für das Datendepot in der isolierten Speicherdateien und Verzeichnisse vorhanden sind. Das Kontingent wird durch die Sicherheitsrichtlinie definiert und kann von Administratoren konfiguriert. Wenn die maximal Größe überschritten wird zulässige, wenn Sie versuchen, Daten Schreiben einer <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst, und der Vorgang fehlschlägt. Dies hilft, Denial-of-Service-Angriffe zu vermeiden, die verursachen könnte die Anwendung Anforderungen verweigern, da die Speicherung von Daten gefüllt ist.  
  
 Um zu ermitteln, ob ein bestimmter Versuch kommt es zu Verbindungsfehlern aus diesem Grund ist die <xref:System.IO.IsolatedStorage.IsolatedStorage> Klasse enthält drei schreibgeschützte Eigenschaften: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, und <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. Sie können diese Eigenschaften verwenden, um zu bestimmen, ob das Schreiben in den Speicher die maximal zulässige Größe des Speichers, der überschritten werden soll. Denken Sie daran, die isolierte Speicher kann gleichzeitig zugegriffen werden. Deshalb, wenn Sie die verbleibenden Speichermenge berechnen, konnte der Speicherplatz nach der Zeit genutzt werden, die Sie versuchen, in den Speicher zu schreiben. Allerdings können Sie die maximale Größe des Speichers verwenden, um zu ermitteln, ob der obere Grenzwert für verfügbaren Speicher ist bald erreicht.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> Eigenschaft hängt Beweis aus der Assembly ordnungsgemäß funktioniert. Aus diesem Grund sollten Sie diese Eigenschaft nur auf abrufen <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte, die erstellt wurden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode. <xref:System.IO.IsolatedStorage.IsolatedStorageFile>Objekte, die auf andere Weise erstellt wurden (z. B. Objekte, die von zurückgegeben wurden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode) keine genaue maximale Größe zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein isolierter Speicher abgerufen, einige Dateien erstellt und ruft die <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> Eigenschaft. Der verbleibende Speicherplatz wird in Bytes angegeben.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)  
 [Gewusst wie: Erhalten von Speichern für isolierten Speicher](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
