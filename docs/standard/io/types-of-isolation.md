---
title: Isolationstypen
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
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6b07c090a381925f5330a820214126a121d3790b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-isolation"></a>Isolationstypen
Zugriff auf isolierte Speicherung ist immer für den Benutzer, der sie erstellt beschränkt. Um diese Art von Isolation zu implementieren, verwendet die common Language Runtime dasselbe Konzept der Benutzeridentität, die das Betriebssystem erkennt, die Identität, die dem Prozess, in dem der Code ausgeführt wird, wenn der Speicher geöffnet ist, zugeordnet ist. Diese Identität ist eine authentifizierte Benutzeridentität Identitätswechsel kann dazu führen, dass die Identität des aktuellen Benutzers dynamisch zu ändern.  
  
 Zugriff auf isolierte Speicherplätze ist auch eingeschränkte gemäß der Identität der Anwendungsverzeichnis Domäne und Assembly, oder die Assembly, die allein zugeordnet ist. Die Laufzeit ruft diese Identitäten auf folgende Weise:  
  
-   Domänenidentität darstellt, den die Anwendung, die sich für eine Webanwendung möglicherweise die vollständige URL-Beweis. Für Shell-gehostetem Code kann die Domänenidentität auf den Verzeichnispfad der Anwendung basieren. Wenn die ausführbare Datei aus dem Pfad C:\Office\MyApp.exe ausgeführt wird, würde z. B. die Domänenidentität C:\Office\MyApp.exe sein.  
  
-   Assemblyidentität ist der Beweis der Assembly. Es kann aus einer kryptografischen digitalen Signatur der Assembly aneinander gehängt u. stammen [starken Namen](../../../docs/framework/app-domains/strong-named-assemblies.md), den Herausgeber der Software, der die Assembly bzw. dessen URL-Identität. Wenn eine Assembly einen starken Namen und eine Software Publisher Identität verfügt, wird die Software Publisher Identität verwendet. Wenn die Assembly aus dem Internet stammt und ohne Vorzeichen ist, wird die URL-Identität verwendet. Weitere Informationen zu Assemblys und starke Namen finden Sie unter [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Roamingspeichern verschieben sich mit einem Benutzer, der über ein servergespeichertes Profil verfügt. Dateien werden in einem Netzwerkverzeichnis geschrieben und werden auf jedem Computer heruntergeladen haben, die der Benutzer sich anmeldet. Weitere Informationen zu servergespeicherten Benutzerprofilen, finden Sie unter <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Durch die Kombination der Konzepte der Benutzer, Domäne und Assemblyidentität, kann isolierte Speicherung Daten auf folgende Weise Isolieren von denen jede eine eigene Verwendungsszenarien hat:  
  
-   [Isolation nach Benutzer und assembly](#UserAssembly)  
  
-   [Isolation nach Benutzer, Domäne und assembly](#UserDomainAssembly)  
  
 Jede dieser Isolationen können mit einem Roamingbenutzerprofil kombiniert werden. Weitere Informationen finden Sie im Abschnitt [isolierte Speicherung und Roaming](#Roaming).  
  
 Die folgende Abbildung zeigt, wie Speicher in verschiedenen Bereichen isoliert sind.  
  
 ![Isolation nach Benutzer und Assembly](../../../docs/standard/io/media/typesofisolation.gif "Typesofisolation")  
Typen des isolierten Speichers  
  
 Beachten Sie, dass mit Ausnahme von Roamingspeichern isolierte Speicherung immer implizit nach Computer isoliert ist, da er die Speicher-Funktionen verwendet, die lokal auf einem Computer befinden.  
  
> [!IMPORTANT]
>  Isolierte Speicherung ist nicht für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps verfügbar. Verwenden Sie stattdessen die zum Speichern von lokalen Daten und Dateien in der `Windows.Storage` -API enthaltenen Anwendungsdatenklassen in den [!INCLUDE[wrt](../../../includes/wrt-md.md)] -Namespaces. Weitere Informationen finden Sie im Windows Developer Center unter [Anwendungsdaten](http://go.microsoft.com/fwlink/?LinkId=229175) .  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a>Isolation nach Benutzer und Assembly  
 Wenn die Assembly, die die Daten verwendet Datenspeicher muss darauf zugreifen können jede Anwendungsdomäne Isolation nach Benutzer und Assembly eignet. In der Regel wird in dieser Situation isolierter Speicher verwendet, zum Speichern von Daten, die für mehrere Anwendungen angewendet wird und nicht an eine bestimmte Anwendung, z. B. den Namen des Benutzers oder Lizenzinformationen gebunden ist. Um nach Benutzer und Assembly isolierten Speicher zuzugreifen, muss Code vertrauenswürdig ist und die Übertragung von Informationen zwischen Anwendungen sein. Isolation nach Benutzer und Assembly ist in der Regel in Intranets, jedoch nicht auf das Internet zulässig. Aufrufen der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> -Methode und übergeben eines Benutzers und eine Assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Speicher bei dieser Art von Isolation zurückgegeben.  
  
 Im folgenden Codebeispiel ruft einen Speicher, der nach Benutzer und Assembly isoliert ist. Der Speicher durch zugegriffen werden kann die `isoFile` Objekt.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Ein Beispiel, die Beweisparameter verwendet, finden Sie unter <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> Methode ist als eine Verknüpfung verfügbar, wie im folgenden Codebeispiel gezeigt. Diese Verknüpfung kann nicht verwendet werden, um Läden öffnen, die roaming möglich sind; Verwenden Sie <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in solchen Fällen.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a>Isolation nach Benutzer, Domäne und Assembly  
 Wenn Ihre Anwendung eine dritten erstellte Assembly, die einen privaten Datenspeicher erfordert verwendet, können Sie isolierte Speicherung verwenden, um die privaten Daten zu speichern. Isolation nach Benutzer, Domäne und Assembly wird sichergestellt, dass nur Code in einer bestimmten Assembly kann die Daten zugreifen und nur, wenn die Assembly von der Anwendung verwendet wird, die ausgeführt wurde, wenn die Assembly der Speicher erstellt und nur während der Benutzer, denen der Speicher erstellt wurde, die  die Anwendung. Isolation nach Benutzer, Domäne und Assembly behält die Drittanbieter-Assembly aus gelangen Daten für andere Anwendungen. Dieser Isolationstyp sollte die Standardauswahl sein, wenn Sie wissen, dass Sie isolierte Speicherung verwenden möchten, aber nicht sicher welche Art von Isolation sind verwenden. Aufrufen der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile> und übergeben Sie einen Benutzer, Domäne und Assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Speicher bei dieser Art von Isolation zurückgegeben.  
  
 Im folgenden Codebeispiel ruft einen nach Benutzer, Domäne und Assembly isolierten Speicher ab. Der Speicher durch zugegriffen werden kann die `isoFile` Objekt.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Eine andere Methode ist als eine Verknüpfung verfügbar, wie im folgenden Codebeispiel gezeigt. Diese Verknüpfung kann nicht verwendet werden, um Läden öffnen, die roaming möglich sind; Verwenden Sie <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in solchen Fällen.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a>Isolierte Speicherung und Roaming  
 Servergespeicherte Benutzerprofile sind ein Windows-Feature, mit der einen Benutzer eine Identität in einem Netzwerk einrichten und verwenden Sie diese Identität bei jeder Computer im Netzwerk, über alle personalisierten Einstellungen befördern anmelden kann. Eine Assembly, die isolierte Speicherung verwendet kann angeben, dass mit das servergespeicherte Benutzerprofil des Benutzers isolierter Speicher verschoben werden soll. Roaming kann in Verbindung mit Isolation nach Benutzer und Assembly oder mit Isolation nach Benutzer, Domäne und Assembly verwendet werden. Wenn ein roaming-Gültigkeitsbereich nicht verwendet wird, werden speichert kein Roaming, selbst wenn ein Roamingbenutzerprofil verwendet wird.  
  
 Im folgenden Codebeispiel ruft einen nach Benutzer und Assembly isolierten Roamingspeicher ab. Der Speicher durch zugegriffen werden kann die `isoFile` Objekt.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Ein Domänenbereich kann hinzugefügt werden, um eine servergespeicherte nach Benutzer, Domäne und Anwendung isolierten Speicher zu erstellen. Dies wird im folgenden Codebeispiel wird veranschaulicht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
