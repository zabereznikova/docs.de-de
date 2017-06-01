---
title: "Gewusst wie: Vorhersehen von Speicherengp&#228;ssen bei isoliertem Speicher | Microsoft Docs"
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
  - "Datenspeicher, Kontingente"
  - "Isolierter Speicher, Kontingente"
  - "Menge des verwendeten isolierten Speichers"
  - "Begrenzen des verwendeten isolierten Speichers"
  - "Speicher, Kontingente"
  - "Speicher, Speicherplatzmangel"
  - "Datenspeicherung mit dem isolierten Speicher, Kontingente"
  - "Speichern von Daten mit dem isolierten Speicher, , Kontingente"
  - "Verbleibender Speicherplatz im isolierten Speicher"
  - "Datenspeicher, Speicherplatzmangel"
  - "Speichern von Daten mit dem isolierten Speicher, Speicherplatzmangel"
  - "Kontingente für den isolierten Speicher"
  - "Isolierter Speicher, Speicherplatzmangel"
  - "Datenspeicher mit dem isolierten Speicher, Speicherplatzmangel"
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Vorhersehen von Speicherengp&#228;ssen bei isoliertem Speicher
Code, der isolierte Speicherung verwendet, ist durch ein [Kontingent](../../../docs/standard/io/isolated-storage.md#quotas) begrenzt, das die maximale Größe des Datendepots festlegt, in dem sich isoliert gespeicherte Dateien und Verzeichnisse befinden.  Das Kontingent wird durch Sicherheitsrichtlinien festgelegt und kann von Administratoren konfiguriert werden.  Wenn das Maximum, dessen Größe zulässig ist, überschritten wird, wenn Sie versuchen, Daten zu schreiben, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme ausgelöst und die Operation schlägt fehl.  Dies verhindert böswillige Denial\-of\-Service\-Angriffe, die die Anwendung dazu veranlassen könnten, aufgrund eines vollen Datenspeichers keine Anforderungen mehr anzunehmen.  
  
 Um einfacher feststellen zu können, ob ein bestimmter Schreibversuch aus diesem Grund nicht erfolgreich sein könnte, stellt die <xref:System.IO.IsolatedStorage.IsolatedStorage>\-Klasse drei schreibgeschützte Eigenschaften bereit: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.  Sie können diese Eigenschaften verwenden, ob beim Schreiben zu bestimmen, den Speicher wird, das die zulässige Speichergröße überschritten wird.  Beachten Sie, dass auf verschiedene isolierte Speicherplätze gleichzeitig zugegriffen werden kann; Daher wenn Sie die Anzahl des verbleibenden Speicher berechnen, könnte der Speicherplatz genutzt werden, wenn Sie versuchen, den Speicher zu schreiben.  Sie können die maximale Speichergröße verwenden, um festzustellen, ob die Obergrenze für verfügbaren Speicher im Begriff ist erreicht werden.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>\-Eigenschaft hängt von den Beweisen der Assembly ab, um ordnungsgemäß zu arbeiten.  Aus diesem Grund sollte diese Eigenschaft nur für <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekte abrufen, die erstellt wurden, indem <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> oder <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode genutzt.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekte, die auf andere Weise erstellt wurden, \(z Objekte, die von der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>\-Methode zurückgegeben wurden\), geben keine genaue maximale Größe zurück.  
  
## Beispiel  
 Im folgenden Codebeispiel werden ein isolierter Speicher abgerufen, mehrere Dateien erstellt und die <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>\-Eigenschaft abgerufen.  Der restliche Speicherplatz wird in Bytes angegeben.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)   
 [Gewusst wie: Erhalten von Speichern für isolierten Speicher](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)