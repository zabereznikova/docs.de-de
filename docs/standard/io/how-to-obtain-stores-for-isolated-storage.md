---
title: "Gewusst wie: Erhalten von Speichern f&#252;r isolierten Speicher | Microsoft Docs"
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
  - "Speicher, Abrufen"
  - "Speichern von Daten mit dem isolierten Speicher, Abrufen von Speichern"
  - "Isolierter Speicher, Abrufen von Speichern"
  - "Datenspeicher, Abrufen"
  - "Datenspeicher mit dem isolierten Speicher, Abrufen von Speichern"
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Erhalten von Speichern f&#252;r isolierten Speicher
Ein isolierter Speicher macht ein virtuelles Dateisystem innerhalb eines Datendepots verfügbar.  Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Klasse stellt mehrere Methoden für die Interaktion mit einem isolierten Speicher.  Um Speicher erstellen und abzurufen, stellt <xref:System.IO.IsolatedStorage.IsolatedStorageFile> drei statische Methoden:  
  
-   gibt <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> Speicher zurück, der nach Benutzer und Assembly isoliert ist.  
  
-   gibt <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> Speicher zurück, der aus der Domäne und Assembly isoliert ist.  
  
     Beide Methoden wird ein Speicher abgerufen, der dem Code angehört, aus dem sie aufgerufen werden.  
  
-   Die statische <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode gibt einen isolierten Speicher zurück, der durch die Übergabe einer Kombination von Bereichsparametern gekennzeichnet ist.  
  
 Im folgenden Code wird ein Speicher zurück, der nach Benutzer, Assembly und Domäne isolierten wird.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode verwenden, um anzugeben, ob ein Speicher für das Roaming mit einem soll.  Ausführliche Informationen, wie dieses, finden Sie unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md) einrichtet.  
  
 Bei isolierten Speichern, die in verschiedenen Assemblys erstellt werden, handelt es sich standardmäßig um unterschiedliche Speicher.  Auf den Speicher einer anderen Assembly oder Domäne kann zugegriffen, indem Sie in den Assemblys oder Domänen in den Parametern der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode übergeben.  Dazu ist die Zugriffsberechtigung für isolierte Speicherung anhand der Identität der Anwendungsdomäne notwendig.  Weitere Informationen finden Sie unter der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methodenüberladung.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methoden geben ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekt zurück.  Unter [Isolationstypen](../../../docs/standard/io/types-of-isolation.md) finden Sie weitere hilfreiche Informationen für die Entscheidung, welcher Isolationstyp sich für Ihre Situation am besten eignet.  Wenn Sie über ein Dateiobjekt mit isolierter Speicherung verfügen, können Sie Methoden der isolierten Speichermethoden verwenden, die zum Lesen, Schreiben, Erstellen und Löschen von Dateien und Verzeichnissen.  
  
 Es gibt keinen Mechanismus, der Code am Übergeben eines <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekts, um zum Code verhindert, das nicht über ausreichende Zugriffsrechte verfügt, um selbst auf den Speicher zuzugreifen.  Domänen\- und Assemblyidentitäten sowie Berechtigungen für isolierten Speicher werden nur überprüft, wenn ein Verweis auf ein <xref:System.IO.IsolatedStorage.IsolatedStorage>\-Objekt abgerufen wird, in der Regel in der Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  Für den Schutz von Verweisen auf <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekte ist daher der Code zuständig, in dem diese Verweise verwendet werden.  
  
## Beispiel  
 Der folgende Code stellt ein einfaches Beispiel einer Klasse, die einen Speicher erhält, der nach Benutzer und Assembly isoliert ist.  Der Code kann geändert werden, um einen Speicher abzurufen, der nach Benutzer, Domäne und Assembly isoliert, indem <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName> zu den Argumenten hinzugefügt wird, die die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode übergibt.  
  
 Nachdem Sie den Code ausführen, können Sie überprüfen, ob ein Speicher erstellt wurde, indem Sie in der Befehlszeile **StoreAdm \/LIST** ein.  Dies führt unter [Isoliertes Storage\-Tool \(Storeadm.exe\)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) aus und führt alle aktuellen isolierten Speicher für den Benutzer auf.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)   
 [Isolationstypen](../../../docs/standard/io/types-of-isolation.md)   
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)