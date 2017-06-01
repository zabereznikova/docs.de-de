---
title: "Isolationstypen | Microsoft Docs"
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
  - "Speichern von Daten mit dem isolierten Speicher, Zugriff auf isolierten Speicher"
  - "Speichern von Daten mit dem isolierten Speicher, Isolationstypen"
  - "Authentifizierung [.NET Framework], isolierter Speicher"
  - "Assemblys [.NET Framework], Identität"
  - "isolierter Speicher, Zugriff"
  - "Datenspeicherung mit dem isolierten Speicher, Isolationstypen"
  - "Datenspeicherung mit dem isolierten Speicher, Zugriff auf isolierten Speicher"
  - "Domänenidentität"
  - "isolierter Speicher, Typen"
  - "Benutzerauthentifizierung, isolierter Speicher"
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Isolationstypen
Der Zugriff auf einen isolierten Speicherplatz ist immer auf den Benutzer beschränkt, der ihn auch erstellt hat.  Zur Implementierung dieses Isolationstyps verwendet Common Language Runtime dasselbe Konzept der Benutzeridentität, das vom Betriebssystem erkannt wird, nämlich die Identität, die dem Prozess zugeordnete ist, in welchem der Code während des Öffnens des Speichers ausgeführt wird.  Bei dieser Identität handelt es sich um eine authentifizierte Benutzeridentität. Jedoch kann eine Imitation dazu führen, dass die Identität des aktuellen Benutzers dynamisch geändert wird.  
  
 Zugriff auf isolierte Speicher auch nach der Identität beschränkt, die der Domäne und der Assembly der Anwendung zugeordnet wird, oder mit der alleinassembly.  Die Identitäten werden durch die Laufzeit folgendermaßen ermittelt:  
  
-   Domänenidentität wird der Beweis der Anwendung dar, die im Fall einer Webanwendung kann die vollständige URL sein.  Bei Shell\-gehostetem Code kann die Domänenidentität auf dem Verzeichnispfad der Anwendung basieren.  Ein Beispiel: Falls die Anwendung vom Pfad C:\\Office\\MyApp.exe aus ausgeführt wird, lautet die Domänenidentität C:\\Office\\MyApp.exe.  
  
-   Bei der Assemblyidentität handelt es sich um den Beweis der Assembly.  Dieser könnte aus einer kryptografischen digitalen Signatur stammen, welche der [starke Name](../../../docs/framework/app-domains/strong-named-assemblies.md) der Assembly sein kann, oder aber es handelt sich um den Softwarepublisher der Assembly bzw. dessen URL\-Identität.  Verfügt eine Assembly sowohl über einen starken Namen als auch über die Identität eines Softwarepublishers, wird die Identität des Softwarepublishers verwendet.  Wenn die Assembly aus dem Internet stammt und nicht signiert ist, wird die URL\-Identität verwendet.  Weitere Informationen über Assemblys und starke Namen finden Sie unter [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Roamingspeicher wandern zusammen mit einem Benutzer, der über ein Roamingbenutzerprofil verfügt.  Dateien werden in ein Netzwerkverzeichnis geschrieben und jeweils auf den Computer heruntergeladen, bei dem sich der Benutzer anmeldet.  Weitere Informationen über Roamingbenutzerprofile finden Sie unter <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName>.  
  
 Durch die Kombination der Konzepte Benutzer\-, Domänen\- und Assemblyidentität können mit isolierter Speicherung Daten auf folgende Weisen isoliert werden, wobei jeder dieser Prozesse ein spezifisches Verwendungsszenario hat:  
  
-   [Isolation nach Benutzer und Assembly](#UserAssembly)  
  
-   [Isolation nach Benutzer, Domäne und Assembly](#UserDomainAssembly)  
  
 Jede dieser Isolationen kann mit einem Roamingbenutzerprofil kombiniert werden.  Weitere Informationen finden Sie im Abschnitt [Isolierte Speicherung und Roaming](#Roaming).  
  
 In der folgenden Abbildung wird die Isolation von Speichern in verschiedenen Gültigkeitsbereichen dargestellt.  
  
 ![Isolation nach Benutzer und Assembly](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
Typen von isolierter Speicherung  
  
 Beachten Sie, mit Ausnahme von Roamingspeichern bei isolierter Speicherung immer implizit nach Computer isoliert wird, da die lokal verfügbaren Speicherfunktionen des jeweiligen Computers verwendet, die auf einem Computer lokal sind.  
  
> [!IMPORTANT]
>  Isolierte Speicherung ist nicht für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps verfügbar.  Verwenden Sie stattdessen die zum Speichern von lokalen Daten und Dateien in der [!INCLUDE[wrt](../../../includes/wrt-md.md)]\-API enthaltenen Anwendungsdatenklassen in den `Windows.Storage`\-Namespaces.  Weitere Informationen finden Sie im Windows Developer Center unter [Anwendungsdaten](http://go.microsoft.com/fwlink/?LinkId=229175).  
  
<a name="UserAssembly"></a>   
## Isolation nach Benutzer und Assembly  
 Wenn die Assembly, die den Datenspeicher verwendet, von jeder Domäne der Anwendung aus verfügbar sein, bietet sich die Isolation nach Benutzer und Assembly an.  In der Regel wird in einer solchen Situation isolierte Speicherung für Daten verwendet, die für mehrere Anwendungen gültig und nicht auf bestimmte einzelne Anwendungen beschränkt sind \(z. B. der Benutzername oder Lizenzinformationen\).  Für den Zugriff auf Speicher, die nach Benutzer und Assembly isoliert sind, muss der Code für die Übertragung von Informationen zwischen Anwendungen vertrauenswürdig sein.  In der Regel ist die Isolation nach Benutzer und Assembly in Intranets, nicht jedoch im Internet erlaubt.  Aufrufen der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=fullName> methode und Übergabe in einen Benutzer und Assembly in einen <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Rückgabespeicher mit folgender Isolation.  
  
 Im folgenden Codebeispiel wird ein Speicher abgerufen, der nach Benutzer und Assembly isoliert ist.  Auf den Speicher kann durch das `isoFile` \-Objekt zugegriffen werden.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Ein Beispiel für die Beweisparameter, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>\-Methode im folgenden Codebeispiel bietet eine Abkürzung.  Diese Verknüpfung kann nicht verwendet werden, um Speicher zu öffnen, die für den Roaming möglich ist; Verwendungs in solchen Fällen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## Isolation nach Benutzer, Domäne und Assembly  
 Wenn die Anwendung eine Assembly von Drittanbietern verwendet, die einen privaten Datenspeicher benötigt, können Sie isolierte Speicherung verwenden, um die privaten Daten zu speichern.  Durch Isolation nach Benutzer, Domäne und Assembly ist sichergestellt, dass nur der Code einer bestimmten Assembly auf die Daten zugreifen kann, und zwar unter der Bedingung, dass die Assembly von der Anwendung verwendet wird, die beim Erstellen des Speichers durch die Assembly ausgeführt wurde. Eine weitere Bedingung ist, dass der Benutzer, für den der Speicher erstellt wurde, die Anwendung ausführt.  Durch Isolation nach Benutzer, Domäne und Assembly wird verhindert, dass die von Dritten erstellte Assembly Daten an andere Anwendungen weitergibt.  Dieser Isolationstyp sollte die Standardauswahl sein, sofern Sie sich für die Verwendung isolierter Speicherung entschieden haben, jedoch noch nicht wissen, welchen Isolationstyp Sie verwenden möchten.  Die statische <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>\-Methode von <xref:System.IO.IsolatedStorage.IsolatedStorageFile> und Aufruf Übergabe eines Benutzers, einer Domäne und einer Assembly gibt <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Speicher mit folgender Isolation zurück.  
  
 Im folgenden Codebeispiel wird ein Speicher abgerufen, der nach Benutzer, Domäne und Assembly isoliert ist.  Auf den Speicher kann durch das `isoFile`\-Objekt zugegriffen werden.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Die Methode im folgenden Codebeispiel bietet eine Abkürzung,  Diese Verknüpfung kann nicht verwendet werden, um Speicher zu öffnen, die für den Roaming möglich ist; Verwenden Sie in solchen Fällen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## Isolierte Speicherung und Roaming  
 Roamingbenutzerprofile sind eine Windows\-Funktion, die einen, mit der Benutzer eine Identität in einem Netzwerk zu installieren und die Identität zu verwenden, um in jedem Netzwerkcomputer zu protokollieren und übertragen alle personalisierbaren Einstellungen.  Eine Assembly, die isolierte Speicherung verwendet, kann festgelegt, dass der isolierte Speicherplatz des Benutzers mit dem Roamingbenutzerprofil mitwandert verschoben werden soll.  Roaming kann in Kombination mit Isolation nach Benutzer und Assembly oder mit Isolation nach Benutzer, Domäne und Assembly verwendet werden.  Wird der Roamingbereich nicht verwendet, erfolgt auch kein Roaming der Speicher, selbst dann nicht, wenn ein Roamingbenutzerprofil verwendet wird.  
  
 Im folgenden Codebeispiel wird ein Roamingspeicher abgerufen, der nach Benutzer und Assembly isoliert ist.  Auf den Speicher kann durch das `isoFile` \-Objekt zugegriffen werden.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Ein Domänenbereich kann zur Erstellung eines Roamingspeichers hinzugefügt werden, der nach Benutzer, Domäne und Anwendung isoliert ist.  Dies wird im folgenden Codebeispiel dargestellt.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)