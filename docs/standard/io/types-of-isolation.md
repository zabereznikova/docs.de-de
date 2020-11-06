---
title: Isolationstypen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET], isolated storage
- assemblies [.NET], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
ms.openlocfilehash: a1d64f0dfe8a457ae551792a852bd816941f2777
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189031"
---
# <a name="types-of-isolation"></a>Isolationstypen

Der Zugriff auf isolierten Speicher ist immer auf den Benutzer eingeschränkt, der ihn erstellt hat. Bei der Implementierung dieses Isolationstyps verwendet die Common Language Runtime den Begriff der Benutzeridentität, der auch vom Betriebssystem erkannt wird. Dabei handelt es sich um die Identität, die mit dem Prozess verknüpft ist, in dem der Code beim Öffnen des Speichers ausgeführt wird. Diese Identität ist eine authentifizierte Benutzeridentität, wobei ein Identitätswechsel dazu führen kann, dass sich die Identität des aktuellen Benutzers dynamisch ändert.  
  
 Zudem ist der Zugriff auf isolierte Speicherplätze durch die Identität eingeschränkt, die mit der Domäne und Assembly der Anwendung oder nur mit der Assembly verbunden ist. Die Runtime erhält diese Identitäten auf folgende Weise:  
  
- Die Domänenidentität stellt den Beweis für die Anwendung dar, die im Falle einer Webanwendung die vollständige URL sein kann. Bei Shell-gehostetem Code kann die Domänenidentität auf dem Pfad des Anwendungsverzeichnisses basieren. Wenn die ausführbare Datei beispielsweise aus dem Pfad C:\Office\MyApp.exe ausgeführt wird, lautet die Domänenidentität C:\Office\MyApp.exe.  
  
- Die Assemblyidentität ist der Beweis für die Assembly. Diese kann aus einer kryptographischen digitalen Signatur stammen, die der [starke Name](../assembly/strong-named.md) der Assembly, der Softwareherausgeber der Assembly oder ihre URL-Identität sein kann. Wenn eine Assembly sowohl einen starken Namen als auch eine Softwareherausgeberidentität hat, wird die Softwareherausgeberidentität verwendet. Wenn die Assembly aus dem Internet stammt und unsigniert ist, wird die URL-Identität verwendet. Weitere Informationen zu Assemblys und starken Namen finden Sie unter [Programming with Assemblies](../assembly/index.md) (Programmieren mit Assemblys).  
  
- Roamingspeicher wandern mit einem Benutzer, der über ein Roamingbenutzerprofil verfügt. Die Dateien werden in ein Netzwerkverzeichnis geschrieben und auf jeden Computer heruntergeladen, bei dem sich der Benutzer anmeldet. Weitere Informationen zu Roamingbenutzerprofilen finden Sie unter <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Durch die Kombination der Konzepte von Benutzer-, Domänen- und Assemblyidentität kann ein isolierter Speicher die Daten wie folgt isolieren, wobei es für jede dieser Methoden eigene Verwendungsszenarien gibt:  
  
- [Isolation nach Benutzer und Assembly](#UserAssembly)  
  
- [Isolation nach Benutzer, Domäne und Assembly](#UserDomainAssembly)  
  
 Jede dieser Isolationen kann mit einem Roamingbenutzerprofil kombiniert werden. Weitere Informationen finden Sie im Abschnitt [Isolierter Speicher und Roaming](#Roaming).  
  
 Die folgende Abbildung zeigt, wie Speicher in verschiedenen Bereichen isoliert werden:  
  
 ![Diagramm einer Isolation nach Benutzer und Assembly](./media/types-of-isolation/isolated-storage-types.gif)  
  
 Isolierte Speicher (mit Ausnahme von Roamingspeichern) sind immer implizit nach Computer isoliert, da sie die Speicherfunktionen verwenden, die sich lokal auf einem bestimmten Computer befinden.  
  
> [!IMPORTANT]
> Die isolierte Speicherung ist nicht für Windows 8.x Store-Apps verfügbar. Verwenden Sie stattdessen zum Speichern von lokalen Daten und Dateien die in der Windows-Runtime-API enthaltenen Anwendungsdatenklassen in den `Windows.Storage`-Namespaces. Weitere Informationen finden Sie im Windows Developer Center unter [Anwendungsdaten](/previous-versions/windows/apps/hh464917(v=win.10)) .  
  
<a name="UserAssembly"></a>
## <a name="isolation-by-user-and-assembly"></a>Isolation nach Benutzer und Assembly  
 Wenn die Assembly, die den Datenspeicher verwendet, von der Domäne einer beliebigen Anwendung aus zugänglich sein muss, ist eine Isolation nach Benutzer und Assembly angebracht. Typischerweise wird in dieser Situation isolierter Speicher verwendet, um Daten zu speichern, die für mehrere Anwendungen gelten und nicht an eine bestimmte Anwendung gebunden sind, wie z.B. der Benutzername oder Lizenzinformationen. Für den Zugriff auf Speicher, der nach Benutzer und Assembly isoliert ist, muss der Code vertrauenswürdig sein, um eine Datenübertragung zwischen Anwendungen zu ermöglichen. In der Regel ist die Isolation nach Benutzer und Assembly in Intranets erlaubt, nicht aber im Internet. Durch den Aufruf der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType>-Methode und die Übergabe an einen Benutzer und eine Assembly gibt <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Speicher dieses Isolationstyps zurück.  
  
 Im folgenden Codebeispiel wird ein Speicher abgerufen, der nach Benutzer und Assembly isoliert ist. Der Zugriff auf den Speicher wird durch das `isoFile`-Objekt ermöglicht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Ein Beispiel zur Verwendung der Beweisparameter finden Sie unter <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Wie im folgenden Codebeispiel gezeigt, ist die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>-Methode als Verknüpfung verfügbar. Diese Verknüpfung kann nicht zum Öffnen von Speichern verwendet werden, für die Roaming möglich ist. Verwenden Sie in solchen Fällen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>
## <a name="isolation-by-user-domain-and-assembly"></a>Isolation nach Benutzer, Domäne und Assembly  
 Wenn eine Anwendung eine Drittanbieterassembly verwendet, die einen privaten Datenspeicher erfordert, können Sie für die privaten Daten einen isolierten Speicher nutzen. Durch die Isolation nach Benutzer, Domäne und Assembly wird sichergestellt, dass nur Code in einer bestimmten Assembly auf die Daten zugreifen kann. Hierzu müssen zwei Voraussetzungen erfüllt sein. Erstens muss die Assembly von der Anwendung verwendet werden, die ausgeführt wurde, als die Assembly den Speicher angelegt hat. Und zweitens muss die Anwendung durch den Benutzer ausgeführt werden, für den der Speicher angelegt wurde. So wird bei der Isolation nach Benutzer, Domäne und Assembly verhindert, dass die Drittanbieterassembly Daten an andere Anwendungen weitergibt. Wählen Sie diesen Isolationstyp standardmäßig aus, wenn Sie isolierten Speicher verwenden möchten, sich aber nicht sicher sind, welchen Isolationstyp Sie verwenden sollen. Durch den Aufruf der statischen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>-Methode von <xref:System.IO.IsolatedStorage.IsolatedStorageFile> und die Übergabe an einen Benutzer, eine Domäne und eine Assembly gibt <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Speicher dieses Isolationstyps zurück.  
  
 Im folgenden Codebeispiel wird ein Speicher abgerufen, der nach Benutzer, Domäne und Assembly isoliert ist. Der Zugriff auf den Speicher wird durch das `isoFile`-Objekt ermöglicht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Wie im folgenden Codebeispiel gezeigt, ist eine weitere Methode als Verknüpfung verfügbar. Diese Verknüpfung kann nicht zum Öffnen von Speichern verwendet werden, für die Roaming möglich ist. Verwenden Sie in solchen Fällen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>
## <a name="isolated-storage-and-roaming"></a>Isolierte Speicherung und Roaming  
 Roamingbenutzerprofile sind ein Windows-Feature, über das ein Benutzer eine Identität in einem Netzwerk einrichten und sich damit bei jedem Netzwerkcomputer anmelden kann, wobei alle personalisierten Einstellungen übernommen werden. In einer Assembly, die isolierten Speicher verwendet, kann festgelegt werden, dass der isolierte Speicher des Benutzers gemeinsam mit dem Roamingbenutzerprofil wandert bzw. wechselt. Roaming kann in Verbindung mit der Isolation nach Benutzer und Assembly oder mit der Isolation nach Benutzer, Domäne und Assembly verwendet werden. Wenn ein Roamingbereich nicht verwendet wird, wechseln Speicher selbst dann nicht mit dem Profil, wenn ein Roamingbenutzerprofil verwendet wird.  
  
 Im folgenden Codebeispiel wird ein Roamingspeicher abgerufen, der nach Benutzer und Assembly isoliert ist. Der Zugriff auf den Speicher wird durch das `isoFile`-Objekt ermöglicht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 Ein Domänenbereich kann hinzugefügt werden, um einen Roamingspeicher zu erstellen, der nach Benutzer, Domäne und Anwendung isoliert ist. Dies wird im folgenden Codebeispiel veranschaulicht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Isolierter Speicher](isolated-storage.md)
