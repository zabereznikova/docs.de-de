---
title: 'Gewusst wie: Erhalten von Speichern für isolierten Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: a08563b67239c679e3bc88876781508fd78bea75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291837"
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Gewusst wie: Erhalten von Speichern für isolierten Speicher
Ein isolierter Speicher macht ein virtuelles Dateisystem in einem Datendepot verfügbar. Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Klasse bietet eine Reihe von Methoden für die Interaktion mit einem isolierten Speicher. Zum Erstellen und Abrufen von Speichern stellt <xref:System.IO.IsolatedStorage.IsolatedStorageFile> drei statische Methoden bereit:  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> gibt Speicher zurück, der nach Benutzer und Assembly isoliert ist.  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> gibt Speicher zurück, der nach Domäne und Assembly isoliert ist.  
  
     Beide Methoden rufen einen Speicher ab, der zu dem Code gehört, von dem sie aufgerufen werden.  
  
- Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> gibt einen isolierten Speicher zurück, der durch die Übergabe einer Kombination von Bereichsparametern angegeben wird.  
  
 Der folgende Code gibt einen Speicher zurück, der nach Benutzer, Assembly und Domäne isoliert ist.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Sie können mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode angeben, dass ein Speicher mit einem Roamingbenutzerprofil wechseln soll. Näheres zur entsprechenden Einrichtung erfahren Sie unter [Isolationstypen](types-of-isolation.md).  
  
 Isolierte Speicher, die von unterschiedlichen Assemblys abgerufen werden, sind standardmäßig unterschiedliche Speicher. Sie können auf den Store einer anderen Assembly oder Domäne zugreifen, indem Sie den Assembly- oder Domänenbeweis in den Parametern der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode übergeben. Dies setzt die Berechtigung zum Zugriff auf isolierten Speicher durch Anwendungsdomänenidentität voraus. Weitere Informationen finden Sie bei den <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methodenüberladungen.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>-, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>- und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode geben ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekt zurück. Um zu entscheiden, welcher Isolationstyp für Ihre Situation am besten geeignet ist, lesen Sie [Isolationstypen](types-of-isolation.md). Wenn Sie über ein Dateiobjekt verfügen, das ein isolierter Speicher ist, können Sie Methoden für isolierten Speicher verwenden, um aus Dateien und Verzeichnissen zu lesen, in sie zu schreiben, sie zu erstellen und zu löschen.  
  
 Es gibt keinen Mechanismus, der verhindert, dass Code ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekt an Code übergibt, der nicht über ausreichende Zugriffsrechte verfügt, um den Speicher selbst abzurufen. Domänen- und Assemblyidentitäten und Berechtigungen für isolierten Speicher werden nur überprüft, wenn ein Verweis auf ein <xref:System.IO.IsolatedStorage.IsolatedStorage>-Objekt abgerufen wird, in der Regel in der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>-, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>- oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode. Der Schutz von Verweisen auf <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Objekte liegt daher in der Verantwortung des Codes, der diese Verweise verwendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code bietet ein einfaches Beispiel einer Klasse, die einen Speicher abruft, der nach Benutzer und Assembly isoliert ist. Der Code kann durch Hinzufügen von <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> zu den Argumenten, die die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode übergibt, geändert werden, um einen Speicher abzurufen, der nach Benutzer, Domäne und Assembly isoliert ist.  
  
 Nachdem Sie den Code ausgeführt haben, können Sie sicherstellen, dass ein Speicher erstellt wurde, indem Sie **StoreAdm /LIST** in der Befehlszeile eingeben. Dadurch wird das [Tool „Isolierter Speicher“ (Storeadm.exe)](../../framework/tools/storeadm-exe-isolated-storage-tool.md) ausgeführt, und alle aktuellen isolierten Speicher des Benutzers werden aufgelistet.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Isolierter Speicher](isolated-storage.md)
- [Isolationstypen](types-of-isolation.md)
- [Assemblys in .NET](../assembly/index.md)
