---
title: 'Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
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
ms.openlocfilehash: 5666019e1a65880221261ef5ad704f82c37263b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708114"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Gewusst wie: Vorhersehen von Speicherengpässen bei isoliertem Speicher

Code, der isolierten Speicher verwendet, ist durch ein [Kontingent](../../../docs/standard/io/isolated-storage.md#quotas) eingeschränkt, das die maximale Größe für das Datendepot festlegt, in dem isolierte Speicherdateien und Verzeichnisse vorhanden sind. Das Kontingent wird durch die Sicherheitsrichtlinie definiert und kann von Administratoren konfiguriert werden. Falls die maximal zulässige Größe überschritten wird, wenn Sie versuchen, Daten zu schreiben, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme ausgelöst, und bei dem Vorgang tritt ein Fehler auf. Dies hilft, bösartige Denial-of-Service-Angriffe zu vermeiden, die dazu führen könnten, dass die Anwendung Anforderungen verweigert, da der Datenspeicher gefüllt ist.

Um Ihnen bei der Bestimmung zu helfen, ob bei einem bestimmten Schreibversuch wahrscheinlich aus diesem Grund ein Fehler auftritt, bietet die <xref:System.IO.IsolatedStorage.IsolatedStorage>-Klasse drei schreibgeschützte Eigenschaften: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. Sie können diese Eigenschaften verwenden, um zu bestimmen, ob beim Schreiben in den Speicher die maximal zulässige Größe des Speichers überschritten wird. Berücksichtigen Sie, dass paralleler Zugriff auf isolierten Speicher möglich ist. Darum denken Sie beim Berechnen der verbleibenden Speichermenge daran, dass der Speicherplatz verbraucht sein könnte, wenn Sie versuchen, in den Speicher zu schreiben. Allerdings können Sie mithilfe der maximalen Größe des Speichers ermitteln, ob der obere Grenzwert verfügbaren Speichers bald erreicht ist.

Die <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>-Eigenschaft hängt von dem Beweis ab, dass die Assembly ordnungsgemäß funktioniert. Aus diesem Grund sollten Sie diese Eigenschaft nur bei <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekten abrufen, die mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>-, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>- oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode erstellt wurden. <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekte, die auf andere Weise erstellt wurden (z.B. Objekte, die von der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>-Methode zurückgegeben wurden), geben keine genaue maximale Größe zurück.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden ein isolierter Speicher abgerufen, einige Dateien erstellt und die <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>-Eigenschaft abgerufen. Der verbleibende Speicherplatz wird in Bytes angegeben.

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
- [Gewusst wie: Erhalten von Speichern für isolierten Speicher](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
